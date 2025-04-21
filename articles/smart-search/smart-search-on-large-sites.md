<!-- Filename: Smart_Search_on_large_sites / Display title: Smart Search on Large Sites -->

## Site Indexing

Smart Search works by creating and maintaining an independent index of
search terms in a number of database tables. The problem for large sites
is that the indexing process can be quite heavy in CPU, memory and disk
usage. Even after the initial construction of the index, incremental
updates can also be heavy. The good news is that querying the index is a
relatively quick and lightweight operation.

Smart Search is suitable for the majority of Joomla sites. However,
search presents particular challenges for large sites. It should be remembered
that Smart Search is a pure PHP implementation of a search engine and
particularly large sites may be better off using a standalone search engine
such as Solr.

To use Smart Search on a large site you will probably need to adjust
some of the configuration settings. What follows is some general advice
on what to look out for and what to try tweaking.

## Always Use the CLI Indexer

Because the initial indexing process can take a long time, it is best to
run the indexer from the command line to avoid any issues from browser
sessions timing out. The CLI indexer will not timeout regardless of how
long it takes to complete and it can be easily aborted if problems are
encountered. Furthermore, error messages are visible with the CLI
indexer, whereas they might be hidden when running from the Administrator.

To use the CLI, open a terminal, switch to the cli folder in the root of your
site and issue the following command:

```
php joomla.php finder:index
```

## Batching

The indexer breaks the indexing job into batches of content items. By
default the batch size is set at 50 meaning that up to 50 content items
will be indexed per batch. Increasing the batch size will potentially
make the indexing process faster, but it will use more memory and
possibly more temporary disk space.

## Out of Memory Issues

If the indexer is running out of memory, try making the following
adjustments one at a time until the problem is resolved.

1.  Decrease the batch size. If you have particularly large content
    items the indexer can run out of memory on even a single content
    item, so try dropping it to 5 initially and if you still run out of
    memory, drop it to 1.
2.  If you are able to allocate more memory to the indexer, do so. You
    can increase the memory allocated to the command-line indexer using
    an extra parameter on the command-line. For example, to increase the
    memory limit to 256Mb use the following command, replacing the
    *256M* with as much memory as you can safely allocate to a process
    on your system.<br>
    *php -d memory_limit=256M finder_indexer.php*
5.  Try to identify which content items are causing the indexer to run
    out of memory. If it's not obvious then you might try disabling all
    Smart Search plugins except one. Running the indexer with only one
    plugin enabled at a time should reveal which content type(s) are
    causing the issue. As a last resort consider breaking a few
    exceptionally large content items into separate items. If the
    problem is with a custom content type, look at the plugin code and
    consider indexing less of the available content per item.

## Out of Disk Space Issues

The Smart Search index tables can grow quickly! The
*#__finder_links_termsX* table contain one row per term/phrase per content item and a single
Joomla article containing 1000 words will typically result in
approximately 3000 rows being added to these tables. A second article of
a similar size will add a similar number of rows even if both articles
contain the same words. A site with tens of thousands of articles, some
of which may contain thousands of words, is likely to end up with this
mapping table containing millions of rows. It is not unusual for the
index tables to occupy several gigabytes of disk space in such
circumstances.

The index has an option to decide between search precision and index size. When you have "Search for phrases" enabled in the global options of the component, your index will be bigger, but it will also allow for more precise search results. Having it disabled will mean a lot smaller index, but also no possibility to search for whole phrases.

## Notes

1.  There is currently no concurrency locking to prevent more than one
    process running the indexer at the same time. This will almost
    certainly result in a corrupt index. Even someone saving changes to
    a content item while a full index is being carried out could
    potentially damage the index.
