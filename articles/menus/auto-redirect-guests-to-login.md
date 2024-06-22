<!-- Filename: Auto_redirect_guests_to_login / Display title: Auto redirect guests to login -->

## Desired Functionality

Suppose you have some menu choices that require a user to be logged in,
such as *Submit an Article*. You would like all users to be able to see the
restricted menu item whether or not they are logged in. The desired behaviour
is as follows.

* If the user is logged in the user goes directly to the restricted menu item.
* If the user is not logged in the user is presented with the login form and on
successful login continues on to the restricted page.
* If the user is not registered, the user has the option to register or navigate
to another page.

## Solution

Here is how you do this in Joomla!.

1.  Create a new menu from **Menus** list, named say **Hidden Menu**.
2.  Add any menu items that will be accessible only to registered users
    (for example, *Submit an Article*). Set the required access levels
    of these menu items to **Registered**.
3.  Do NOT create a module for the *Hidden menu*. It will not be
    displayed on any page, so it doesn't need a module.
4.  Create your *real* menu, named say **Site Menu**, and the menu item
    that will display for all users, say *Submit an Article*.
    - The menu item will have a menu item type of **Menu Item Alias** found
    in the **System Links** Menu Item Type.
    - It's *Menu Item* parameter will be the *Submit an Article* menu
      item in the *Hidden Menu**.
    - The Access Level for this menu item will be **Public**, since everyone
    needs to be able to see and use it.
5.  Create a module for *Site Menu* just like you do for any menu.
6.  If you want sub-menus, make sure you've added the sub-menu items in
    the **Site Menu** and not the **Hidden menu**.

Now when a guest (non-logged-in user) accesses the *Submit an Article*
menu choice it redirects to the login page. If login is successful the user
is redirected to the restricted **Submit an Article** page. If already logged
in the redirection is immediate.

## Example

For the following menu items:

1.  Home
2.  Blog
3.  Wiki
4.  Directory
5.  Classifieds
6.  FAQS
7.  Shop
8.  Contact Us

All the menu items should be viewable by everyone in the front end but
items 3,4,5,6 and 7 should be accesible to **Registered** users only.

In this case, menu items 3 to 7 are located in the *hidden* menu with their
**Access** parameter set to **Registered**. Items 3 to 7 have *Alias* menu
items in the *real* menu with their **Access** parameters set to **Public**.

