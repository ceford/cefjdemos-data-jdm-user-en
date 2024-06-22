<!-- Filename: Installing_Joomla!_using_BitNami_Joomla!_stack / Display title: Bitnami Installation -->

## Preface

**NOTE:** BitNami Joomla! stack no longer exists as a standalone installer.
Instead, it delivers as: 1) A cloud based instance, 2) In a container, either
Kubernetes or Docker or 3) A virtual machine. The virtual machine will run on
your operating system in a hypervisor such as Virtual Box or VMware Player.
It still comes with all the required dependences as in the standalone installer.

Option 1 below no longer applies. Also, in Option 2, BitNami Lamp Stack further
down, delivers in the cloud or virtual machine. In any case, Bitnami makes
having a performing local installation of Joomla! easy and complete.

You can download the latest version of the Bitnami package for Joomla! for
Windows, Linux and Mac at <a href="http://bitnami.org/stack/joomla"
rel="nofollow noreferrer noopener">http://bitnami.org/stack/joomla</a>.

**Revision Needed!**

BitNami Joomla! Stack is an all-in-one installer that makes it easy to
install Joomla on your computer. It is free, easy to use and
self-contained. That means that it bundles and automatically configures
every piece of software (dependency) necessary to run Joomla for
development or production purposes, including Apache HTTP Server, MySQL
and PHP.

## Option 1: Joomla! stack (Recommended)

This method assumes you already have a
(**W**indows/**L**inux/**M**ac)...**AMP**(Apache HTTP Server, MySQL, &
PHP) environment installed.

### Installing Joomla! Stack

Regardless of which operating system you are running (Windows / Linux /
Mac), the install process is the same.

Download the latest version of Joomla! Stack from the
<a href="http://bitnami.org/stack/joomla"
rel="nofollow noreferrer noopener">BitNami website</a>.

Find the installer you just downloaded (the filename will be similar to
bitnami-joomla-VERSION-linux-installer.run. Double click on the icon to
launch the installer.

If you are using Linux you will have to give executable permissions to
the file first, using this command:

chmod +x /path/to/bitnami-joomla-VERSION-linux-installer.run

<img src="https://docs.joomla.org/images/a/a0/Joomla_welcome2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack setup" />

Click "Next".


<img src="https://docs.joomla.org/images/5/5f/Joomla_components2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack components" />

Select the components you want to install. If you are not sure, leave
the default components checked. Click "Next" when you are done.


<img src="https://docs.joomla.org/images/0/0a/Joomla_directory2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack installation directory" />

Now it will ask where do you want to install the program. Provide the
location where you want to install the BitNami Joomla! stack and click
"Next" when you are done.


<img src="https://docs.joomla.org/images/3/3c/Joomla_userdata2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack sdmin account" />

The user and password you provide here will be used to create the admin
account in Joomla! Click "Next" when you are done.


<img src="https://docs.joomla.org/images/8/8b/Joomla_sitename2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack sitename" />

Type in the name you want to use for your Joomla site, and click "Next".


<img src="https://docs.joomla.org/images/d/dd/JoomlaReadytoinstall2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack Ready to install2" />

The installer allows you to configure an email account so Joomla! can
send notifications via email . Click "Next".

<img src="https://docs.joomla.org/images/9/9d/JoomlaCopyingfiles2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack Copying files" />

Wait a minute while the installer copies the files and configures your
Joomla! installation.


<img src="https://docs.joomla.org/images/e/ea/Joomlafinalscreen2.png"
decoding="async" data-file-width="614" data-file-height="538"
width="614" height="538" alt="Joomla Bitnami lampstack final screen" />

Joomla! is now set up and ready to be used. Click "Finish" to launch the
application.

<img src="https://docs.joomla.org/images/8/8d/JoomlaManager.png"
decoding="async" data-file-width="784" data-file-height="586"
width="784" height="586" alt="Joomla Bitnami lampstack Manage servers" />

Using the manager tool is easy to start/stop the Apache and MySQL
servers.

<img
src="https://docs.joomla.org/images/7/73/Joomlaapplicationscreen2.png"
decoding="async" data-file-width="982" data-file-height="729"
width="982" height="729" alt="Joomla application screen" />

You can manage the Joomla! database with phpMyAdmin easily.

<img src="https://docs.joomla.org/images/f/f3/JoomlaphpMyAdmin.png"
decoding="async" data-file-width="982" data-file-height="751"
width="982" height="751" alt="phpMyAdmin screen" />

## Option 2: BitNami LAMPStack and Joomla!

### What is BitNami LAMPStack?

BitNami LAMPStack is a free, easy to install package that bundles every
piece of software (dependency) necessary to setup a LAMP (Apache, MySQL
and PHP for Linux) environment up and running for development or
production purposes. It is self-contained, it makes no modifications to
your system and can be uninstalled easily. You can download the latest
version of BitNami LAMPStack for Linux at
<a href="http://bitnami.org/stack/lampstack"
rel="nofollow noreferrer noopener">http://bitnami.org/stack/lampstack</a>.
A <a href="http://bitnami.org/stack/wampstack"
rel="nofollow noreferrer noopener">Windows version</a>
and a <a href="http://bitnami.org/stack/mampstack"
rel="nofollow noreferrer noopener">OS X version</a> are also available.

Regardless of which operating system you are running (Windows / Linux /
Mac), the install process is the same.

### Installing BitNami LAMPStack

Find the installer you just downloaded from the BitNami website (the
filename will be similar to
bitnami-lampstack-VERSION-linux-installer.run). Double click the icon to
launch the installer.

<img src="https://docs.joomla.org/images/1/14/Lampstack_welcome.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bitnami lampstack welcome" />

Click "Forward".


<img src="https://docs.joomla.org/images/7/78/Lampstack_directory.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bitnami lampstack directory" />

Now it will ask where you want to install the program. Select the
location on your machine and click "Forward" when you are done.


<img src="https://docs.joomla.org/images/2/22/Lampstack_passwd.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bitnami lampstack password" />

Type your MySQL root password. This will be the password for the "root"
user for the database.


<img
src="https://docs.joomla.org/images/7/72/LampstackReadytoinstall.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bitnami lampstack Ready to install" />

The installer is now ready to begin the installation process. Click
"Forward".


<img src="https://docs.joomla.org/images/1/19/LampstackCopyingfiles.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bitnami lampstack Copying files" />

Wait a minute while the installer copies the files and configures your
LAMPStack installation.


<img src="https://docs.joomla.org/images/b/bc/Lampstackfinalscreen.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bitnami lampstack final screen" />

BitNami LAMPStack is now set up and ready to be used. Click "Finish" to
launch the application.

### Installing Joomla! manually

Follow the instructions outlined in the article  Installing
Joomla.
