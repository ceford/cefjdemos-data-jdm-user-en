<!-- Filename: No_original_yet / Display title: Local Hosting on Linux -->

This article covers hosting Joomla on a personal Linux based computer for
testing and development purposes. The Linux versions covered are from the
Debian-Ubuntu family, and specifically Linux Mint. Other distributions are
similar but have different command syntax and file locations.

You need to install a set of software packages often referred to as LAMP stack.
The letters refer to Linux, Apache, MySQL and PHP. You can install software
using either the Graphical User Interface (GUI) or the command line in a
Terminal window. They are different ways of using the Synaptic Package
Manager.

## Install Apache with the GUI

From the system Menu, marked with the LM logo, select Administration / Synaptic
Package Manager. You will be prompted for your password. Enter your login
password to open the GUI. At the top right is a `Search` button. Select it and
enter **apache** and select `Search`. Select the `apache2` checkbox and in
the pop-up label select `Mark for Installation`. Another pop-box will show
a list of additional packages required to support apache. Select `Mark`:

![synaptic package manager](../../../en/images/hosting/synaptic-package-manager-gui.png "Synaptic Package Manager GUI")

Select the `Apply` button in the top Toolbar and the `Apply` button in the
Summary dialog. Apache will be installed and configured, the process ending
with a **Changes Applied dialog**. Select `Close`.

You can confirm that Apache is installed and working by opening your
browser, Firefox by default in a new Linux Mint install, and entering
**localhost** in the URL bar. You should see the Ubuntu Apache2 Default Page:

![apache default page](../../../en/images/hosting/apache-default-page.png "Apache Default Page")

The page contains some useful information about file locations that may
not be so readily available later so you might like to print this page to
paper or a pdf file.

## Install PHP with the CLI

It is probably best to install PHP using the command line. One reason for this
is that, at the time of writing, the Synaptic Package Manager only offers PHP8.1
although PHP8.2 has been available for some time and can be installed from a
third party repository. There is a good description of the procedure in this
tutorial with Quickstart
and Detailed sections.

First close your Synaptic Package Manager GUI and then open a Terminal window
and enter the following commands one at a time:

```bash
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php8.2 php8.2-cli php8.2-{bz2,curl,mbstring,intl}
sudo apt install php8.2-fpm
sudo a2enconf php8.2-fpm
sudo systemctl reload apache2
```
In your browser, check that the localhost default page is still working.

## Install MySQL or MariaDb

You can search the web for information on each of these database packages.
MySQL is the traditional choice but was taken over by Oracle and is now less
popular. MariaDB is a drop-in Open Source replacement with additional features.
Both work with Joomla! 5 but it is not easy to change from one to the other.
Tables have to be exported and imported. Joomla! 5 requires specific minimum
versions which Linux Mint offers via the Synaptic Package Manager.

Open the Synaptic Package Manager GUI and search for either mysql-server or
mariadb-server. Select the checkbox for the item ending in -server. Select
`Mark for Installation` and them `Apply` in the top Toolbar. You can open the
Details panel to see what is happening during the installation. Select `Close`
when done.

You can test to see whether your database is working by entering `mysql` in
the command line. This is the the same for both MySQL and MariaDB. You should
see an `Access denied` error message, which is fine as it indicates your
database installation is actually working.

## Install phpMyAdmin

phpMyAdmin is a GUI database management tool that you will need to create and
manage your databases. In the Synaptic Package Manager GUI search for
**phpmyadmin**. Select its checkbox and `Mark for Installation`. After download
there is a prompt to select the `Webserver to reconfigure automatically`.
Select the chckbox for `apache2` and then the `Next` button. At the next
configuration screen leave the `Configure database...` checkbox checked and
select `Next`.

Select an application password for the user phpmyadmin. Test: in your bowser
enter localhost/phpmyadmin in the URL bar. You should see the phpMyAdmin login
screen. With the username phpmyadmin and the password you entered during
installation you will be able to login. But you will not be able to create
any databases! To solve the problem you need to edit the configuration file
as root in the Terminal window:

```bash
sudo nano /etc/phpmyadmin/config.inc.php
```
Find the two lines containing // $cfg['Servers'][$i]['AllowNoPassword'] = TRUE;
and remove the leading slashes to uncomment them. Both of them!

Then login to mysql from the command line and create a new user and grant
that user all privileges:
```bash
sudo mysql
CREATE USER 'admin'@'localhost' IDENTIFIED BY '';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;
exit
```
Then go back to phpMyAdmin and try to login with username **admin** and no
password. You should see all databases and be able to create new databases.

## Index File Priority

The default location for web pages on Ubuntu/Linux Mint is /var/www/html. If
you list the contents of that directory you will see it contains index.html
containing the content of the Ubuntu Apache2 Default Page. Create a file named
index.php in that directory with the following content:

```php
<?php echo phpinfo();
```
Reload localhost. There is no change! Enter **localhost/index.php** in the
URL bar and you will see a page containing PHP Version information. This
behaviour is controlled by the default Apache configuration which it can be
changed by enabling the Apache `dir` module and editing its configuration:

```bash
sudo a2enmod dir
sudo nano /etc/apache2/mods-enabled/dir.conf
```

Move index.php to the front of the list. Then restart Apache:

```bash
sudo systemctl restart apache2
```

This time using **localhost** alone in the URL bar you should see the content
of the index.php file, a PHP Information page.

## Virtual Hosts

In a default Linux installation the system files are in the root folder (/)
and user data files are in the home folder (/home/myusername). This is a
potential because the default Apache user, www-data, may not have appropriate
permissions to create files in user file space. The best solution is to create
Virtual Hosts.

First, a module is needed that allows Apache to switch its user and group to
suit each user:

```bash
sudo apt-get install libapache2-mpm-itk
sudo a2enmod mpm_itk
```

Next, make a copy of the default site configuration file and edit it:

```bash
cd /etc/apach2/sites-available
sudo cp 000-default.conf username.localhost.conf
sudo nano username.localhost.conf
```

The default site configuration file contains comments to explain its
content. They are left out in the illustration below. Uncomment the
ServerName line and change all instance of `username` to your own
username.

```xml
<VirtualHost *:80>
        ServerName username.localhost
        ServerAdmin webmaster@localhost
        DocumentRoot /home/username/public_html
        <IfModule mpm_itk_module>
                AssignUserId username username
        </IfModule>
        <Directory /home/username/public_html/ >
                Options Indexes FollowSymLinks
                AllowOverride None
                Require all granted
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Enable the new site and restart Apache:

```bash
sudo a2ensite username.localhost
sudo systemctl reload apache
```

Make an entry in the /etc/hosts file to add an entry for the new virtual host.
Otherwise your browser will be looking for it on the internet.

```bash
sudo nano /etc/hosts
```
When done it will look something like this:

```bash
127.0.0.1       localhost
127.0.0.1       username.localhost
127.0.1.1       hostname

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```
**Hostname:** This is the name you gave to your computer when you installed
Linux. You will need it shortly. You can change it if you wish - but best to
read up on that and do it first.

All being well, with a URL of the form username.localhost you will see a
directory listing of your public_html directory. Public display of directory
listings is considered bad practice, a security risk, and usually disallowed by
another Apache configuration setting. However, for a personal site on a
personal computer used for development and testing it is very useful. Many
different sites may be set up in different sub-directories. For example,
Joomla 4 and Joomla 5 sites, Bulletin Boards, Wikis and so on. When you have
a lot of test sites it is difficult to remember all of the subdirectory names!

## Home Network Access

If you have another computer on your home network you would probably like to
access your Linux site from there too. To make that work you need another
virtual host. Copy and edit the one just made:

```bash
cd /etc/apache2/sites-available
sudo cp username.localhost.conf username.conf
sudo nano username.conf
```
Change the ServerName from username.localhost to username.hostname and
then enable the new virtual site and restart Apache.

```bash
sudo a2ensite username
sudo apachectl restart
```
Go to your other computer on the home network and edit its personal hosts file.
For example, on a Mac edit /private/etc/hosts and add the following line
at the bottom:

```bash
192.168.178.20 username.hostname www.username.hostname
```
Where 192.168.178.20 is the IP address of your Linux computer.

Now on your second computer you should be able to access the web server on
you Linux computer by entering username.hostname in the URL bar of
your browser.

## Partition Notes

Software installed using the Synaptic Package Manager is usually in the Linux
root directory (/). User data is located in the home directory (/home). In a
simple  installation these directories are in the same physical disk
partition.

In a more complex installation, perhaps with the option to boot different
operating systems (Windows or Linux) or different versions of the same
operating system, the root and user data are often in separate partitions. This
allows access to the same user data from each operating system.

There is a snag: a Joomla site located in a /home/username directory needs
database data that is usually in the root directory, specifically in
/var/lib/mysql. You can move the MySQL/MariaDB data directory
to a location available to both operating systems, either in the /home
partition or in a separate partition. This tutorial describes how to
Change the MySQL Data Directory
in Ubuntu and Debian Linux. That needs to be done for each operating system
but is not covered here.
