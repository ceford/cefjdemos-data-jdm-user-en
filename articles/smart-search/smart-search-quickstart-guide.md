<!-- Filename: Smart_Search_quickstart_guide / Display title: Smart Search Quickstart -->

## Background

Search has been a feature of Joomla! since its early days. It allowed
users to search the database for words or phrases and return results in first
found order. That form of search has been removed and replaced by Smart Search,
which pre-indexes significant words and uses scoring and filtering algorithms
to help return the best results. Smart Search is enabled by default in Joomla 4
and 5.

### Be aware

If you have content items that are not available for public view the
auto-completion feature will still show terms contained in those content items.
The content items themselves cannot be viewed and will not be listed in search
results but if revealing the presence of a word or phrase in a restricted
content item is of concern then you should disable auto-completion. To
disable auto-completion use the following procedure:

1.  Login to the Administrator.
2.  Select **Components → Smart Search**.
3.  Select the **Options** toolbar button.
4.  Change *Search Suggestions* from **Show** to **Hide**.
5.  Select **Save & Close**.

## Preparing Smart Search plugins

For content to be displayed in search results it must first be indexed
by one of the Smart Search plugins. Before starting the indexer, it is
recommended that you review the available plugins and disable any that
will not be necessary for your site. To review the available Smart
Search plug-ins use the following procedure:

1.  Login to the Administrator.
2.  Select the **Plugins** from the *Home Dashboard*.
3.  Filter the plugins using the **finder** item from the **- Select Type -** list.
4.  Review the list of plug-ins and disable any that will not be
    necessary for your site by selecting the green tick icon in the
    Status column for the plug-in. This should change to a grey cross/circle to
    indicate that the plug-in is disabled.

## Running the Indexer

After you have reviewed the search plug-ins, it is time to start the
Smart Search indexer. This will scan the content on your Website and
build an index that will enable fast and intelligent searching by your
site visitors. There are two ways to run the indexer:

* From the **Administrator / Smart Search / Index** menu. This is suitable for
smaller sites.
* From the Command Line. This is suitable for larger sites and should not incur
time-out faults. However, very large sites might really need an external
search service.

### Index from the Administrator interface

1.  Login to the Administrator.
2.  Select the **Components → Smart Search → Index** menu items.
3.  Select the **Index** button in the toolbar to start the indexer. This
    will cause a modal window to load with some indexer status
    information and a progress bar.

Depending on the size of your site, indexing can take a few minutes to a few
hours to complete. The indexer uses AJAX requests to complete the overall
process in small chunks to avoid timeouts and memory problems. Indexing is
complete when the progress bar disappears and the modal window closes.

### Index from the CLI

1. Open a terminal window.
2. cd to the cli folder in the root of your site.
3. Use the following command:<br>
    php joomla.php finder:index
4. When the indexer has finished go to the Administrator Smart Search: Indexed
Content page.

## Indexed Content

The Indexed Content page lists all the indexed content. If you would prefer
that specific items not be displayed in search results, you can unpublish them
from the Smart Search database by selecting the checkbox next to the title of
the item and then pressing the Unpublish button.

**IMPORTANT NOTE**: If your site has a large amount of content, or
particularly large content items, or has restricted disk space, you
should read about [Smart Search on large
sites](jdocmanual?article=user/smart-search/smart-search-on-large-sites "Smart Search on large sites").

## Exposing Smart Search to Site Users

Now that the Smart Search index is prepared and ready, you need to
expose Smart Search to your Website's users. Smart Search offers two
ways to do this:

### The Module Interface

Smart Search includes a module that can be enabled to display a simple
search form on any page in virtually any position. To enable the Smart
Search module use the following procedure:

1.  Log in to the Administrator.
2.  Select the Extensions → Module Manager menu item.
3.  Click the New button in the Module Manager toolbar.
4.  Select "Smart Search Module" from the list of module types shown.
5.  Configure the module by (at least) entering a title, selecting the
    module position, and adjusting the pages for it to display on if
    desired. Additional module configuration options are described on
    the Smart Search module help screen.
6.  Select the Save button in the toolbar to publish the module.

### The Menu Item Interface

Smart Search can also be linked to via a Joomla menu item so that users
can navigate directly to the main search form. To create a menu item
link to Smart Search use the following procedure:

1.  Log in to the Administrator.
2.  Select the Extensions → Module Manager menu item.
3.  Press the New button in the Menu Manager toolbar.
4.  Click the Select button next to the Menu Item Type field.
5.  Select "Search" under the "Smart Search" entry on the list of menu
    item types shown.
6.  Configure the menu item by (at least) entering a Menu Title and
    adjusting the parent item if desired.
7.  Select the Save button in the toolbar to publish the menu item.

## Testing, Testing, Testing

To test Smart Search, navigate to one of the menu items you created and
enter a query in the search form or enter a query into one of the
instances of Smart Search module. You should be taken to a list of
search results if any could be found for the word or phrase you entered.
If no results could be found, a message will be displayed indicating
that no results could be found. If no results could be found and the
system has a search suggestion based on your term, the suggested search
phrase will display above the message indicating no results could be
found.
