<!-- Filename: J4.x:Joomla_CLI_Installation / Display title: Joomla CLI Installation -->

## Introduction

The Joomla CMS is usually installed via a web browser interface. However,
experienced users may wish to install Joomla using commands in a terminal
interface. This allows rapid deployment of multiple Joomla instances.

## System Requirements

Joomla requires PHP, a database and a web server. For the latest
information about the supported software and the minimum and recommended
versions, please visit the
<a href="https://manual.joomla.org/docs/next/get-started/technical-requirements/"
rel="noreferrer noopener">Technical Requirements</a> page.

The installation can be performed in two different ways:

1.  Manual installation
2.  Script-driven automatic installation

## Manual installation

Manual installation offers good control during the installation process. Each
step is visible in the terminal and can be aborted with `Ctrl+C` in case of
an incorrect entry.

### Steps to be accomplished

1.  Upload the installation package zip or tar file to the web server.
2.  Uncompress the zip or tar file.
3.  Rename the uncompressed folder and move it to an appropriate place in
    the web server document root.
4.  Change to the folder containing the Joomla code and run the following
    command:<br>
    `php installation/joomla.php install`
5.  You will be prompted for the parameters required for installation, as in
    the following example transcript:
```bash
php installation/joomla.php install

Install Joomla
==============

Checking system requirements...OK
Collecting configuration...

 Enter the name of your Joomla site:
 > J51
 Enter the real name of your Super User:
 > John Doe
 Set the username for your Super User account:
 > johndoe
 Set the password for your Super User account:
 >
 Enter the email address of the website Super User:
 > johndoe@example.com
 Database type. Supported: mysql, mysqli, pgsql [mysqli]:
 >
 Database host [localhost]:
 >
 Database username:
 > j4
 Database password:
 >
 Database name [joomla_db]:
 > j51
 Prefix for the database tables [u5dke_]:
 >
 Encryption for the database connection. Values: 0=None, 1=One way, 2=Two way [0]:
 >
 Relative or absolute path to the public folder []:
 >
OK
Validating DB connection...OK
Creating and populating the database...OK
Writing configuration.php and additional setup ...OK
Deleting /installation folder...OK
 [OK] Joomla has been installed
```

Once the script is successfully completed the new website can be accessed
via your web browser.

### Notes

*   Pay careful attention to your input. It is not possible to step back in
    the script. If the input is incorrect, the script must be aborted.
*   The name of your Joomla site appears in the Adiministrator Title bar so
    keep it short and distinctive. It can be changed later.
*   The real name of your Super User can be changed later.
*   The username for your Super User account should avoid a name similar to
    *admin*. It is potentially insecure as it can be guessed easily by a hacker.
*   The User password must be 12 characters.
*   The Database type default is *mysqli*. Supported database types are MySQL
    (mysql) and PostgreSQL (pgsql) databases and compatible types such as
    MariaDB.
*   The Database host is almost always `localhost`. An IP address
    or a host name should be entered here only if the responsible
    database server is installed on another host. However, the terminal
    user has to have write permissions on the selected host. You will
    get this information from your internet provider (ISP).
*   The Database username is usually different from the name of the Super User.
*   The Database password for the Joomla database is almost always different
    from the Super User password.
*   The Database name defaults to `joomla_db` but other names are often used.
*   The Prefix for the database tables is set to a random selection of five
    characters. The value is used to separate Joomla tables from other tables
    contained in the database if it is used also by other applications.
*   The Encryption setting for the database connection is rarely used. Unless
    advised otherwise by your ISP leave this value at the default [0].

## Script-driven automatic installation

The installation of Joomla is controlled by a *joomla.php* file located in
the *installation* subfolder after unpacking the Joomla package file. Any
programming language that allows calling and executing PHP files allows you
to create a script that automates the necessary preparations and the actual
installation using custom variables. A list of parameters can be obtained
with the following command:
```bash
php installation/joomla.php help install
```
Here is an example shell script named jinstall.sh placed in the Joomla root
folder created for a simple Joomla installation:
```
#!/bin/bash

php installation/joomla.php install \
--site-name=SITE-NAME \
--admin-user=ADMIN-USER \
--admin-username=ADMIN-USERNAME \
--admin-password=ADMIN-PASSWORD \
--admin-email=johndoe@example.com \
--db-type=mysqli \
--db-host=localhost \
--db-user=j51 \
--db-pass=Garbage1n0ut \
--db-name=j51 \
--db-prefix=xyz12_ \
--db-encryption=0 \
--public-folder=j51
```
With its permissions set to 700 it is a simple matter to call the script
from the command line with `./jinstall.sh` and Joomla is installed literally
in a flash. The script could have been edited to change placeholder values or
they could be changed later after Administrator login.

If you use this approach remember to delete your jinstall.sh script or move
it out of your web tree for use elsewhere later. The installation folder is
removed at the end of the installation process. So running the jinstall.sh
script a second time will not work.