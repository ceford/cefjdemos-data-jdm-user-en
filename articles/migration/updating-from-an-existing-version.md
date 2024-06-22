<!-- Filename: J4.x:Updating_from_an_existing_version / Display title: Version Update -->

## Introduction

**Remember: Always back up your site before updating.**

The recommended way to update installations of Joomla! is to use the *Joomla
Update Component*.

A standard installation of Joomla 4 and later includes a helpful notifications
panel on the Home Dashboard after login. You can see at a glance if an update
is available and the version number.

The Update message that appears in the Notifications panel depends on the
*Update Chennel* set in the *Joomla Update: Options* page and the current
*Minor* version. With **Update Channel** set to **Default**, updates within the
current *Major* version are notified. With the Parameter set to *Joomla Next*
you may update to the latest current version and then select the
**Check for Updates** button to see if the next *Major* version is available.

Although Joomla will notify you when an update is available, it requires you to
carry out the update. It is a simple process that should be carried out at the
earliest opportunity to keep the site up to date.

## Accessing the Update Component

If the notifications panel is displayed in the Home Dashboard, select the
**x.y.z Available - Update Now!** button go to the Update Component.

<img
src="https://docs.joomla.org/images/thumb/f/f5/J4x_joomla_update_notification-en.png/800px-J4x_joomla_update_notification-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/f/f5/J4x_joomla_update_notification-en.png 1.5x"
data-file-width="1000" data-file-height="444" width="800" height="355"
alt="joomla update notification" />

Alternatively, to access the Update Component from the Administrator menu,
select **System** to go via the **System Dashboard**.

<img
src="https://docs.joomla.org/images/thumb/1/14/J4x_joomla_system_dashboard_update-en.png/800px-J4x_joomla_system_dashboard_update-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/1/14/J4x_joomla_system_dashboard_update-en.png 1.5x"
data-file-width="1000" data-file-height="399" width="800" height="319"
alt="joomla system dashboard update" />

The System Dashboard has an *Update Panel* which includes a Joomla link
that will show the available update version number. Select the **Joomla**
link to go to the Update Component.

## Carrying out the Update

Joomla! 4 and 5 providee a Pre-Update Check for Updates to Minor Versions.
This view of the Joomla Update component shows technical specifications of
the server the site is on and core and third-party extensions that use the
Update Server in a list form.

**Note:** The *Pre-Update Check* screen is not displayed if the site is on the
current **Minor** version.

<img
src="https://docs.joomla.org/images/thumb/5/5d/J4x_joomla_pre_update_check-en.png/800px-J4x_joomla_pre_update_check-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/5/5d/J4x_joomla_pre_update_check-en.png 1.5x"
data-file-width="1000" data-file-height="882" width="800" height="706"
alt="joomla pre update check" />

Pay careful attention to check results and take action to rectify any issues
highlighted before updating. You may need to update, disable or uninstall
incompatible extensions before updating Joomla.

It is not uncommon to see warnings for *Recommended Settings* as these
are often server specific and hosting related. It is likely they existed when
you installed Joomla and most likely won't prevent the update from completing.

*Note the reminder that you are strongly advised to take a backup if you
haven't already!*

There is a link below the update button. In most cases you can ignore
this link. It provides an option to manually upload the update files if
your server is behind a firewall or otherwise unable to contact the
Joomla update servers.

When you have reviewed the Pre-Update Check and are happy, select **Update**.

### Confirming the Update

<img
src="https://docs.joomla.org/images/thumb/c/c3/J4x_joomla_start_update-en.png/800px-J4x_joomla_start_update-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/c/c3/J4x_joomla_start_update-en.png 1.5x"
data-file-width="1000" data-file-height="645" width="800" height="516"
alt="joomla start update" />

Click the checkbox to confirm you have made a backup and checked
extensions are compatible then click the **Start Update**.

### Update Progress

<img
src="https://docs.joomla.org/images/thumb/c/cd/J4x_joomla_update_progress-en.png/800px-J4x_joomla_update_progress-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/c/cd/J4x_joomla_update_progress-en.png 1.5x"
data-file-width="1000" data-file-height="193" width="800" height="154"
alt="joomla update progress" />

Once the update starts a progress bar will appear as the Joomla files
are updated.

### Completion

<img
src="https://docs.joomla.org/images/thumb/9/9a/J4x_joomla_updated-en.png/800px-J4x_joomla_updated-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/9/9a/J4x_joomla_updated-en.png 1.5x"
data-file-width="1000" data-file-height="274" width="800" height="219"
alt="joomla updated" />

When the progress bar reaches 100% a system message will confirm your
site has been updated and the version number. The version number will
also update in the top toolbar, next to the site name.

Click the **Back** button and you will be returned to the Joomla Update
Component where it is possible to check for updates again.

## Post Update Checks

Once the update is complete you should carry out some checks to make
sure everything went as expected, that no errors are present and that
there have been no changes that require further action.

### Frontend Check

Go to the front end of the website and check it is working and displaying as
it did prior to the update. Use the *Shift + Reload* combination to force your
browser to reload any changes to stylesheets and scripts.

### System Checks

From the sidebar menu select **System** to be taken to the System Dashboard.
This gives you an overview of the current status of your Joomla site.

<img
src="https://docs.joomla.org/images/thumb/7/71/J4x_system_dashboard-en.png/800px-J4x_system_dashboard-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/7/71/J4x_system_dashboard-en.png 1.5x"
data-file-width="1000" data-file-height="715" width="800" height="572"
alt="system dashboard" />

In this example we can see that since the update we have two items that
require attention. They are marked with a label that includes a number.
The number relates to how many items require attention. Clicking on each
one will allow you to fix them.

**Note** The System Dashboard makes a check each time the page is
loaded. Bear in mind that browser caching settings could affect this.
It's good practice to clear the browsers cache when checking using
*Shift + Reload*.

### Database Check

Navigate to **System → Maintenance → Database**. If your database is up to
date, you should see a screen similar to the one below:

<img
src="https://docs.joomla.org/images/thumb/0/08/J4x-update-screenshot-db-ok-en.png/800px-J4x-update-screenshot-db-ok-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/0/08/J4x-update-screenshot-db-ok-en.png 1.5x"
data-file-width="1000" data-file-height="434" width="800" height="347"
alt="Database Screen With No Problems" />

If your database is not up to date, you will see a screen listing the problems
found, similar to the one below:

<img
src="https://docs.joomla.org/images/thumb/4/42/J4x-update-screenshot-db-not-ok-en.png/800px-J4x-update-screenshot-db-not-ok-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/4/42/J4x-update-screenshot-db-not-ok-en.png 1.5x"
data-file-width="1000" data-file-height="527" width="800" height="422"
alt="Database Screen With 3 Database Problems" />

In this case, select the problem extension *Name* and then the Update Structure
button in the Toolbar. Joomla will update your database to correct the issues
listed and then it will re-display the screen. If the fix was successful, the
display will indicate that the database is up to date.

**N.B.** If any errors still exist make sure all the database tables are
checked in.

## System Discover

In some cases, when you update to a new Joomla version, new core
extensions are added. If there were problems with the database update,
these extensions may not have been correctly installed. To check this,
navigate to **System → Discover**. Then select the Discover icon
in the toolbar. The screen should show as follows:

<img
src="https://docs.joomla.org/images/thumb/1/12/J4x-update-screenshot-extensions-en.png/800px-J4x-update-screenshot-extensions-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/1/12/J4x-update-screenshot-extensions-en.png 1.5x"
data-file-width="1000" data-file-height="539" width="800" height="431"
alt="Discover Screen With No Extensions To Install" />

If so, you know that any new extensions added during the update were
correctly installed in the database.

If there are uninstalled extensions, they will show similar to the
following screen:

<img
src="https://docs.joomla.org/images/thumb/1/13/J4x-update-screenshot-uninstalled-ext-en.png/800px-J4x-update-screenshot-uninstalled-ext-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/1/13/J4x-update-screenshot-uninstalled-ext-en.png 1.5x"
data-file-width="1000" data-file-height="325" width="800" height="260"
alt="Discover Screen With One Extension To Install" />

In this case, check the boxes and click on the Install icon in the
toolbar. Joomla will install the extension(s) and then display the
screen showing no extensions discovered. At this point, the new
extensions have been installed in the database.

## Troubleshooting

If you have any questions, problems or errors before, during or after
the update, please ask them on the
**<a href="https://forum.joomla.org/viewforum.php?f=812" class="extiw"
title="jforum:812">Migrating and Upgrading to Joomla! 4.x Forum</a>**.

If you have problems or errors during the update process, here are some
tips.

- Clearing your browser cache. There may have been changes to the CSS or
  Javascript that will need to be reloaded by your Web browser after an
  update.
- If any database error messages show after the update, be sure to check
  the **System → Maintenance panel → Database** link. In some
  cases, if a database error occurs it will prevent all of the database
  updates from running. In this case, you can run them from the Database
  link and then use the **System → Install → Discover** method
  to check and install any new extensions.
- The update process creates or appends to a log file named
administrator/logs/joomla_update.php which you can open with a text editor to
see the steps recorded in the log. It will be show the major steps (donload zip,
install, run SQL statements, clean up), something like this:

```
2024-04-17T09:13:16+00:00	INFO 127.0.0.1	update	Update started by user Jimmy (139). Old version is 5.0.3.
2024-04-17T09:13:18+00:00	INFO 127.0.0.1	update	Downloading update file from ...
2024-04-17T09:13:28+00:00	INFO 127.0.0.1	update	File Joomla_5.1.0-Stable-Update_Package.zip downloaded.
2024-04-17T09:13:28+00:00	INFO 127.0.0.1	update	Starting installation of new version.
2024-04-17T09:13:40+00:00	INFO 127.0.0.1	update	Finalising installation.
2024-04-17T09:13:40+00:00	INFO 127.0.0.1	update	Start of SQL updates.
2024-04-17T09:13:40+00:00	INFO 127.0.0.1	update	The current database version (schema) is 5.0.0-2023-09-11.
... Lots of individual SQL queries
2024-04-17T09:13:41+00:00	INFO 127.0.0.1	update	End of SQL updates.
2024-04-17T09:13:41+00:00	INFO 127.0.0.1	update	Uninstalling extensions
2024-04-17T09:13:41+00:00	INFO 127.0.0.1	update	Deleting removed files and folders.
2024-04-17T09:13:44+00:00	INFO 127.0.0.1	update	Cleaning up after installation.
2024-04-17T09:13:44+00:00	INFO 127.0.0.1	update	Update to version 5.1.0 is complete.
```
