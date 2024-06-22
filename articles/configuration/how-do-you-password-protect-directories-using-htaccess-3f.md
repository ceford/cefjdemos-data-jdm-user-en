<!-- Filename: How_do_you_password_protect_directories_using_htaccess%3F / Display title: Password protect directories -->

## Introduction

You may wish to protect a directory or an entire site from public access. One
reason for this is to deny public access to a Development site. Only those
who know the username and password will be granted access. Another reason is
paranoia - for example protection of the administrator folder so users have to
enter a username and password just to gain access to the Joomla Administrator
login form.

The method described here is for Apache servers using a *.htaccess* file.

### Caveat from Apache.org

Basic authentication should not be considered secure for any
particularly rigorous definition of secure. Although the password is
stored on the server in encrypted format, it may be passed from the client
to the server in plain text across the network. Anyone listening with
any variety of packet sniffer will be able to read the username and
password as it goes across.

The username and password are passed with every request,
not just when the user first types them in. So the packet sniffer need
not be listening at a particularly strategic time, but just for long
enough to see any single request come across the wire.

In addition to that, the content itself is also going across the network
in the clear, and so if the website contains sensitive information, the
same packet sniffer would have access to that information, even if the
username and password were not used to gain direct access to the
website.

Don't use basic authentication for anything that requires real security.
It is a detriment for most users, since very few people will take the
trouble, or have the necessary software or equipment, to find out
passwords. However, if someone had a desire to get in, it would take
very little for them to do so.

Basic authentication across an SSL connection, however, will be secure,
since everything is going to be encrypted, including the username and
password.

## Using cPanel

If you are using a hosting service you should use its method for directory
protection. For example, cPanel has an option named Directory Privacy. On
selection you may navigate to any directory and set a name for it. You will
then have the opportunity to create a User Username and Password for the
named directory. Simple?

If you now look in the directory you protected you will find a new .htaccess
file containing something like the following set up to protect the Joomla
api folder:

```
#----------------------------------------------------------------cp:ppd
# Section managed by cPanel: Password Protected Directories     -cp:ppd
# - Do not edit this section of the htaccess file!              -cp:ppd
#----------------------------------------------------------------cp:ppd
AuthType Basic
AuthName "API"
AuthUserFile "/home/username/.htpasswds/public_html/[jroot]/api/passwd"
Require valid-user
#----------------------------------------------------------------cp:ppd
# End section managed by cPanel: Password Protected Directories -cp:ppd
#----------------------------------------------------------------cp:ppd
```
It is important to be aware that cPanel directory protection may use the
same .htaccess file being used by Joomla for other purposes.

If you look in the quoted passwd file you will see the Username you provided
and the encrypted version of the password.

The protection can be removed by repeating the process and unchecking the
`Password protect this directory.` checkbox. That removes the authentication
section from the .htaccess file. It does not remove the .htaccess file!

## .htaccess Rules

You can do all of the required steps manually. This tool may help:

<a href="https://www.htaccessredirect.net/"
 rel="nofollow noreferrer noopener"><em>.htaccess</em>
generator</a>

It creates the necessary files for you. You need to specify the user name,
password, and path.

Fill out the two sections: **Password Protect File** and **htpasswd Generator**
and then select the `Generate Code` button. You get back the text for the
.htaccess file and the text for the .htpasswd file in separate boxes.
Examples:
```
//Password Protect file
<Files /admin>
AuthName "Prompt"
AuthType Basic
AuthUserFile /home/user/.htpasswd
Require valid-user
</Files>
```

```
John:$apr1$a3dbt6j7$KJQr137CY9QuN6tYl6M4Z1
```
