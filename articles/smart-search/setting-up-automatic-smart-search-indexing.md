<!-- Filename: Setting_up_automatic_Smart_Search_indexing / Display title: Smart Search Indexing -->

## Automatic Indexing

Although the Smart Search index is automatically kept up-to-date
whenever content items are amended, there are some circumstances where
you need to re-run the Indexer. You can do this manually using the *Index*
toolbar button in the *Smart Search: Indexed Content* page. However if you need
to re-index content automatically then it is also possible to run the Indexer
from the command line interface. This makes it particularly convenient to run the
Indexer from a *cron* job.

From the cli directory the command line is:

```
php joomla.php finder:index
```

Typical output from the command line Indexer looks like this:

```sh
    Smart Search INDEXER
    ============================

    Starting Indexer
    Setting up Finder plugins
    Setup 154 items in 0.094 seconds.
     * Processed batch 1 in 0.213 seconds.
     * Processed batch 2 in 0.182 seconds.
     * Processed batch 3 in 0.177 seconds.
     * Processed batch 4 in 0.009 seconds.
    Total Processing Time: 0.676 seconds.
```

## Purging Before Indexing

Ordinarily, running the Indexer will do an incremental update of the
index. That is, it will only update the index for those content items
that have changed since the index was last updated. It will not 
remove any items from prior indexing that came from plugins that were uninstalled. 
So, if you need
to completely clear all the existing index entries before completely
rebuilding the index, then you need to do a "purge and then index"
operation. To do that you can add the `-- purge` argument to the command
line, like this

    php joomla.php finder:index -- purge

Note that this will attempt to preserve any static filters you may have
set up, whereas selecting **Maintenance→Clear Index** in the Administrator toolbar will **not** preserve your static filters.

## Setting Up a *cron* Job

Whilst the specifics are beyond the scope of this article, in general
you will merely have to enter the above command into the *cron* job
manager and specify the time or times at which the job is to be run. You
will probably need to include the full path to the indexer. For example,
like this

    php /var/www/myjoomla/cli/joomla.php finder:index -- purge

It may also be necessary to specify the full path to the php command, such as `/usr/local/opt/php@8.2/bin/php`.

## Out of Memory Issues

If your site has particularly complex indexing requirements it is
possible that the standard memory allocation will not be sufficient for
the indexer to run to completion. You can increase the memory allocated
to the command-line indexer using an extra parameter on the
command-line, like this:

    php -d memory_limit=256M joomla.php finder:index

Replace the `256M` with whatever is appropriate for your circumstances.

The command line Indexer uses the same parameters as the Indexer in the **Smart
Search: Indexed Content** page. You can change the parameters using the Options
toolbar button on that page. Note that both the **Indexer Batch Size** and
**Memory Table Limit** fields affect the amount of memory used by the indexer.
