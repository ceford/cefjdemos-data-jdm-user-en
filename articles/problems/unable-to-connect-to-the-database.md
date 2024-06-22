<!-- Filename: Unable_to_connect_to_the_database / Display title: Database Connection -->

## Unable to Connect Error

If you receive an "**Unable to connect to the database**" error during
installtion, verify that you have entered your MySQL/MariaDB database details
correctly. The **installation** script will not allow you to continue unless
the details are correct.

Note that you are not expected to create a database user and password during
installation. They must be created first.

If the failure occurs after moving your site to another host, check the
following items of your *configuration.php* file. The normal database
settings are the following:

	public $dbtype = 'mysqli';
	public $host = 'localhost';
	public $user = 'yourdbuser';
	public $password = 'yourdbpassword';
	public $db = 'yourdbname';
	public $dbprefix = 't6q6i_';

If the failure occurs in a site that has been working there are a number of
possible reasons, sometimes temporary and sometimes accidental.

## The Most Common Faults

1.  Sometimes you will see this message if MySQL/MariaDB has stopped
    running on your server. Your server administrator may temporarily
    shut down MySQL/MariaDB to perform maintenance. In such
    circumstances, your site will likely return shortly.
2.  Your database user has been deleted. If this is the case, you will
    need to recreate your database user with the same username and
    password that existed when you first installed Joomla. Use your
    domain control panel to administer this or contact your server
    administrator.
3.  Your database username or password has changed.
