<!-- Filename: Customising_the_Smart_Search_results_page / Display title: Smart Search Layout Overrides -->

## Results Pages

The Smart Search component has five layout files that you can override to
produce a layout to your own liking. To initiate the process from the
Administrator menu:

* Select **System / Site Templates / Cassiopeia Details and Files**.
* Select the **Create Overrides** tab.
* From the Components panel select **com_finder**.
* Select the **Search** item
* From the Editor panel select **html / com_finder / search** to see the list
of override files created.

These files will not be affected by Joomla updates but you may be reminded to
check them if the original sources are updates

## The Search View (Default Layout)

The default layout search view is divided into several parts: the default
layout, the form layout, the results layout and the sorting layout.

### The default layout (default.php)

This layout is very simple. It just defines the structure in which
the search form and the search results are displayed. This layout is also
responsible for loading the default CSS stylesheet for Smart Search which is
located in `media/com_finder/css/finder.css`, so you might want to alter that
to load your own CSS rules for Smart Search.

### The form layout (default_form.php)

This layout defines the code required for the search form to operate
correctly. The layout uses JavaScript code so you need to take care to preserve
selectors that should not be altered unless you know what you are doing.

The view method `getFields` includes a number of hidden fields that are
required for reliable searching. The search term is defined by the input
field with the name of "q".

### The results layout (default_results.php)

This layout produces the list of matching results for the search term.
It also handles pagination and loads a layouts for each individual
search result.

### The result layout (default_result.php)

This is the layout loaded to display a single result.

### The sorting layout (default_sorting.php)

This item is only present if Show Sort Fields is set to Yes and one or more
Additional Sort Fields are selected in the Menu Item Advanced tab.
