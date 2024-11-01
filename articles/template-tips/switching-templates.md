<!-- Filename: J4.x:Switching_Templates / Display title: Switching Templates -->

## Site and Administrator Templates

Joomla 4 comes with a single Site template, Cassiopeia, and a single
Administrator template, Atum. You can obtain additional templates from
third party template suppliers, both free and paid, and you can create
your own templates, most easily as child templates.

You are unlikely to want to use an alternative Administrator template so
this article only covers alternative Site templates. For illustration, a
child template has been created with a green theme as described in the
article on Child Templates. Also, the site used for illustration has
Testing Sample Data installed.

## Default Template Style

One of your templates must be marked as the default. It is used for all
pages except any individual pages that specify an alternative template.
To set the default template:

- Select **System → Templates panel → Site Template Styles**
  from the Administrator menu.
- Select one of the buttons in the Default column.

![templates site styles list page](../../../en/images/templates/switch-templates-styles-list.png)

Have a look at your site to see that all of the pages are using the
default template.

## Using an Alternative Style

Joomla allows you to select a style for a specific page from its menu
assignment. The selection can be done from the Template Style form or
the Menu Edit form. The methods produce the same result. The first
method is more convenient for selection of a group of menu items
belonging to the same menu.

### Template Menu Assignment method

From the Templates: Styles list:

- Select a style That is **not** set as the default. The yellow star
  indicates the default style.
- Select the Menu Assignment tab.
- Select individual menu items or toggle all items in a menu.
- Save

![templates edit style page menu assignment tab](../../../en/images/templates/switch-templates-styles-edit-style-menu-assignment.png)

In this example all of the menu items in the `Main Menu Testing` menu
have been selected. Return to your site and select any of the menu items
that should use the selected template.

### Menu Details method

This method is used to set the template for individual menu items.

- Select **Menus → \[Menu Name\]** from the Administrator menu.
- Select a menu item link from the Title column to open the edit form.
- In the **Template Style** field, select the desired template style.
- Save

![templates menus edit item form showing style selection](../../../en/images/templates/switch-templates-styles-edit-menu-style.png)

Return to your site and select the changed menu item to check that it is
displayed with the selected template style.
