<!-- Filename: Enabling_the_Login_Form_module / Display title: Login Form -->

## Site Login Methods

There are two ways to allow registered users to login to the frontend of a
website. There is a **Login Form** menu item found in the Users group of menu
items. It needs its *Access* permissions set to *Guest*. A second *Logout* menu
item is needed with its *Access* permissions set to *Registered*.

The alternative is the **Login Form** module. It is installed by default in the
*sidebar-right* position in a new Joomla installation. This module can be moved
to another position, unpublished, trashed and deleted. The latter actions
apply to an instance of the module and not the module code. So you can create
a new *Login Form* module or make a duplicate, perhaps for use in different
templates. The Login Form module changes its display after login to present
a *Logout* button.

## The Login Form Module

To publish an unpublished Login Form:

*  Select **Content → Site Modules** from the Administrator menu.
*  Locate the **Login Form** module.
*  If the **Status** icon is a green tick inside a circle it is already
enabled. If the Status icon is a grey cross it is currently disabled. Select
the icon to enable the module.
* If the *Login Form* module is not present in the list set the Filter Options,
*- Select Status - field to *All* or *Trashed* to see if it has been trashed.
If so it can be published by selecting its trash icon.
* If the Login Form module is missing create a new one.

To create a new Login Form or a second Login Form:

*  Select **Content → Site Modules** from the Administrator menu.
* Select the **New** button from the Toolbar.
* From the Modules list select the **Login** item.
* Fill in the *Modules: Login* data entry form.
  - Enter a unique Title.
  - Select a template position or create a named position for use in an article.
  - Fill in other fields as appropriate.
* **Save & Close**
* Test the module appears correctly in the site frontend.

## To assign the Login Form module to selected web pages

You can make the Login Form module appear on one or more pages by
assigning it to selected Menu Items. This is done using the fields in
the Menu Assignment group on the Module Edit screen:

- Select the **Menu Assignment** tab.
- The **Module Assignment** list has four options:
  - **On all pages**: The Login Form module will appear on all pages.
  - **No pages**: The Login Form module will not appear on any page.
  - **Only on the pages selected**: A list of all menus and menu items on your
  site will appear. The Login Form module will appear on those pages selected
  in the this list.
  - **On all pages except those selected:** The Login Form will appear on all
  pages not selected.
- **Menu Selection**: Shows a list of all the Menus and Menu Items from
  which one or more may be selected. This field is only used if the
  **Menus** field is set to **Select Menu Item(s) from the List**.

  ![module menu assignment](../../../en/images/modules/modules-login-menu-assignment.png)

## To customise the Login Form module

If you wish to change the appearance of the Login module you can add styles,
either Bootstrap styles or your own styles defined in your template user.css
file. Add the styles in the **Advanced** tab of the Modules: Login edit form.

If you wish to change the information shown in the Login form you can create
a template override. See the section on
[Template Overrides](jdocmanual?article=user/templates/template-overrides)
for further details.
