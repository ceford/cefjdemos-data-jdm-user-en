<!-- Filename: J4.x:Administrator_Modules / Display title: Administrator Modules -->

## Introduction

The Atum Administrator template is provided with a complete set of
Administrator modules installed and configured for everyday use. The
following illustration shows the Home Dashboard positions to indicate
where modules are located.

![atum home dashboard positions](../../../en/images/modules/atum-template-positions.png)

In the illustration above the panels are instances of the Quick Icon
module linked to quickicon plugins.

### Notes on some Module positions

- **Custom Top** is above the banner and is useful if you wish to
  publish a Custom menu or a Custom module containing an important
  message. For example, to warn Administrators that the site will close
  shortly for system maintenance.
- **Status** is for the icons shown right aligned in the Banner.
- **Menu** is in the left sidebar of the Atum screen.
- **Toolbar** is above the Main content area in list and edit screens
  but is not present in dashboard screens.
- **Top** is below the Toolbar but above any System Message and
  component content.
- **Bottom** is below the component content.
- **Debug** is below everything.

Atum template positions by name

```xml
  <positions>
    <!-- used directly in the template -->
    <position>bottom</position>
    <position>cpanel</position>
    <position>customtop</position>
    <position>debug</position>
    <position>icon</position>
    <position>login</position>
    <position>menu</position>
    <position>sidebar</position>
    <position>status</position>
    <position>title</position>
    <position>toolbar</position>
    <position>top</position>
  </positions>
```

## Add a Custom Module

You may wish to add a Custom module to advise Administrators of some
system problem. Select **Content → Administrator Modules** from the
Administrator menu. The list of installed modules is quite long:

![atum admin modules list](../../../en/images/modules/atum-admin-modules-list.png)

Select the New button and then the Custom module. In the Modules: Custom
edit form enter a Title, a Custom message and select a Position for the
module. In the example below the Top position has been selected. Also,
in the Advanced tab, Module Class field some styles have been entered to 
centre the text and provide some padding: **alert alert-warning text-center**.
Save to see the result. Close to see the result on the Modules list page.

![atum custom module edit system message](../../../en/images/modules/atum-admin-module-system-message.png)

When you have finished with the message you can just select the Status
button in the module list to Unpublish the module.

## List of Administrator Modules

- **Action Logs - Latest** This module shows a list of the most recent
  actions.
- **Administrator Dashboard Menu** This module displays an administrator
  submenu module.
- **Administrator Menu** This module displays an administrator menu
  module.
- **Articles - Latest** This module shows a list of the most recently
  created Articles.
- **Custom** This module allows you to create your own Module using a
  WYSIWYG editor.
- **Feed Display** This module allows the displaying of a syndicated
  feed.
- **Frontend Link** This module shows a link to the frontend and is
  intended to be displayed in the 'status' position.
- **Joomla! Version Information** This module displays the Joomla!
  version and is intended to be displayed in the 'status' position.
- **Logged-in Users** This module shows a list of the Logged-in Users.
- **Login Form** This module displays a username and password login
  form. It should not be unpublished.
- **Login Support Information** This module displays some useful links
  to Joomla support sites on the login screen.
- **Messages** This module shows the count of private messages and is
  intended to be displayed in the 'status' position. It is only
  displayed when there are messages to read.
- **Multilingual Status** This module shows the status of the
  multilingual parameters and is intended to be displayed in the
  'status' position.
- **Popular Articles** This module shows a list of the most popular
  published Articles that are still current. Some that are shown may
  have expired even though they are the most recent.
- **Post Installation Messages** This module shows a counter and a link
  to the latest post installation messages. It is only displayed when
  there are messages to read.
- **Privacy Dashboard** The Privacy Dashboard Module shows information
  about privacy requests.
- **Privacy Status Check** The Privacy Status Check Module shows
  information about your sites privacy status.
- **Quick Icons** This module shows Quick Icons that are visible on the
  Home Dashboard (administrator area home page)
- **Sample Data** This module lets you install sample data.
- **Statistics** The Statistics Module shows information about your
  server installation together with statistics on the website users and
  the number of Articles in your database.
- **Title** This module shows the Toolbar Component Title.
- **Toolbar** This module shows the toolbar icons used to control
  actions throughout the Administrator area.
- **User Menu** This module shows the User Menu and is intended to be
  displayed in the 'status' position.
