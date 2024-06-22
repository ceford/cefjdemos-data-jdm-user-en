<!-- Filename: J4.x:Hosting_Setup / Display title: cPanel Hosting -->

## Introduction

## cPanel Hosting

When you login to your cPanel hosting service, this is what you should
expect to see:

<img
src="https://docs.joomla.org/images/thumb/7/7b/J4.x-hosting-setup-cpanel-en.png/800px-J4.x-hosting-setup-cpanel-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/7/7b/J4.x-hosting-setup-cpanel-en.png 1.5x"
data-file-width="1000" data-file-height="508" width="800" height="406"
alt="cpanel hosting control panel" />

### Database Setup

The Databases panel is used to create a database and database user for
Joomla.

Select the MySQL Databases item and enter a database name in the form.
The first part of the form is predefined. The rest is up to to you. It
should be short and perhaps not obvious - *jblog* for example.

In the same form, go down to the *Add New User* section. Enter a user
name. This can be anything you like. It will be used in your Joomla
configuration file so it is not something you need to remember. Use the
password generator to create an unmemorable password and copy it to a
text editor - you will need it during Joomla installation.

In the same form, go down to *Add User to Database*. Select the user you
created and the database you created from the drop-down lists and then
click the Add button. A form to Manage Privileges opens. Select the *All
Privileges* check box and then click the *Make Changes* button.

That is it - you now have a database ready for a Joomla installation.

### Upload Joomla Source

At some stage you will have downloaded the Joomla source code zip file
to your own laptop or desktop computer. You now have to decide how to
structure your site. The document root for your site is the
*public_html* folder. You could put Joomla there. However, that prevents
you from using another application on the same site. For example, you
could have two entirely separate Joomla installations, one for
production (public viewing) and one for testing (private viewing). So
you could create a folder within *public_html*, named *j4* for example,
and upload Joomla there. You could have another folder named *j4test*
and put another copy of Joomla there. The illustration below shows such
a set-up with two Joomla websites.

<img
src="https://docs.joomla.org/images/thumb/0/01/J4.x-hosting-setup-cpanel-file-manager-en.png/800px-J4.x-hosting-setup-cpanel-file-manager-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/0/01/J4.x-hosting-setup-cpanel-file-manager-en.png 1.5x"
data-file-width="1000" data-file-height="508" width="800" height="406"
alt="cpanel hosting file manager" />

When you have decided on your structure, select you chosen Joomla folder
in File Manager and click the Upload button. In the upload form, select
the Joomla source zip file on your local computer to upload it to the
selected folder. After upload, go back to File Manager, select the *zip*
file and click the Extract button. After extraction, you can select and
delete the *zip* file.

That is it! You are ready to install Joomla.

