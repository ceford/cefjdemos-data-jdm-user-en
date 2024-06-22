<!-- Filename: Setting_up_automatic_Smart_Search_indexing / Display title: Smart Search Indexing -->

## Automatic Indexing

Although the Smart Search index is automatically kept up-to-date
whenever content items are amended, there are some circumstances where
you need to re-run the indexer. You can do this manually using the Index
toolbar button in the Smart Search: Indexed Content page. However if you need
to re-index content automatically then it is also possible to run the indexer
from the command-line. This makes it particularly convenient to run the
indexer from a *cron* job.

From the cli director the comman line is:

```
php joomla.php finder:index
```

Typical output from the command-line indexer looks like this:

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

## Purging Before Indexing

Ordinarily, running the indexer will do an incremental update of the
index. That is, it will only update the index for those content items
that have changed since the index was last updated. However, if you need
to completely clear all the existing index entries before completely
rebuilding the index, then you need to do a "purge and then index"
operation. To do that you can add the `--purge` argument to the command
line, like this

    php joomla.php finder:index -- purge

Note that this will attempt to preserve any static filters you may have
set up, whereas clicking on the "Purge" toolbar button in the
Administrator will **not** preserve your static filters.

## Setting Up a *cron* Job

Whilst the specifics are beyond the scope of this article, in general
you will merely have to enter the above command into the *cron* job
manager and specify the time or times on which the job is to be run. You
will probably need to include the full path to the indexer. For example,
like this

    php /var/www/myjoomla/cli/joomla.php finder:index -- purge

And possible the full path to the php file such as /usr/local/opt/php@8.2/bin/php

## Out of Memory Issues

If your site has particularly complex indexing requirements it is
possible that the standard memory allocation will not be sufficient for
the indexer to run to completion. You can increase the memory allocated
to the command-line indexer using an extra parameter on the
command-line, like this:

    php -d memory_limit=256M joomla.php finder:index

Replace the `256M` with whatever is appropriate for your circumstances.

The command-line indexer uses the same parameters as the indexer on the Smart
Search: Indexed Content page. You can change the parameters using the Options
toolbar button on that page. Note that both the **Indexer Batch Size** and
**Memory Table Limit** fields affect the amount of memory used by the indexer.
