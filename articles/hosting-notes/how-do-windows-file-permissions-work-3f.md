<!-- Filename: How_do_Windows_file_permissions_work%3F / Display title: Windows File Permissions -->

## Introduction

For those of you who are either developing or delivering your Joomla!
websites from a Windows environment, it is sometimes difficult to
obtain relevant information regarding permissions. Unfortunately, it is
a fact that most Web-Serving is offered under Unix and that Unix is
pretty well documented within this environment. Hopefully, the following
information will go some way to clear up any confusion and provide a
little guidance as well.

### Windows Web Server Overview

Firstly, let's discuss the differences between servers. In general, most
Windows folks appear to be using either Apache(Win32) or Microsoft IIS.
These two web servers operate very differently and utilize slightly
different models of delivery. Apache(Win32) generally runs on the host
computer as the User that it was installed under, whereas IIS installs
under a specific user but will run under a newly installed user *IUSR_*.

### Permission Defaults

By default, Unix tends to only give full access to the *owning* user to
files and directories, in opposition to this approach Windows by default
will also assign the Group *Everyone*, Full permissions. The first thing
any good Windows Administrator will do is to remove the rights of the
*Everyone* group, to improve security. For local PC testing, this is
probably not necessary, but explains why, if *Everyone* is not removed
and you run some form of permissions check script or the Joomla!
Pre-Installation check, on the whole you will have Full *Read, Write and
Execute* permissions, because you are acquiring the rights of the
*Everyone* Group.

### Microsoft Internet Information Server (IIS)

IIS comes in two main flavors, PWS (Personal WebServer), and IIS
(Internet Information Server). Essentially these are the same
application. PWS is just a cut-down version of IIS designed for desktop
environments, whereas IIS is designed for Server environments. PWS
limits you to a single main website, so your application installations
will generally be in sub-directories of the main website. IIS, on the
other hand, provides the functionality for Virtual Hosts to be run from
these directories, delivering multi-site capability.

Due to the different functionality limitations, PWS does not have the
*Permissions Wizard* as it is determined to not be needed. Only one user
will be using the PWS Server. In IIS, many users will be using the
Server, thus differing permission assignments are needed.

Once the *Everyone* account is removed, Windows IIS is now left with the
*IUSR_* account having top-level rights to the Web-Server
directories. A permissions check now should yield different results.
Only the *IUSR_* account has full permissions and other users should
acquire either *Read Only* or no rights. Rights are determined by which
other users have been assigned which rights to the IIS directories
manually.

### Assigning Permissions

Assigning permissions in Windows is reasonably straight forward, but can
be a little confusing at times. Right-Click on the appropriate folder or
file. Selecting *Properties* or *Sharing and Security* will enter the
Windows Security Management pane. Selecting (click once) any user name
listed will display the rights that user has in the bottom half of the
pane. Some rights might be *greyed* out. These are unavailable, either
because the current user (you are logged in as) does not have high
enough permissions to alter them, or they are inherited from the
directory above and have been set to use that higher level directory's
permissions (this is generally the default mechanism).

As you can see, Windows utilizes the following Permissions/Rights
scheme:

<table data-cellpadding="2" data-cellspacing="0" data-align="center"
data-border="1" width="533">
<thead>
<tr>
<th>#</th>
<th>Permissions</th>
<th>Rights</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p>1. </p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Full
Control</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows:
1, 2, 3, 4, 5, 6, 7</p></td>
</tr>
<tr class="even">
<td style="text-align: left;" width="5%"
data-valign="top"><p> 2.</p></td>
<td style="text-align: left;" width="33%"
data-valign="top"><p> Modify</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows:
2, 3, 4, 5, 6</p></td>
</tr>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p> 3.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p> Read
&amp; Execute</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows:
3, 4 </p></td>
</tr>
<tr class="even">
<td style="text-align: left;" width="5%"
data-valign="top"><p> 4.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p> List
Folder Contents</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows: 4
(but cannot run programs) </p></td>
</tr>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p> 5.</p></td>
<td style="text-align: left;" width="33%"
data-valign="top"><p> Read</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows: 5
(Implies: 4)</p></td>
</tr>
<tr class="even">
<td style="text-align: left;" width="5%"
data-valign="top"><p> 6.</p></td>
<td style="text-align: left;" width="33%"
data-valign="top"><p> Write</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows: 6
(Implies:4 )</p></td>
</tr>
<tr class="odd">
<td style="text-align: left;" width="5%"
data-valign="top"><p>7.</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p> Special
Permissions</p></td>
<td style="text-align: left;" width="33%" data-valign="top"><p>Allows:
Combinations </p></td>
</tr>
</tbody>
</table>

### Windows file permissions properties

Windows file permissions can be seen as having **similar** properties as
UNIX or Linux file (Modes) permissions, they are just represented
differently. For example, if you are primarily a Unix/Linux user, you
are probably used to having permissions represented as 644/666 755/777,
instead of being described in the terms above. So, when you are quoted
to use 644 this equates to:

* The owner of this file can read and write to it.
* The owner's group can read the file.
* Everyone else can read the file.

**Note:** Windows and Unix permissions (Access Control Lists) do not
equate exactly, as Windows does not use the *Groups* mechanism in the
same manner. However, for this discussion and in regards to the
Web-Hosting environment they can be summarily equated. Ah, but, in windows
***Groups*** are not used and ***Everyone*** should have been removed.
This is where Windows and Unix do not quite equate, but what can be
done is to *match* or *correlate* equivalent meanings.

This outline is not really going to provide you with a Windows or an NTFS
specific permissions guide but more of an understanding of how the commonly
quoted numbered UNIX/Linux style permissions correlate on a machine with
an NTFS file system. The files that are placed in the www or public_html root
folder, or whatever directory your site (www.domain.com.au or localhost) points
to on your hard drive should be owned by your user account, but only if
that user is not what is considered as a privileged user like
*Administrator* on Windows or *root* on UNIX/Linux. These accounts allow
way too much access and should never be used for everyday use.

### Best Practices

Commonly used security practices suggest that all **files** should have
the following permissions.

* **Owner:** Read & Write
* **Group:** Read Only
* **Others:** Read Only

All **directories/folders** should have the following permissions:

* **Owner:** Read, Write & Execute
* **Group:** Read & Execute
* **Others:** Read & Execute

Arguably, this is not necessarily *optimum* security, but a balance
must be struck between security, functionality and maintainability.
Windows, unlike Unix, does not maintain a single ACL for *Execute*, but
simply provides *Read & Execute* combined, which does not imply *Write*.
The *Read & Execute* ACL does however imply *List Directory Contents*.
Therefore, if you have only *Read & Write* permissions on a directory
but no *Execute* you will not be able to see the contents of the
directory and may also have problems when attempting to run the file
through a web browser. A little understanding of UNIX/Linux permissions is
required to fully equate/correlate them to Windows permissions. The
following table should assist;

<table data-cellpadding="2" data-cellspacing="0" data-align="center"
data-border="1" width="659">
<thead>
<tr class="odd">
<th style="text-align: center;" data-bgcolor="#cccccc" width="7%"
data-valign="top"><p><strong>Unix Mode</strong></p></th>
<th data-bgcolor="#cccccc" width="10%"
data-valign="top"><p><strong>Windows ACL </strong></p></th>
<th data-bgcolor="#cccccc" width="33%"
data-valign="top"><p><strong>Comments </strong></p></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>7 </strong></p></td>
<td width="10%" data-valign="top"><p><strong> Modify </strong></p></td>
<td width="33%" data-valign="top"><p><em>Read, Write &amp; Execute, you
should be the owner of this file</em></p></td>
</tr>
<tr class="odd">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>6</strong></p></td>
<td width="10%" data-valign="top"><p><strong> Read &amp; Write</strong></p></td>
<td width="33%" data-valign="top"><p><em> </em></p></td>
</tr>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>5</strong></p></td>
<td width="10%" data-valign="top"><p><strong> Read &amp; Execute</strong></p></td>
<td width="33%" data-valign="top"><p><em>used for most
applications</em></p></td>
</tr>
<tr class="odd">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>4</strong></p></td>
<td width="10%" data-valign="top"><p><strong> Read Only</strong></p></td>
<td width="33%" data-valign="top"><p><em>security through obscurity is
not a good practice</em></p></td>
</tr>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>3</strong></p></td>
<td width="10%" data-valign="top"><p><strong> Write &amp; Execute</strong></p></td>
<td width="33%" data-valign="top"><p><em>not available through windows,
unless "Special" Permissions is used, not commonly used</em></p></td>
</tr>
<tr class="odd">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>2</strong></p></td>
<td width="10%" data-valign="top"><p><strong> Write Only</strong></p></td>
<td width="33%" data-valign="top"><p><em>not available through windows,
unless "Special" Permissions is used, not commonly used</em></p></td>
</tr>
<tr class="even">
<td style="text-align: center;" width="7%"
data-valign="top"><p><strong>1</strong></p></td>
<td width="10%" data-valign="top"><p><strong> Execute Only</strong></p></td>
<td width="33%" data-valign="top"><p><em>not available through windows,
unless "Special" Permissions is used, not commonly used
</em></p></td>
</tr>
</tbody>
</table>

In comparison to Unix Modes, when you see something like 644, you would break
that into three elements:

**6**  :  **4**  : **4**

The first number represents the **Owners*** permissions, the second
represents the ***Group*** permissions and the third, the ***Other***
permissions. The Windows equivalent would be;

* **Owner** (6) : **Read & Write**
* **Group** (4) : **Read Only**
* **Others** (4) : **Read Only**

Hopefully, this example provides some insight into how to correlate Unix
Modes/Permissions into Windows Permissions/ACL's. This document does not
include more complex subjects such as *Effective*, *Inherited*, or
*Special* permissions. Despite Windows ease of use, Microsoft's
Permissions and ACL mechanisms are actually reasonably complex and very
extensive, but this might just give you a quick reference to try and
alleviate some of the confusion surrounding Unix and Windows Permissions
translations.
