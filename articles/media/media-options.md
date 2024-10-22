<!-- Filename: J4.x:Media:_Options / Display title: Media: Options -->

## Introduction

The *Media: Options* page is used to control upload and storage of media,
both images and files. **Beware:** there are security implications associated 
with some types of file - a hacker's way in.

To access the *Media: Options* form select the **Options** button in the
Toolbar on the Media page. The fields are well commented and provided
with default values that should be suitable for almost all sites. You
usually only need to use the options form if you wish to keep Files
separate from Images or if you have an unusual file format not included
in the default list.

## Screenshot

![The media Options form](../../../en/images/media/media-options.png)

## Path to Files and Folders

These are separate items in the configuration form but they both point to the
the *images* folder in a new Joomla installation. If you would like to store
non-image media separately (for example PDFs, Spreadsheets and Text files)
use the following steps:

1. Create a folder named *files* in the root of your Joomla installation.
2. Enable the * FileSystem - Local* plugin and configure it, described in the 
   article on [Media File Locations](jdocmanual?article=user/media/media-file-locations).
3. Enter the folder name, *files*, in the *Path to Files Folder* field of the
   Media Options Form

In the Options form enter the folder name in the **Path to Files
Folder** field. Make sure you do not use the name of an existing core
Joomla folder.

When set up, you will be able to choose between the images and files
folders in the Local part of the Media view.

![The media page](../../../en/images/media/media-sample-data-cassiopeia.png)

## Additional Image or Document Types

You may find that an Image or Document cannot be uploaded. If so, check that
its extension is amongst the *Allowed Extensions*, that its extension is amongst
the *Legal Extensions Types* for the media, and that it is amongst the 
*Legal MIME Types* (you may have to look this up). All three must be correct
or upload will be denied.