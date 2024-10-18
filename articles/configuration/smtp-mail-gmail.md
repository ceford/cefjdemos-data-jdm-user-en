<!-- Filename: How_to_debug_SMTP_mail_in_Joomla_4 / Display title: SMTP mail and Gmail-->

## Introduction

In the Global Configuration page, Server panel there is an option to select a
mail delivery agent. The default setting is *PHP Mail*. If this does not work
you may be advised to use SMTP. It uses the same mechanism as your mail 
application. There are several settings that you need to get right. In brief:

Go to **Global Configuration** and select the **Server** tab. Look for the 
*Mail* panel near the bottom of the form.

- **Mailer** set to SMTP. Several more fields appear
- **SMTP Host** This is localhost by default but that is unlikely to work. It
  needs to be set to the host that handles your outgoing mail, for example a
  Gmail account.
- **SMTP Port** The default is 25. Check that is the value your SMTP Host expects.
- **SMTP Security** The default is *None* but you are likely to need STARTTLS.
- **SMTP Authentication** This may not be required if you are using a home
  network that expects outgoing emails not to require authentication. Otherwise:
- **SMTP Username** and **SMTP Password** enter the values you use to access
  your email account over the internet.
- Select the **Send Test Mail** button.

## Using Gmail

If you have a working Gmail account you can use Gmail as your mail
server by setting it in the global configuration.

On the server tab set the following:

- Mailer: SMTP
- SMTP Host: smtp.gmail.com
- SMTP Port 465
- SMTP Security: SSL/TLS
- SMTP Authentication: Yes
- Set the next two lines with your information. You need to use an app
  specific password (ASP), described below.
- SMTP Username: your gmail username
- SMTP Password: the app specific password (ASP) you generated,
  described below.

The following are also working combinations:

- SMTP Port 587
- SMTP Security: STARTTLS
- SMTP Port 25
- SMTP Security: STARTTLS

The SSL module does not need to be enabled in Apache.

The OpenSSL extension needs to be enabled in PHP. The details can be
found at the [php.net Installation page](https://www.php.net/manual/en/openssl.installation.php).

If you are using WAMP on Windows, the openssl module is not enabled by
default and you need to enable it. To do this:

1.  Open the php.ini file and uncomment the line `extension=php_openssl.dll` 
    by removing the semicolon ; from the beginning of the line.
2.  Save the php.ini file and restart the Apache service.

Note that if you use 2-step verification in Gmail, you need to add a new
password in Settings - Accounts - Change accounts settings - Other
Google Account settings - Security - 2-step verification - Manage your
application specific passwords.

When the new Application Specific Password (ASP) is presented in groups
of four characters separated by spaces, make sure that you **do NOT
enter the spaces** into the SMTP password in the mail server settings in
Joomla.

- Application Specific Passwords (ASPs): See the Google Support page entitled
  [Sign in with App Passwords](https://support.google.com/accounts/answer/185833).
- 2-Step Verification: See the Google Support page entitled 
  [Turn on 2-Step Verification](https://support.google.com/accounts/answer/185839).

## Debugging

If the mail is not sent or never arrives:

- Select **Plugins** from the **Home Dashboard → Site panel**. 
- Find and Enable the **System - Debug** plugin and configure it:
- Set **Allowed Groups** to *Super Users* to restrict debug output to your own 
  login session in both the backend and the frontend. If you do not want to 
  login to the frontend as Super User, create a unique user group for your 
  testing activities and select that user group from the list of allowed user 
  groups.
- **Save & Close**

- Select **Global Configuration** from the **Home Dashboard → Site panel**. 
- In the *System* tab set **Debug System** to *Yes*.
- In the *Server* tab set **Error Reporting** to *Maximum*.
- In the *Logging* tab note the contents of *Path to Log Folder*, 
  usually *\[something\]/administrator/logs*. 
- Set **Log Almost Everything** to *Yes*.
- In the *Custom logging* panel set the *Log Categories* field to *mail* 
  (no quotation marks).
- **Save** to save the debug settings.
- In the **Server** tab select the *Send Test Email* button at the bottom of 
  the page.

If there are problems in the code during testing you should get a *Stack Trace*
that will help you or others diagnose the problem. Also, look for a file in the
logs folder with a name like *administrator/logs/everything.php* and open it
with a text editor. It may help to see what was logged when the message was sent.
