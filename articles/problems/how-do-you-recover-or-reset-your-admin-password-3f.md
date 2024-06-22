<!-- Filename: How_do_you_recover_or_reset_your_admin_password%3F / Display title: Admin Password Recovery -->

## Lost Super User Password

Normally a Super User can add, edit and delete users and passwords from the
Users list. In some situations this may not be possible. For example, the
person who knew a Super User password is no longer available. Or maybe the
Super User has forgotten the password that was used.

In such cases there are two methods available to allow a site Administrator
to login as a Super User.

## Method 1: Edit the configuration.php File

If you have access to the `configuration.php` file for the Joomla installation
on your server, then you can reset a Super User password or create a new Super
User if you can login as a Manager or Administrator.

You need to open the `configuration.php` file in a text editor. First change
its file permissions to 644. Your site management tools, such as cPanel or
Plesk (there are others), usually allow you to do this online. If not, you
may need to use FTP to download the file, change it locally and upload it again.

Add this line at the foot of the file but before the closing curly brace:
```
    public $root_user='myname';
```
where **myname** is a username with *Manager* or *Administrator* group
access that you know the password for. A username that is in the *Author*,
*Editor* or *Publisher* groups will not work because those groups do not have
backend access.

This user will now be a temporary Super User.

Login to the back end and change the password of the Super User you don't have
the password for or create a new Super User account. If you create a new user
you may want to block or delete the old user depending on your circumstances.

When finished, make sure to use the *Select here to try to do it
automatically* link that appears in the alert box to remove the line
that was added to the configuration.php file. If using the link was not
successful, then go back and delete the added line from your
configuration.php file using a text editor.

If you have no users who know their passwords you may need to make a change in
your database.

## Method 2: Edit the Database

If the methods above did not work, you have two other options, both of
which require working with the MySQL database directly.

### Change a Password in the Database

The simplest option is to change the Super User password in the database to
a known value. This requires that you have access to the MySQL database
using phpMyAdmin or another client. These instructions show how to change a
password to the word **secret**.

This method will work only if the selected user is in the *Manager* or
*Administrator* groups.

**Make sure you change the Super User password once you regain access!**

1.  Open phpMyAdmin and select the database for the Joomla! site. This will
    show the database tables on the left side of the screen.
2.  Find and select the *#__users* table where *#_* is the table prefix for
    your site.
3.  In the *Browse* view find the user whose password you want to change and
    select the Edit icon for this row.
    - if the list is long select the SQL button at the top and use this query:<br>
    `SELECT * FROM `xxxxx_users` WHERE `username` = 'username'`<br>
    where you use your database prefix to replace `xxxxx` and the username
    you need to find in place of `username`.
4.  In the edit form change the password to<br>
    `d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199`<br>
    and select the *Go* button at the bottom of the form. phpMyAdmin should
    display the message *Affected rows: 1*. At this point, the password should
    be **secret**.
5.  Log in with this user and password and change the password of this
    user to a secure value. Check all of the users to make sure they are
    legitimate. If you have been hacked, you may want to change all of the
    passwords on the site.

### Add a new Super User

If changing the password does not work, or you are not sure which user is a
member of the Super User group, you can use this method to create a new
Super User.
1.  Open phpMyAdmin and select the database for the Joomla! site.
2.  Select the *SQL* button in the toolbar to run an SQL query on the
    selected database. This will display a field called "Run SQL
    query/queries on database xxxxx".
3.  Delete any text in this field and copy and paste the following query.
    Remember to replace `xxxxx` with your own database prefix.
    ```
    INSERT INTO `xxxxx_users`
       (`name`, `username`, `password`, `params`, `registerDate`, `lastvisitDate`, `lastResetTime`)
    VALUES ('Administrator2', 'admin2',
        'd2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199', '', NOW(), NOW(), NOW());
    INSERT INTO `xxxxx_user_usergroup_map` (`user_id`,`group_id`)
    VALUES (LAST_INSERT_ID(),'8');
    ```
    Select the *Go* button to execute the query and add the new Super User to
    the table.

At this point, you should be able to log into the back end of Joomla!
with username *admin2* and password *secret*.

After logging in, go to the User list and change the password to a new secure
value and add a valid email address to the account.

If there is a chance you have been *hacked*, be sure to check that all users
are legitimate, especially any members of the Super User group.

## Alternative Temporary Passwords

**Warning:** The password values shown on this page are public knowledge and
are only for recovery. To avoid being hacked be sure you change a temporary
password to a secure value after logging in.

    password = "this is the MD5 and salted hashed password"
    ------------------------------------------------------
    admin  = 433903e0a9d6a712e00251e44d29bf87:UJ0b9J5fufL3FKfCc0TLsYJBh2PFULvT
    secret = d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199
    OU812  = 5e3128b27a2c1f8eb53689f511c4ca9e:J584KAEv9d8VKwRGhb8ve7GdKoG7isMm
