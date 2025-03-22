<!-- Filename: Smart_Search_quickstart_guide / Display title: Smart Search Quickstart -->

## Background

Search has been a feature of Joomla! since its early days. It allowed users to search the database for words or phrases and return results in first found order. That form of search has been removed and replaced by Smart Search, which pre-indexes significant words and uses scoring and filtering algorithms to help return the best results. Smart Search is enabled by default in Joomla 4+.

### Be Aware

If you have content items that are not available for public view the auto-completion feature will still show terms contained in those content items. The content items themselves cannot be viewed and will not be listed in search results but if revealing the presence of a word or phrase in a restricted content item is of concern then you should disable auto-completion. To disable auto-completion use the following procedure:

1.  Login to the Administrator interface.
2.  Select **Components → Smart Search → Index**.
3.  Select the **Options** toolbar button.
4.  In the *Smart Search* tab change *Search Suggestions* from **Show** to **Hide**.
5.  Select **Save & Close**.

## Preparing Smart Search plugins

For content to be displayed in search results it must first be indexed by one of the Smart Search plugins. Joomla! includes Smart Search plugins for articles, categories, contacts, news feeds and tags. Third party components may include their own Smart Search plugins too. 

Before starting the Indexer, it is recommended that you review the available plugins and disable any that will not be necessary for your site. To review the available Smart Search plugins use the following procedure:

1.  Login to the Administrator interface.
2.  Select **Plugins** from the *Home Dashboard* Site panel. Or...
    - Select **System → Plugins** from the Manage panel.
3.  Filter the plugins using the **finder** item from the **- Select Type -** list.
4.  Review the list of plugins and disable any that will not be necessary for your site by selecting the green tick/circle icon in the Status column for the plugin. This should change to a grey cross/circle to indicate that the plugin is disabled.

## Running the Indexer

After you have reviewed the search plugins, it is time to start the Smart Search Indexer. This will scan the content on your Website and build an index that will enable fast and intelligent searching by your site visitors. There are two ways to run the Indexer:

* From the **Administrator → Smart Search → Index** menu. This is suitable for smaller sites.
* From the Command Line. This is suitable for larger sites and should not incur time-out faults. However, very large sites might really need an external search service.

**Note:** Smart Search will return no results until you have run the Indexer. Article content is re-indexed whenever an article is added or changed. Other types of content may require running the Indexer via the Administrator interface or the Command Line Interface (CLI).

### Index from the Administrator interface

1.  Login to the Administrator interface.
2.  Select **Components → Smart Search → Index** from the Administrator menu.
3.  Select the **Index** button in the toolbar to start the Indexer. This will cause a modal window to load with some Indexer status information and a progress bar.

Depending on the size of your site, indexing can take a few minutes to a few hours to complete. The Indexer uses AJAX requests to complete the overall process in small chunks to avoid timeouts and memory problems. Indexing is complete when the progress bar disappears and the modal window closes.

### Index from the CLI

This method requires access to your site's file system via a terminal (command shell) window.

1. Open a terminal window.
2. cd to the cli folder in the root of your site.
3. Use the following command:<br>
    php joomla.php finder:index
4. When the Indexer has finished go to the Administrator Smart Search: Indexed Content page.

## Indexed Content

The Indexed Content page lists all the indexed content. If you would prefer that specific items not be displayed in search results, you can unpublish them from the Smart Search database by selecting the checkbox next to the title of the item and then selecting the Actions → Unpublish button. Individual items  can be unpublished by selecting Status green tick icon.

**IMPORTANT NOTE**: If your site has a large amount of content, or particularly large content items, or has restricted disk space, you should read about [Smart Search on large sites](jdocmanual?article=user/smart-search/smart-search-on-large-sites "Smart Search on large sites").

## Exposing Smart Search to Site Users

Now that the Smart Search index is prepared and ready, you need to expose Smart Search to your Website's users. Smart Search offers two ways to do this:

### The Module Interface

Smart Search includes a module that can be enabled to display a simple search form on any page in virtually any template position. To enable the Smart Search module use the following procedure:

1.  Log in to the Administrator interface.
2.  Select the **Content → Site Modules** menu item.
3.  Select the **New** button in the Modules list Toolbar.
4.  Select **Smart Search** module from the list of module types.
5.  Configure the module by (at least):
    - Enter a title
    - Selecting a template position
    - Adjust the pages where it should be displayed if desired.
    - Additional module configuration options are described in the Smart Search module help screen.
6.  Select the **Save** button in the toolbar to publish the module.

### The Menu Item Interface

Smart Search can also be linked to via a Joomla menu item so that users can navigate directly to the main search form. To create a menu item link to Smart Search use the following procedure:

1.  Log in to the Administrator interface.
2.  Select the **Menus → Main Menu** menu item. Or ...
    - Select the applicable menu if it's not Main Menu.
3. Select the **New** button in the *Menus: Items* toolbar.
4. Select the **Select** button next to the *Menu Item Type* field.
5. Select **Search** from the *Smart Search* entry in the list of menu item types.
6. Configure the menu item by (at least) entering a menu Title and adjusting the parent item if desired.
7. Select the **Save** button in the toolbar to publish the menu item.

## Search Filters

Search filters can be used to pre-filter searches meant to focus on specific content. These filters can be selected when configuring a Smart Search module or menu item instance; they cannot be selected by site users. To create a new Filter:

1. Log in to the Administrator interface.
2. Select the **Smart Search → Filters** menu item.
3. Select the **New** button and give the new filter a name.
4. Select the filter criteria for the various taxonomies.
5. Select **Save and Close**.
6. Create a new menu or module Smart Search instance and select the filter.

**Note:** These filters do not seem to change the selections available in the front end at all. Therefore, their usefulness is questionable.

## Search Terms

Over time, your site's users will search for a wide variety of terms and phrases. The Search Terms page lists all of the search terms entered and the number of times each one was searched. This gives you a way to know what your users search for the most. To access this page:

1. Log in to the Administrator interface.
2. Select the **Smart Search → Search Terms** menu item.

You can clear all the Search Term results by selecting the **Reset** button at the top of the page.

## Plugin Settings

Each Smart Search plugin will likely have settings specific to the component the plugin supports. If you want to limit what your site users can select in terms of taxonomies, you must configure all the plugins in a consistent way to achieve that. The default taxonomies for Joomla!'s default content are as follows. Additionally, you can select whether to search archived content.

- Language
- Country
- Region
- Type (Articles, Categories, Tags)
- Author
- Category

For example, if all your site's articles are written by the same person, you may want to omit Author in all your Smart Search plugins. Similarly, if your site is written entirely in a single language, the omitting Language would make sense. By omitting taxonomies, you limit the choices your site users must select when doing a search.

## Testing, Testing, Testing

To test Smart Search, navigate to the menu item you created and enter a query in the search form or enter a query into one of the instances of Smart Search module. You should be taken to a list of search results if any could be found for the word or phrase you entered. If no results could be found, a message will be displayed indicating that no results could be found. If no results could be found and the system has a search suggestion based on your term (if you enabled Search Suggestions in the Smart Search configuration), the suggested search phrase will display above the message indicating no results could be found.
