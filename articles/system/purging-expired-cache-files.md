<!-- Filename: Purging_expired_cache_files / Display title: Purge Expired Cache -->

## Cache Files

Cache files are temporary files that are created to improve the
performance of your site. You need to ensure that cache files that have
expired, so they are no longer needed, are removed from the system.
Otherwise you will eventually run out of disk space.

Expired cache files can be purged from the Administrator interface or thr
Command Line interface (CLI).

## Purge - Administrator Method

From the *Home Dashboard*
* Select the **Cache** option in the *System* panel.
* In the *Maintenace: Clear Cache* page select the **Clear Expired Cache**
button in the Toolbar.

## Purge - Command Line Method

Open a terminal window and cd to the cli directory in the root of your site.
If you do not know what CLI commands are available issue the following command:
```bash
php joomla.php
```
You will see a list of commands available. The `cache` command is:
```bash
php joomla.php cache:clean
```
There should be a green confirmation message or perhaps a maroon error message.

## Automatically Purging Expired Cache Files

You can automatically purge expired cache files using a cron job. Hosting
services make this easy by providing a form to select how frequently a job runs
and the command to use. So you might choose set the cron to run a 05:00 every
day with the following command:
```
 /usr/local/bin/ea-php82 /home/username/public_html/cli/joomla.php cache:clean
 ```
Most *cron* job managers allow you to enter an email address to which the cron
output will be sent. If you do not want a message sent append ` > /dev/null 2>&1`
to the command.

The PHP version used on the command line is often different from that used for
delivery of a website. It might be incompatible with Joomla. So use the full
path to the version of PHP you wish to use rather than `php` alone.
