<!-- Filename: J4.x:FatalError / Display title: FatalError -->

## Introduction

From time to time Joomla may display an error page instead of the page
you were expecting. There are two types of error pages:

- The system error page has a red background. It is invoked if there is
  a serious error before the site or administrator template is rendered.
- The template error page looks like the normal site or administrator
  template but the content area is replaced with an error message. This
  is invoked when the error occurs in content code.

### System Error Page

![System fatal error page](../../../en/images/problems/fatal-error.png)

### Template Error Page

![Template error page](../../../en/images/problems/template-error.png)

## How to Resolve

There are a number of possible reasons for fatal errors to occur. Here
are just a few:

- A change in your host, for example an updated PHP version that is not
  compatible with Joomla or one of your Extensions.
- A problem with disk space, memory usage or script time-out.
- A newly installed or enabled Extension that is not compatible with
  Joomla. A bad plugin may disable Administrator login!

### Enable Debug

If your Administrator interface **is** still working:
- Go to **Home Dashboard → System panel → Global Configuration**. 
- In the System tab set *Debug System* to *Yes* 
- In the Server tab set *Error Reporting* to *Maximum*. 
- Then *Save & Close*.

If your Administrator interface is **not** working, edit the
*configuration.php* file in the root folder of your Joomla website.

1.  Change the permissions from *444* or *-r--r--r--* (no one has
    permission to write to the file) to *644* or *-rw-r--r--* (only the
    Owner has permission to write).
2.  Edit the file with a text editor and set `$debug` to `true` and 
    `$error_reporting` to `'maximum'`.
3.  *Save* the file.

With the changes made, reload the page that was causing the error. Now
you should see a stack trace. Example:

![Template error page](../../../en/images/problems/template-error-stack-trace.png)

The first item in the stack trace indicates where the error was
triggered. Sometimes that is enough to identify the faulty Extension.
Sometimes the faulty Extension is farther down the stack trace. It may
not mean much to you but the stack trace is invaluable to the experts
who answer questions in the Joomla Forums.

If you can identify the faulty Extension, disable it. You can do that
using the Administrator interface if it is working. Otherwise, use
phpMyAdmin to find the Extension in the `#__extensions` database
table and set its `enabled` value to `0`. You should not need to disable
any core Joomla Extensions.

## Forum Post Assistant

To help resolve problems you should download the
[Forum Post Assistant (FPA)](https://forumpostassistant.github.io/docs/) and
load it in the root of your Joomla website. The link to find it is also
near the top of each Joomla Forum page. The FPA is a stand-alone PHP
script that analyses your Joomla installation and tells you what might
be wrong. Again, it might not mean much to you but the experts who
answer questions in the Forums may ask to see it.

## Cleaning Up

When your problem is resolved:

1.  Go to **Home Dashboard → System panel → Global Configuration**
2.  Select the System tab and set *Debug System* to *No*.
3.  Select the Server tab and set *Error Reporting* to *System Default*.
4.  *Save & Close*.
5.  Remove the Forum Post Assistant.

The `configuration.php` permissions are set to read-only (444 or *r--r--r--*) 
when the Global Configuration form is saved. There is no need to to do it 
manually.
