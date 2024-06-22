<!-- Filename: jdocmanual?manual=user&heading=system&filename=backup.md / Display title: Backup -->

## Accidents Happen!

A lot of time, effort and money go into the creation and maintenance of a
website. Pity to lose it all through a freak accident. Backup is easy for
average sites. Large or specialist sites probably need specialist advice.

## Backup Strategy

Joomla! websites consist of two parts:

* The **files** located in the Joomla root directory tree. In between updates
the files may not change much as they are mostly code related. New images and
documents may be added and perhaps template overrides.
* The **database** located somwhere else on the host server. The database
contains most of the site content and may change a lot as users add or edit
content.

Every site owner needs a strategy for site recovery in the event of a disaster.
Common advice in the Forums is to **restore the last backup**. So decide
what to back up and how often to do it.

Hosting services often take **snapshots** of customer sites and may be able to
restore a site to its condition yesterday, last week or last month. But that
might cover everything in the account, such as mail and other software packages.
Do not rely on that for Joomla site recovery.

This article describes some common **free** methods to backup Joomla websites.
You could choose to pay for backup tools and/or services but that is not
covered here.

## Akeeba Backup

If you use the Administrator menu to navigate to **System / Install Extensions
/ Install From Web** the first item in the list is *Akeeba Backup*. It is first
in the list because it has the largest number of positive reviews. Needless to
say that it has a very long history and an impeccable reputation. There is a
free version and a paid for verion with some extra features. That is a common
business model for Extension developers. Do not be wary! The free version is
easy to use, has no distractions and suffices for most sites. What it does:

* Akeeba Backup analyses your installation to determine the optimum settings to
create a backup file.
* It makes a composite backup file containing all the website files and the
database content.
* It stores time-stamped backups to manage, download or delete as appropriate.
* The download is a .jpa file. It recommends use of FTP to do the download.
* There is a separate Akeeba Kickstart application to unpack the .jpa file.
This is all described in the Akeeba Manage Backups page.
* After unpacking, the site is installed with an Akeeba installer in a sequence
similar to a Joomla install.
* The installer changes the configuration for restoring to a different location
and prompts for the new database details.

The only problem that is likely to occur is that the backup file may be very
large and you may exceed your file space quota if you allow backups to
accumulate.

Try it! It costs nothing and takes minutes rather than hours.

## Host Tools

Most hosting services provide backup tools. Example:

### cPanel

On the **Tools** page, the *Files* item has a *Backup* link. Tha **Backup**
page has three options:

*  **Full Backup:** A full backup creates an archive of all of your website’s
files and configuration. You can use this file to move your account to another
server or to keep a local copy of your files.
* **Partial Backup**
    - Download a Home Directory Backup
    - Download a Database Backup (with a list of dtabases)

There are also options to **Restore** each of these backup types. Options to
produce automatic backups may be available too.

Individual folders can be compressed in various formats suitable for download
using the cPanel File Manager. A database can be exported using phpMyAdmin.
Neither of these methods is covered here.

## Local Tools

There are occasions when you may need to backup a site locally on a laptop or
office desktop computer. For example, you may want to copy a site to/from a
hosting service to/from your local computer. If you have a local Joomla
installation you can use Akeeba Backup as described above. Otherwise, you
can backup the database and Joomla files separately.

### mysqldump

If you are using MySQL you are likely to have the *mysqldump* command line
tool available. Try this command:

```bash
/usr/local/mysql/bin/mysqldump -u root -p dbname > ~/tmp/dbname-dump.sql
```
where `root` is a user who has access to the database and `dbname` is the name
of the database you wish to export. You may be prompted to enter the password.

You could pipe the output to a zip or gzip command too:
```bash
/usr/local/mysql/bin/mysqldump -u root -p dbname | gzip > ~/tmp/dbname-dump.sql.gz
```

### phpMySQL

To do the same job with your local installation of phpMyAdmin, open it and
select the database you wish to export. Select the **Export** button at the
top of the screen. By default, the *Quick* export uses SQL as the output
format. Select the **Export** button to try that. You will be prompted to
nominate an output file.

If you select the *Custom* option allows you to select an Output Compression
optione, either none, zipped or gzipped. Try a compressed export and select
the **Export** button.

You need to **check** the exported database. Create a new database, perhaps
`animporttest` so that it is near the top of your list of databases. With the
new empty database selected use th **Import** button at the top of the screen.
In the import form **Browse** to find the file you exported and then select the
**Import** button.

It was worth the **check**. The gzip export only exported three tables. The
zip export worked fine. That was evident in the sizes of the exported file. The
zip file was 4Mb but the gzip was only 75Kb. Must be a bug somewhere!

### Zip and Gzip

These command line tools are fairly ubiquitous and are often used from within
graphical interfaces. For example, in the Finder on Mac I can select a
directory containing a Joomla site, right click and select **Compress**. It
takes a few seconds to make a zip archive and does not affect the original.

## Restoring a Backup

Common advice from the Joomla Forums:

* Do not restore a backup on top of a faulty site.
* Empty your database by deleting all tables or create a new database and
assign a database user for it.
* Delete all directories and files within your Joomla root directory.

## Akeeba Quickstart

If you have used Akeeba Backup then use Akeeba Quickstart to restore your
backup.
* Consult the [Video Tutorial](http://akee.ba/abrestoreanywhere "").
* Download Akeeba Quickstart (PDF 94Kb)
free of charge.
* Check that the restored site works properly!

Akeeba Quickstart restores both the database and Joomla files. Other methods
restore the database and Joomla files separately.

## Restore the Database

If you have a database backup it is best to use system tools to restore it.
*phpMyAdmin* can install moderately sized databases but it might run out of
time or memory on large databases.

If you are using cPanel on a hosting service you can import a database from
the *Backup / Restore* page. That is not described here.

If you have command line access, either on a hosting service or on you local
laptop or desktop computer, you can use the `mysql` command line to do the
import. Upload the database archive to a temporary location outside your web
tree and expand it so you have a filename ending in `.sql`. Then use the
following command:
```
mysql -u dbusername -p -D dbname < db_dump_file.sql
```
Replace `dbusername`, `dbname` and `db_dumo_file.sql` with the reak values for
your site. You may be prompted for a database username password. It may take a
whhile but it should go to completion.

## Restore the Files

This is a simple matter of expanding the compressed file from your last backup.
Except that it is sometimes not so simple. Depending on your operating system
and chosen method, the archived directories and files might all appear in the
current directory or a new directory or you may prompted to nominate a
destination directory. Until you know what your system does it may be best to
put the archive in an empty directory, expand it there and then move the
containing directory to where it needs to be.

Some users prefer to use SFTP to upload files to a hosting service from the
archive files extracted locally. There are thousands of files so this is quite
time consuming.

In the root of your site there is a file named `configuration.php`. It contains
the database name and access credentials. Make sure they are correct for your
restored site. The file has access permissions set to 444. That needs to be
changed to 644 so that you can save any editing needed.

All being well your restored site should work and be in the state it was in
when the backup was taken.

## Copying a Site

There are several good reasons to copy an entire website from one server to
another. For example, the Forum experts often reccommend that users create a
a local version of a site on a laptop or desktop computer for testing purposes
such as trying out new extensions or designs. Sometimes an individual decides
to move to a new hosting service for cost or performance reasons.

Whatever the reason, the process is relatively simple: take a backup in the
original site and restore it on the destination site. There are some issues
to watch out for:

* Make sure the destination host meets the minimum Joomla Technical
Requirements. That usually means Server, PHP and Database versions
* After installation you may find some essential modules have not been enabled.
Most hosting services will fix such problems on request.

