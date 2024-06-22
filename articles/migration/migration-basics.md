<!-- Filename: jdocmanual?manual=user&heading=migration&filename=migration-basics.md / Display title: Migration Basics -->

## Terminology

Joomla! documents use a variety of terms to mean change from an older version
to a newer version:

* **Migration or mini-migration** is a term usually applied to a change from
an older to a newer *Major* version, sometimes through several interim *Major*
verions.
* **Upgrade** is a term usually applied to a change from one recent version to
the next version in a sequence of *Minor* versions.
* **Update** is a term usually used for the Upgrade process using the Joomla
Update component. It is the word seen in the Administrator interface in
Joomla! 3, 4 and 5. From now on the term *Update* will be used in this article.

See this article for a complete list of Joomla! CMS Versions.

It is also worth knowing that Joomla follows the Semantic Versioning standard.
In brief, given a version number MAJOR.MINOR.PATCH, such as 5.1.0:

* The **MAJOR** version allows for backward compatibility breaks.
* The **MINOR** version allows for additional functionality in a backward
compatible manner within the Major version.
* The **PATCH** version allows for backward compatible bug fixes.

There may be additional suffixes such *alpha*, *beta* or *rc*, but not in
stable releases intended for production sites.

## Reasons to Update

The reasons to update are many and varied:

* **Security:** although Joomla! is recognised as a very secure CMS, occasional
vulnerabilities are discovered and fixed in Minor or Patch releases.
* **Hosting changes:** Joomla uses the *PHP* scripting language and a database
server such as *MySQL*, *MariaDB* or *PostGres*. They progress through changes
and hosting services need to keep up to date. So you may find that an older
version of Joomla no longer works or fails to work if you move hosting service.
* **Design changes:** you may wish to make your site look better, work better
with mobile devices and score more highly with search engines. You might have
to meet legal *Accessibility* rquirements.
* **Functionality:** You may wish to use a Joomla extension that provides some
feature not provided by core Joomla extensions. Choices may be limited by your
current Major version.

## Backup before Update

**This is really important!** Even if you have accomplished several interim
updates it is possible that something may go wrong during the update process.
This may leave your site broken. The standard advice offered in the Forums is
revert to your last backup, find out why the backup failed, fix it and then try
again.

**Akeeba Backup** is a free tool obtainable from the Joomla Extensions Directory
(JED) to which you have direct access via System / Install Extensions / Install
from Web. It only takes a minute or two to download and install. It analyses
your system to configure a profile using a Configuration Wizard. It then makes
a backup which you can download for safe-keeping.

## Self Assessment

Before performing a *Major* or *Minor* version update you need to assess your
system and your existing third party extensions for compatibility with the
Joomla target version. It is a good idea to make a list of the third party
extensions you have installed. In Joomla 4 and 5 the *System / Extensions /
Manage* list has a filter to select **None-core Extensions**. This is not
present in Joomla 3.

You could also use the **Forum Post Assistant**. This is a tool intended to
analyse a site and make a report suitable for posting on the Joomla Forums to
help the Forum experts diagnose problems with your site. However, it has a
private user interface that tells you all about your site. Its extensions lists
(Components, etc.) indicate which are *3rd Party*.

The problems that arise during updates are usually associated with third party
extensions not being code compatible with your target Joomla version. You
should check each extension for compatibility and **uninstall** any that are
known to be incompatible. You may be able to install compatible versions later.

You should set one of the default Site templates as your **default template**:

* Joomla! 1.5 default templates are Rhuk_milkyway, JA Purity, Beez.
* Joomla! 2.5 default templates are Atomic, Beez3, and Beez25.
* Joomla! 3 default templates are Protostar and Beez3.
* Joomla! 4 default template is Cassiopeia only.

## Local Testing

If at all possible, it is best to set up a local testing environment on your
laptop or home workstation to test your update procedure. You can use the
backup of your online site to populate your test site. Your home site must be
able to run your copy of your live site and have adequate PHP and Database
specifications to run the updated site. There is a separate article describing
how to set up a home testing environment.
<!--
## Additional Information

There are a number of articles describing specific update scenarios that are
not included in this manual because they are old or repetetive.

* https://docs.joomla.org/Why_Migrate
* https://docs.joomla.org/Migration_Step_by_Step_Self_Assessment
* https://docs.joomla.org/J3.x:Updating_Joomla_(Install_Method
* https://docs.joomla.org/J3.x:Updating_Joomla_(Update_Method)
* https://docs.joomla.org/Planning_Migration_-_Joomla_1.5_to_4
* https://docs.joomla.org/Planning_for_Migration
* https://docs.joomla.org/Pre-Update_Check
* https://docs.joomla.org/Template_Considerations_During_Migration
* https://docs.joomla.org/J3.x:Update_fails_with_an_error_message
* https://docs.joomla.org/Converting_an_existing_website_to_a_Joomla!_website
* https://docs.joomla.org/Potential_backward_compatibility_issues_in_Joomla_4
->