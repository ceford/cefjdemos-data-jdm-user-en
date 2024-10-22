<!-- Filename: J6.x:Media_File_Locations / Display title: Media File Locations -->

## Introduction

By default, Joomla stores both user images and document files in the */images*
folder of the the Joomla installation. Any links to such media are not directly 
processed by Joomla. The web server sends them when requested by the browser.

If you have a lot of documents you might like to keep them in a separate folder,
most obviously a */files* folder also in the root of the Joomla site.

To set up a location for files that is separate from images first create
a new folder in the root of your installation, for example **files**.
Remember, it will be part of a url link so lower case and no spaces or
punctuation marks.

### FileSystem - Local Plugin

Find the *FileSystem - Local* plugin in the list of plugins and open it. Add
your newly created *files* folder to the list of places you can keep media.
Just click on the + button and select **files** from the list of available
folders.

![File System Plugin](../../../en/images/plugins/plugin-group-file-system-local.png)

The **Create Thumbnails** option set to **Yes** causes creation of small images
with a maximum height or width of 200 pixels in media/cache/com_media/thumbs
with the same folder structure as the media folder. It should greatly increase
the display speed of a folder with many images. It is not needed for files
as they are represented by icons.

Make sure the plugin is enabled. **Save & Close**.
