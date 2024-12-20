<!-- Filename: J4.x:Login_and_Logout_Redirects / Display title: Login and Logout Redirects -->

## Defaults

Login and Logout have options to select a page to redirect to on
success. There are defaults but they may not be appropriate for your
site. For example the Login form leads to the User Profile page by
default. That becomes tedious if there is no good reason to see the
Profile page on every login.

This article covers the redirect options available after successful
login or Logout.

## Login Module

The default behaviour of a login module is to stay on the same page
after login and logout. The only snag with this behaviour is that a user
logging out from a restricted page will be prompted to login in again.
If this is troublesome an easy solution is to select the Home page to
redirect to in the Module settings Logout Redirection Page field.

![logout menu form restricted to registered access](../../../en/images/users/login-redirects-login-form.png)

Tip: You could use two login modules. One with **Guest** access entitled
**Login**. The second with **Registered** access entitled **Logout**.

## Login Menu Item

The login menu item item type may be used for login and logout. If used
for both purposes it should have a title such as Login/Logout. If you
find that clumsy you can use separate menu items for Login and Logout.

The Login menu item type allows a choice of Login Redirect Type: by Menu
Item or by Internal URL. By default, Menu Item is selected but not set
and login leads to the User Profile page. You can select a menu item or
you can give the URL of a page. For example you could have a System
Status page with a hand-crafted message of the day.

![logout menu form restricted to registered access](../../../en/images/users/login-redirects-login-menu-options.png)

The default Logout behaviour is to redirect to the site Home page. You could 
redirect to something else, such as Good Bye message linked by a menu item or 
an internal URL.

## Logout Menu Item

The Logout menu item is simple. The default is to stay on the same page
after logout. If that proves inconvenient, select the site Home page.

![logout menu form restricted to registered access](../../../en/images/users/login-redirects-logout-menu-options.png)
