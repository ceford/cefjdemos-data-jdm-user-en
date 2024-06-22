<!-- Filename: J4.x:Hosting_Setup / Display title: Hosting Setup -->

## Introduction

This page provides some guidance for anyone completely new to hosting
technology. You can set up a website on your own laptop or desktop
computer. This is known as local hosting and is a good way to experiment
with new features and is completely free. To make your website content
available to the rest of the world you will need an account on a hosting
service and for that you will have to pay.

## Supporting Software

Joomla! is an application that depends on three items of supporting software:
the PHP scripting language, a database (one of MySQL, MariaDB or PostgreSQL)
and a web server (one of Apache, Nginx, Microsoft IIS, or ...). The minimum
version numbers are indicated in the following tables:

### Requirements for Joomla! 5.x

| Software                                  | Recommended     | Minimum     |
|-------------------------------------------|-----------------|-------------|
| PHP                    | 8.3             | 8.1.0       |
| **Databases**                             |                 |             |
| MySQL                | 8.1             | 8.0.13      |
| MariaDB            | 11.1.0          | 10.4.0      |
| PostgreSQL      | 16.0            | 12.0        |
| **Web Servers**                           |                 |             |
| Apache        | 2.4             | 2.4         |
| Nginx                | 1.25            | 1.21        |
| Microsoft IIS      | 10              | 10          |

### Requirements for Joomla! 4.x

| Software           | Recommended     | Minimum     |
|--------------------|-----------------|-------------|
| PHP                | 8.2             | 7.2.5       |
| **Databases**      |                 |             |
| MySQL              | 8.0             | 5.6         |
| PostgreSQL         | 11.0            | 11.0        |
| **Web Servers**    |                 |             |
| Apache             | 2.4             | 2.4         |
| Nginx              | 1.18            | 1.10        |
| Microsoft IIS      | 10              | 8           |

## Hosting Services

Commercial hosting services provide everything you need to support a
website. Some also provide one-click installation of popular
applications such as Content Management Systems, Bulletin Boards, Wikis
and so on. But please note: Joomla Forum gurus do not recommend using
one-click installation of Joomla.

Each hosting service offers different plans at different price levels. The
more you pay the more disk space and bandwidth you get, along with more
email addresses, databases and so on. Some also provide a free domain name.
Mostly, you have to pay for a domain name and a small annual registration fee.

## Free Hosting

There is no such thing as free hosting! However, a Joomla partner hosting
service offers a free Joomla website in the joomla.com domain. This gives you
the opportunity to try out your own fully functional Joomla website completely
free of charge. It is similar to a shared hosting plan but with restrictions
and frequent pleas to upgrade to a paid plan. And the free plan needs to be
renewed every 30 days or it will be terminated. The following article shows
the steps required to set up a free Joomla site.

* [Free Joomla Hosting](jdocmanual?article=user/hosting/free-hosting "")

If you find you like Joomla you are can update to a paid plan or look elsewhere
for a hosting service suited to your needs and budget.

## Shared Hosting

You can obtain a minimal hosting plan for about £/$/e50 per year. This plan
level is often referred to as shared hosting and is suitable for
anything not involving sensitive data. Businesses should seek specialist
advice on suitable hosting plans. Choosing a hosting service is not
without problems. The cheapest may have unduly restrictive *php.ini*
settings that do not appear in their advertising. Some may have a poor
reputation for support.

If you opt for a shared hosting plan check the following:

- Support for PHP applications such as Joomla, WordPress and Mediawiki.
- Disk space: 500Mb is an absolute minimum. 1Gb or more would be better
  if you plan on using lots of images.
- Number of Databases: Joomla uses one but you will soon find you need 5
  or 10 or more. Some plans offer an unlimited number within the total
  disk space allocation.
- Database size: with Smart Search the database can grow very quickly.
  If shared hosting has a restriction on the size of the database, it
  will be important to find out what this is. It can lead to a site not
  working.
- Number of email addresses: plenty!
- Number of HTTP and DB connections to the server, which some shared
  hosts limit
- Backups: how are these done, and is there a Terms of Service (TOS)
  document stating who is responsible for backups.

Also check the control panel and platform offered. Judging from Forum
posts, most use cPanel on Linux. The hosting service should provide all
of the basic website support software:

- Apache web server 2.4+ - *directory indexes* should be disabled. Also
  supported:
  - Nginx 1.18+ (fewer users so less Forum support)
  - Microsoft IIS\[6\] (fewer users so less Forum support)
- MySQLi database 5.6+ or MariaDB clone with InnoDB support. Also
  supported:
  - PostgreSQL 11.0+ (fewer users so less Forum support).
- PHP 8+ is recommended, the minimum is 7.2.5.
- phpMyAdmin database management tool.

Before buying, check the following minimal PHP requirements for Joomla:

- *memory_limit* - Minimum: 256M
- *upload_max_filesize* - Minimum: 64M
- *post_max_size* - Minimum: 64M
- *max_execution_time* - Recommended: 30
- *allow_url_fopen* - true

Many of these parameters may be set by the user in cPanel. Ask if that
is possible.

If you have purchased a domain name your hosting service will configure
it for you. They should also provide you with an IP address to use until
your domain registration propagates to Domain Name Servers (DNS),
usually a few hours.

The following article shows what to expect if you purchase a hosting plan that
includes a cPanel user interface.

* [cPanel Hosting](jdocmanual?article=user/hosting/cpanel-hosting "cPanel Hosting")

## VPS Hosting

A Virtual Private Server (VPS) hosting plan provides full access to a server
that is sharing hardware. It behaves like a dedicated computer. You can stop
and start the server, reboot it and install your own software exactly like you
would on a desktop computer. You can create accounts for individual users
just like in shared hosting. Typically, you can allow some features that are
not normally allowed in shared hosting accounts.

Dedicated and Cloud hosting plans are similar in principle but offer either
dedicated resources or resources tailored to your needs.

These advanced plans are not covered here.

## Local Hosting

Most individuals who develop websites keep local copies on a laptop or
desktop computer to test updates or new extensions or to try out new designs.
Setting up a local development site does require some technical knowledge but
it is fairly easy to follow simple instructions.

The following articles describe how to set up local hosting on different types
of desktop or laptop computers:

* [Local Hosting on Windows](jdocmanual?article=user/hosting/local-hosting-on-windows "Local Hosting on Windows") for Windows only
* [Local Hosting with XAMPP](jdocmanual?article=user/hosting/local-hosting-with-xampp "Local Hosting with XAMPP") for Linux, Mac and Windows.
* [Local Hosting on Linux](jdocmanual?article=user/hosting/local-hosting-on-linux "Local Hosting on Linux")
