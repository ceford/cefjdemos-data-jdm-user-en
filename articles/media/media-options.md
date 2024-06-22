<!-- Filename: J4.x:Media:_Options / Display title: Media: Options -->

## The Options Form

To access the Media: Options form select the **Options** button in the
Toolbar on the Media page. The fields are well commented and provided
with default values that should be suitable for almost all sites. You
usually only need to use the options form if you wish to keep Files
separate from Images or if you have an unusual file format not included
in the default list.

**Beware:** there are security implications associated with some types
of file - a hacker's way in.

## Separate Files

To set up a location for files that is separate from images first create
a new folder in the root of your installation, for example **files**.
Remember, it will be part of a url link so lower case and no spaces or
punctuation marks.

### FileSystem - Local Plugin

Find the *FileSystem - Local* plugin in the list of plugins and open it. Add
your newly created file folder to the list of places you can keep media.
Just click on the + button and select **files** from the list of available
folders.

![File System Plugin](../../../en/images/media/media-filesystem-local-plugin.png "File System Plugin")

The **Create Thumbnails** option set to **Yes** causes creation of small images
with a maximum height or width of 200 pixels in media/cache/com_media/thumbs
with the same folder structure as the media folder. It should greatly increase
the display speed of a folder with many images.

Make sure the plugin is enabled. **Save & Close**.

### Options Form

In the Options form enter the folder name in the **Path to Files
Folder** field. Make sure you do not use the name of an existing core
Joomla folder.

<img src="https://docs.joomla.org/images/9/98/J4.x-media-options-en.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="406" width="800" height="406"
alt="media options" />

## Screenshot

When set up, you will be able to choose between the images and files
folders in the Local part of the Media view.

<img
src="https://docs.joomla.org/images/0/08/J4.x-media-images-files-en.png"
class="thumbborder" decoding="async" data-file-width="800"
data-file-height="406" width="800" height="406"
alt="media images and files" />
