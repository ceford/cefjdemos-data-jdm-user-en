<!-- Filename: J4.x:CLI_Database_Exporter_Importer / Display title: CLI Database Export Import -->

## Introduction

Before updating Joomla! or  installing a third party extension, it is strongly 
recommended that you back up your site. The Joomla! Command line interface
(CLI)  provides commands for exporting (backing up) and importing (restoring) 
your Joomla! database. Note that it doesn't backup your filesystem which should 
be done separately

## Requirements

To use these commands, you need a terminal access to the host on which the site 
is installed. This may be a problem on shared hosting! You also need basic 
knowledge of linux shell commands such as ls and cd. If all of this is 
unfamiliar you should probably use Akeeba Backup, the most popular backup and 
restore extension and free for basic use.

## Backup Temporary Storage Location

Take care when choosing a storage location for a backup. It should be within
your personal file space but outside your web tree. The objective is to create
a backup file that you can download to your local computer or another safe
place after which you can delete the backup file to save space. Also, take
care not to use the system /tmp folder which can be ready by any user. The best
location is your personal tmp folder. The folder tree layout:
```
|-/home/username/tmp - your personal tmp folder
|-/home/username/public_html - your Joomla root folder
```

## Instructions

Log into your host and go to the root folder of your site.
```
cd /home/username/public_html
```

- List all available available CLI commands:
```sh
  php cli/joomla.php list
```
- Export the database to the account tmp folder:
```sh
  php cli/joomla.php database:export --folder /home/username/tmp/mydbname
```
- Import the database from folder:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/mydbname
```

You can also:

- Export the database as a .zip file:
```sh
php cli/joomla.php database:export --zip --folder /home/username/tmp/mydbname
```
- Export a table:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --folder /home/username/tmp/mydbname
```
- Export a table as a .zip file:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --zip --folder /home/username/tmp/mydbname
```
- Import a table:
```sh
php cli/joomla.php database:import --table xxxxx_action_log_config --folder /home/username/tmp/mydbname
```
- If you need help:
```sh
php cli/joomla.php database:export --help
php cli/joomla.php database:import --help
```

## Backup

To make a full backup of folders, files and the database execute these commands:

1.  Archive your Joomla root directory:
```sh
tar --exclude='/home/username/public_html/tmp' -zcvf /home/username/tmp/joomla_bak.tgz /home/username/public_html > /home/username/tmp/joomla_bak.log
```
2.  Export all the Joomla database, from the Joomla root folder:
```sh
php cli/joomla.php database:export --folder /home/username/tmp/db_bak
```

## Restore

And to restore it, first make sure the database and database user exist. Then
execute these commands:

1.  Extract the archive:
```sh
tar -xvf /home/username/tmp/joomla_bak.tgz --directory /home/username/public_html
```
2. Make sure you are in the root of your site:
```sh
cd /home/username/public_html
```
2.  Import the Joomla database:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/db_bak
```

## Notes

In the tar command options -zcvf and -xvf the v stands for verbose - a list of
processed files scroll swiftly down the terminal screen. Leave out the v to
not see the list,