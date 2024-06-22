<!-- Filename: Installing_an_extension / Display title: Installing an extension -->

## Extension Documentation

Before starting it is always wise to read the documentation associated
with an extension. Most extensions have home pages and forums, and it is
a good idea to look at them first. If there is a README file included
with the extension, you should read it. There may be special installation
or configuration instructions.

## System Install Extensions

The System / Install / Extensions form is fairly well documented in the
Help screen. What is not so obvious is that each of the install methods
is a plugin. In early editions of Joomla 4 the Install from Web plugin
was first in the list and it is possible that is still the case in
versions that have been updated. Having that method first is
inconvenient if you usually use one of the other methods because it
takes a few seconds to fetch data from the Joomla Extensions Directory
site.

To change the order:

- Go to **Home Dashboard / Plugins**
- Select **installer** from the **Select Type** drop-down filter.
- Select the **Sort Order** icon to reveal the sorting grab handles
  (vertical ellipsis).
- Drag the **Installer - Install from Web** item to the bottom of the
  list.
- Go back to **System / Install / Extensions** to view the result.

You are then ready to use one of the standard installation method.

### Upload Package File

For most extensions and most users, the procedure will be:

- Download the extension to your local machine as a zip file package.
- From the backend of your Joomla site (administration) select
  **System → Install → Extensions**.
- From the **Upload Package File** tab Select the `Browse for file` button
  and select the extension package on your local computer or drag and drop
  the file from your file manager.
- The upload and install process begins automatically,
- Some extensions may provide further instructions on installation.
- Note that modules and plugins Usuall need to be enabled before they will work.

### Install from Folder

Some extensions may be to large to use the Upload Package File method, usually
a limit on the *Maximum File Upload Size* set by your host. In this case
you can use the Install from Folder method.

- Create a temporary directory on your local hard drive and unpack the
  Extension's archive file in this temporary directory.
- Using FTP, upload the contents of this directory (including files and
  subdirectories) to the /tmp directory of the Joomla root on your server so
  that you have a path such as /tmp/acmeextension.
- In the Install Directory field specify the server directory where you
  uploaded the files and subdirectories of the package, for example
  /home/username/public_html/tmp/acmeextension.
- Select the **Check and Install** button and Joomla! will install the contents
  of the given directory.

### Install from URL

Instead of downloading a zip file to your local computer you can just use the
download URL. Joomla will fetch the zip file directly and save the download
and upload steps of the previous methods.

### Install from Web

This option allows you to install an extension directly from the Joomla!
Extensions Directory. The initial list is in order of number of reviews but
you can select by Category to quickly find a list of extensions that may suit
your needs.

## System Install Discover

As described in the Help screen, the Discover function allows you to
install extensions that are too big for some systems, especially
low-cost shared hosting environments. Something that may not be obvious
is that you may have to create folders in different places on your
hosting service, typically:

- Upload site files to siteroot/components/com_mybigcomponent
- Upload administrator files to
  siteroot/administrator/components/com_mybigcomponent
- Upload media (css and javascript) to siteroot/media/com_mybigcomponent
- Upload site language files to siteroot/language/en-GB if they are not
  in a language folder in the component site folder.
- Upload administrator language files to
  siteroot/administrator/language/en-GB if they are not in a language
  folder in the component administrator folder.

With that done, Discover should find and allow installation of the
component and it might actually work.

## System Install Languages

The default language is English GB. It cannot be removed or installed.
It may not be obvious but every page loads appropriate en-GB strings
first to ensure that language keys used by coders do not appear in the
page output. If the user selected language is not English then the user
language is loaded, overwriting the English strings. If a language has
not been fully translated the result will be a mixture of user language
and English strings. This may look strange but it is better than a
mixture of user language and coder keys.

From the list of available languages select whichever you need to install.
Some are marked with a green button to indicate they are up to date with
the current Joomla version. Others are marked with a yellow button to indicate
they are not quite up to data. Go ahead and install anyway. You may see some
English words in places that ought to be in your selected language. But they
may be rare.
