<!-- Filename: J3.x:Plugin_Joomla_Update_Notification / Display title: Joomla! Update Notification -->

## Icon and Task

There are two plugins with similar names:

* **Quick Icon - Joomla! Update Notification**
* **Task - Joomla! Update Notification**

The first checks for Joomla updates and notifies you when you visit the Home
Dashboard page.  It has one parameter: the Group of this plugin (this value is
compared with the group value used in Quick Icons modules to inject icons).

The second periodically checks for the availability of new Joomla! versions.
When one is found it triggers a task to send an update reminder email to Super
Users. The email can be customised via *System → Mail Templates*.

The emails sent by the Joomla! Update Notification System plugins are
intended to help keep the software up to date, which helps the website
stay secure. Updates should be installed as soon as possible after release.

## Plugin Status

The two separate plugins may each be Enabled or Disabled.

- With **Quick Icon ... Disabled** the Home Dashboard *Checking Joomla ...*
icon remains inactive, although you can select it to go to the Joomla update
page.
- With **Task ... Disabled:** the task to send an email is not triggered.

## Task Parameters

From the Administrator menu go to **System / Scheduled Tasks** and select the
**Update Notification** item from the *Scheduled Tasks* list. There are a
number of parameter and information tabs there to view and change if
appropriate.

### Frequency of Notification Emails

The frequency of task execution is set to 24 hours by default. That means the
Joomla website will check for an update to core and all extensions, plugins,
modules and templates installed at 24 hour intervals. A value of 0 would
send an update email every time the site is accessed. 0 is for testing only!

Note that the task is triggered by site activity. If you are the only user it
will be triggered at your next visit if that is a lapse of more than 24 hours.

### Super User Emails

The email notification is sent only to users who have the Super User
privilege. This field allows you to select which Super users will
receive the email notifications.

- If left blank, all Super Users of the site will receive the update
  notification email.
- To limit which Super Users receive the update notification enter the
  email addresses for the Super Users here. If there are multiple Super
  Users email addresses use a comma to separate them.

### Email Language

The notification can be sent in any language you are using in your
website.

- **Auto (default)** sends the update notification email in the default
  site language.
- Selecting a language other than Auto (default) forces the update
  notification emails to be sent in this specific language.

## Quick Tips

- To turn off Joomla! update email notifications simply disable the
  plugin.
- The email Subject and Body text can be modified via the
**System / Email Templates** list. Select the **Joomla: Update Notification**
item. In a multi-lingual site it will be in the currently selected language.
  - **Subject** Note the {SITENAME} – {URL} placeholders are substituted when
  the message is sent.
  - **Body** More placeholders there too!

