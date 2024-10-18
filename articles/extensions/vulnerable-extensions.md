<!-- Filename: jdocmanual?manual=user&heading=extensions&filename=vulnerable-extensions.md / Display title: Vulnerable Extensions -->

## Extension Sources

Anyone may write and distribute a Joomla! extension as a service to the
global community. Such **third party** extensions may be found on professional
extension developer's websites, personal blog websites, GitHub and similar
repositories and the Joomla Extensions Directory website.

## Vulnerable Extensions

Very few sources offer deliberately malicious extensions. Usually, a
**vulnerable extension** is one that has been found to contain (or
contribute to) a security vulnerability after initial release.

Vulnerable extensions are not necessarily poorly coded. As the Web
evolves, technical requirements and commonly accepted coding practices
change. Active projects release new versions of their extensions as
requirements change and quickly fix any reported vulnerabilities.

If you are concerned about any of your extensions you should consult the
Joomla Vulnerable Extensions
list (VEL) which contains information on 240+ mostly old extensions.

## The JED Checker

If you are concerned about an extension that does not appear in the VEL you
can use the JED Checker
extension. This is an extension used to check extensions submitted to appear
in the Joomla Extensions Directory list. It is installed like any other
extension. In use, it accepts an extension zip file and examines its contents
for compliance with JED standards. It is extremely useful even for extensions
that do not appear in the JED list. Here is an example screenshot:

![jed checker result](../../../en/images/extensions/extensions-jed-checker.png)

The 400 PHP files with missing GPL Licence Notice are in third party libraries
with a different Licence. The 30 files identified by the Joomla Anti-Malware
Scan Script are also in those third party libraries. There is work to do on
the files missing JEXEC security!

## Removing a Vulnerable Extension

### Make a List of Files to Remove

If you can locate it, read the extension's xml file to determine exactly
which directories, files, and database tables were added to your system.
The XML file is in the original zip archive used during the extension
install process. For example, the zip archive for an extension called
mod_vulnerable, would contain an XML file called, mod_vulnerable.xml,
and might contain a list of files such as the following:

```
    mod_vulnerable.php
    mod_vulnerable/vulnerable_file.txt
    mod_vulnerable/another_vulnerable_file.txt
    mod_vulnerable/yet_another_vulnerable_file.txt
    mod_vulnerable/index.html
```

### Uninstall Via the Joomla Installer

Using the Installer in the Joomla! Administrator backend, uninstall the
vulnerable extension. You may also need to uninstall related modules,
components, or plugins.

### Verify that the Uninstall Process was Complete

Don't trust the extension to safely remove all of its files. Compare
directories and files on your system to the extension's XML list to
ensure that all related files were actually removed.

### Optionally, Remove the Related Database Tables

Check your database and remove any tables created by the extension. To
ease the upgrade process to new versions, many uninstall scripts do not
remove related database tables. You can find the list of tables in each
extension's XML file.

If you plan to install a safer, compatible version of the same extension
and you want to reuse existing data, you can usually leave the database
tables as is.

### Remove Menu Links

Simply removing the menu links to an extension, or unpublishing a module
is **not** enough to protect your site! As long as the extension's files
exist on your server, you are vulnerable. Note how in the following
examples an attacker can bypass the Joomla! index file to directly
target any file, of any extension.

```
    www.your_site.org/components/com_bad_component/vulnerable_file.php
    www.your_site.org/modules/mod_bad_module/vulnerable_file.php
```
