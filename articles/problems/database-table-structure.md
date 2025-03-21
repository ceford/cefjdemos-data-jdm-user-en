<!-- Filename: J4.x:Fix_%22Database_Table_Structure_NOT_Up_to_Date%22_before_Update / Display title: Database Table Structure -->

## Errors Reported

When updating Joomla! the database table structure has to be up to date
before the process can start. The *Pre-Update Check for Joomla* complains if
this is not the case.

But when you go to **System → Maintenance → Database**, there
is no entry available. This was reported in several Joomla! 4.x versions.

## What is the Cause

The problem is caused by an empty `#__schemas` table in the database. Most
likely this occurs when the Joomla! instance is not installed by the
official Joomla! installer but through a customized script that did not
fill in all required data.

## How to Fix

You can fix this by adding the missing value to the table. Using phpMyAdmin
(or another database client), go to the `#__extensions` table. Search for
name='files_joomla' and write down the extension_id (in our case *211*).

Next, you need to know the latest SQL script which is installed. Go to
`administrator/components/com_admin/sql/updates/mysql` and get the file
name with the highest version. In this example, assume
*4.0.3-2021-09-05.sql* is the file name with the highest version. Now
you have to add this in your insert query as the second value:

    INSERT INTO `#__schemas` (`extension_id`, `version_id`) VALUES
    (211, '4.0.3-2021-09-05');

or for PostgreSQL:

    INSERT INTO "#__schemas" ("extension_id", "version_id") VALUES
    (211, '4.0.3-2021-09-05');

Replace `#__` with your database prefix before running the statements.

Then from the Administrator menu go to
**System → Maintenance → Database** and fix the tables.

Now the update should work as expected.
