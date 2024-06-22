<!-- Filename: How_do_you_block_directory_scans_using_htaccess%3F / Display title: How to block directory listing -->

## Background

By default, on an Apache web server, a directory that does not contain a
configuration defined index file (index.html or index.php) will display a list
of all files and sub-directories in the directory. This can be useful on a
personal test server but is a severe security risk on a live production server.

In the past it was common practice to include an empty index.html file in all
Joomla directories to prevent this problem appearing on badly configured
servers. This is no longer the case. Proper server configuration is expected,
either in the server configuration files or in individual .htaccess files. The
former is preferred as it is applied to all websites on the server.

However, sites in a shared hosting environment may expect each site to modify
the server configuration using .htaccess files. The server must be set to
AllowOverride Options" or "AllowOverride All" to enable oveerides in .htaccess.

## Using .htaccess

The htaccess.txt file supplied with Joomla can be used on Apache servers by
renaming or copying it to .htaccess. It contains many settings to counter
hacker attacks on Joomla sites. Amongst others you will see the following
settings to prevent directory listings:

```
Options -Indexes

## No directory listings
<IfModule mod_autoindex.c>
	IndexIgnore *
</IfModule>
```

## Test your site

One way to test your site is enter the URL of your images folder in the
browser URL bar: `https://yourdomain.com/images/`. As the images folder does
not normally contain an index.html or index.php file you should see a
completely empty page. If you see a list of all files and folders then you are
not preventing directory scans for any part of your site. Fix it!
