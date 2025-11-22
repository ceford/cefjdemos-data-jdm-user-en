<!-- Filename: https://docs.joomla.org/Joomla_5.4.x_to_6.x_Planning_and_Upgrade_Step_by_Step / Display title: Joomla 5 to 6 Step by Step -->

<div class="alert alert-warning">
<h2>Warning</h2>

This guide assumes you are starting with Joomla 5.4.x. If you are on an earlier version, make sure you migrate or update to Joomla 5.4.x prior to upgrading to Joomla 6.x.
</div>

## Introduction

Good news for Joomla 5.4.x to 6.x, it’s an upgrade, not a migration. Why? Two main reasons:

- Joomla 5 (J5) extensions that have removed all deprecations of code, are using up-to date Joomla code, and do not require the Behaviour - Backward Compatibility plugin to be enabled, will work in Joomla 6 (J6)
- Most others will work with the new Behaviour - Backward Compatibility 6 plugin enabled

This documentation reflects the simpler process by combining the planning and step by step in one document. Still, you will need some skills. Please see the [[Migration Step by Step Self Assessment|Self Assessment]] to determine if you should or shouldn’t tackle the upgrade yourself.

<div class="alert alert-info">
<h2>5.4 to 6.0 Developer documentation for third-party extension developers.</h2>

- [Removed and Backward Incompatibility](https://manual.joomla.org/migrations/54-60/removed-backward-incompatibility)
- [New deprecations](https://manual.joomla.org/migrations/54-60/new-deprecations)
- [About Migrations Documentation](https://manual.joomla.org/migrations)
- [New Features](https://manual.joomla.org/migrations/54-60/new-features/)
</div>

## Planning 5.4.x to 6.x

### Hosting/Technical specification

1. Determine if your hosting environment meets the requirements. You will not 
be able to upgrade to Joomla 6 if your server environment does not meet the 
minimum [technical requirements](https://manual.joomla.org/docs/get-started/technical-requirements/). 
The option to upgrade will not appear in the Joomla Update component.
    - PHP 8.3
    - MySQL 8.0.13
    - MariaDB 10.6.x
    - PostgreSQL 14.0

You can check your system information in Joomla 5 site by clicking System -> System Information. Contact your hosting provider if your server doesn’t meet the requirements.

![System Dashboard with the System Information link outlined](../../../en/images/migration/steps-5-to-6-system-dashboard.png)

The following is an example of an environment that meets the technical requirements. It shows MySQL 8.0.43, PHP 8.3, Joomla 5.4.x, and the Backward Compatibility Plugin Disabled.

![System Information Showing Joomla Version, PHP Version, DB Type, DB Version and BC Compatibility Plugin Disabled](../../../en/images/migration/steps-5-to-6-system-information.png)

2. Check all of your extensions for compatibility with Joomla 6. There are a number of third-party extension scenarios for this upgrade.

    1. The extension may be compatible with J5 and J6 WITHOUT the use of the backward compatibility plugin.
    2. The extension may be compatible with J5 and J6 WITH the use of the backward compatibility plugin.
    3. The extension may appear to work in J6, but when you try to use it, it’s broken.
    4. The extension may break the entire site.

Don’t worry! It’s not as bad as it sounds! First, let’s talk about the backward compatibility plugins.

<div class="alert alert-warning">
<h2>Warning</h2>

To upgrade from Joomla 5.4.x to 6.x, the Backward Compatibility Plugin for Joomla 5 MUST be DISABLED.
</div>

### The Backward Compatibility Plugins

The [Behaviour - Backward Compatibility 6](https://manual.joomla.org/migrations/54-60/compat-plugin/) plugin included with Joomla 5.4.x is to enhance backward compatibility between Joomla 5 and Joomla 6. The plugin assists third-party extensions to use classes no longer included in Joomla 6. It is implemented as a "Behaviour" plugin type to guarantee that it is loaded before any other plugin is loaded.

![Plugin page showing the backward compatibility plugins](../../../en/images/migration/steps-5-to-6-bc-plugins.png)

The image above shows two Backward Compatibility plugins:

1. Behaviour - Backward Compatibility and
2. Behaviour - Backward Compatibility 6

The Behaviour - Backward Compatibility plugin (without a number in the Plugin Name) is provided with Joomla 4.4.x to create a backward compatibility layer for Joomla 5 extensions. **This plugin must be disabled before upgrading to J6**.

The Behaviour - Backward Compatibility 6 plugin is provided with Joomla 5.4.x to create a backward compatibility layer for Joomla 6 extensions.

They cannot both be enabled whilst upgrading to J6. 

Before upgrading from Joomla 5 to Joomla 6, the Behaviour - Backward Compatibility plugin (without a number in the Plugin Name) must be disabled. You need to make sure that all of your third-party extensions can run on your website without having the Behaviour - Backward Compatibility plugin enabled before you can upgrade to J6.

After determining that every single one of your third-party extensions are compliant and fully functional in J5 without the Behaviour - Backward Compatibility plugin enabled, you can disable it. That said, we recommend using caution. Before you disable the backward compatibility plugin, doing one of the following two things is suggested:

1. Do it on a dev/test site. That way, if you accidentally missed one extension that makes your backend inaccessible, it doesn’t take your production site down.
2. Make sure you have access to the db. That way, you can enable the plugin again quickly via the db if needed. More about this below.

When performing an upgrade to J5.4.x, the Behaviour - Backward Compatibility 6 plugin will be enabled automatically. In new installations of J6, the backward compatibility plugin will be disabled by default.

The Behaviour - Backward Compatibility 6 plugin that supports extensions that work in J5 will be in place through J6. In J7, the J5 extensions will not be made backward compatible with the plugin. This gives extension developers two additional years to make their extensions compatible with J6 without the backward compatibility plugin. The intention is that with every life cycle release, a backward compatibility plugin will support the life cycle before it until the life cycle after it.

Can you ever disable the Behaviour - Backward Compatibility 6 plugin in J6? Great question. After determining that every single one of your third-party extensions are compliant and fully functional without the backward compatibility plugin enabled, you can disable the Behaviour - Backward Compatibility 6 plugin. That said, we recommend using caution. Before you disable the Behaviour - Backward Compatibility 6 plugin, doing one of the following two things is suggested:

1. Do it on a dev/test site. That way, if you accidentally missed one extension that makes your backend inaccessible, it doesn’t take your production site down.
2. Make sure you have access to the db. That way, you can enable the plugin again quickly if needed. More about this below.

### Pre-update check vs. System -> Manage Extensions

Theoretically, the pre-update check would tell you if your third-party extensions are compatible with J6. However, the pre-update check is only helpful if all extension developers have made their extension reflect compatibility with their extensions. In a perfect world, the **Extensions** portion of the pre-update check would tell you if an extension either:

* Can be upgraded without the backward compatibility plugin enabled
* Can be upgraded with the backward compatibility plugin enabled
* If an update to the extension is required before upgrading from J5 to J6
* If an extension is incompatible completely

Testing has shown discrepancies between extensions that are compatible and are not compatible. This isn’t an issue with the pre-update check component. Rather, extension developers send information through their extensions which would populate the pre-update check correctly. If their extensions aren’t coded to tell the pre-update check the correct information, there’s very little (nothing) the pre-update check, nor the Joomla! Project can do about it. A good source of information would be the third-party extension developer’s website to verify how the specific extension should be handled during the upgrade from J5 to J6.

The image further down this section shows an example of the pre-update check component in Joomla 5.4.x of the Extensions section.

The top section will show the extensions that require an update. Please go to System -> Update -> Extensions and update your extensions.
The middle section shows extensions that update information is unavailable from the extension developer. You will not know if these are compatible or not without testing them or contacting the developer.

The bottom section shows the extensions that have no update required. This means that the extensions are telling Joomla that they are compatible with Joomla 6. It is not specified if they require the backward compatibility plugin or not.

Please note that these extensions are not preferred by the Joomla Project. These extensions are shown as an example only. They were randomly picked from the JED as a test.

![Pre-update Check Extensions Section](../../../en/images/migration/steps-5-to-6-pre-update-check.png)

It is recommended to only use the **Extensions** portion of the pre-update check component as an extremely high level overview, but not the 100% source of truth. To say it another way, you may not be able to trust the pre-update check component depending on the extensions you are using.

*What is the source of truth then?* Systems -> Manage Extensions

![System Dashboard with Manage Extensions outlined](../../../en/images/migration/steps-5-to-6-system-dashboard-manage.png)

From the Extensions: Manage screen, you will be able to see all of the third-party extensions you are using on the site. In the screenshot below you see the main screen. In the Author column, you can see a popular extension developer’s name in a number of rows. You can also see the Author of the Joomla Project in a number of rows.

![The main Manage Extensions page](../../../en/images/migration/steps-5-to-6-extensions-manage.png)

Check your third party extensions. Next, you will need to determine if they are compatible with J6 (with or without the backward compatibility plugin) or not. If they’re not, the upgrade will be unsuccessful.

### Three ways to check your third-party extensions for J6 compatibility

1. Check the developer website.
2. Take a backup/copy of your J5 site, restore it on a subdomain, turn on debug, follow the step by step (below) to upgrade to J6. See if anything breaks. If it does break, disable each extension that throws an error making note of the extension. You’ll need to contact the developer about it since it isn’t compatible with J6.
3. Install a clean J6 package on a subdomain, enable the Behaviour - Backward Compatibility Plugin, install all the extensions you use and see if they work.

NOTE: The Joomla! Extensions Directory JED will display Joomla 6 compatible badges for extensions that are compatible with or without the use of the backward compatibility plugin.

You could do a combination of the above. Start with a clean install and test out your extensions. When you know which ones do or don’t work, you can work with the developers to see where they’re at with their development for J6. THEN, once all your extensions work in a clean site, you’ll know you can **test** a full upgrade from J5.4.x to 6.x.

You may want to determine if an extension works without the backward compatibility plugin enabled. If that’s the case, you’ll want access to the database. Plan for it. Make sure you have access to the database.

After installing a fresh installation of J6, the backward compatibility plugin will be disabled.  Install each extension one at a time. If it kills your site, enable the backward compatibility plugin via the database.

The Backward Compatibility Plugin can be found in the database in the #__extensions table. It’s called plg_behaviour_compat6. Set the Enabled field to 0 to disable the plugin. 1 to enable the plugin. By enabling the backward compatibility plugin again, you may gain access to the backend of Joomla again (as long as the extension works with the backward compatibility plugin).

OR

You can disable individual extensions in the database so that you can continue testing your other extensions to see if they will function without the compatibility plugin enabled. These entries will be in the #__extensions table. Change the Enabled field to 0 to disable the extension.

In some cases, when you install an extension in J6 that isn’t compatible with or without the backward compatibility plugin enabled, you will need to find the entries in the database for that extension (there may be a few or many of them) and disable them until you can regain access to the backend. These entries will be in the #__extensions table. You’ll change the Enabled field to 0 to disable the extension. Once you can access the backend of Joomla again, you can uninstall it properly from System -> Manage -> Extensions. Then inquire with the developer.

### Cassiopeia and Weblinks

#### Cassiopeia

Cassiopeia will remain the frontend template for Joomla 6. Your customisations should be fine, still, we recommend testing on a dev site to make sure.

#### com_weblinks

The Weblinks extension works in J6 without the backward compatibility plugin enabled in version 5.4.0+:

- [Weblinks Evolved in the JCM](https://magazine.joomla.org/all-issues/september-2025/joomla-weblinks-evolved-insights-from-gsoc-2025). 
- [Weblinks on the JED](https://extensions.joomla.org/extension/weblinks/).

### Trial Run

As part of your planning, it’s recommended to test your upgrade on a subdomain or locally to determine it works perfectly. Make sure you keep track of any steps you need to take for your upgrade to take place **perfectly**.

Once you’ve tested your upgrade on a subdomain or localhost, and it works **perfectly**, you can take a backup of your production site and perform the upgrade to it. Step by step instructions are below.

## Upgrade Step by Step

The site you will be upgrading must meet all the technical requirements and be running Joomla 5.4.x in order to upgrade. If your site is not yet running Joomla 5.4.x, update to 5.4.x prior to upgrading to J6.

1. Follow all the instructions in the Planning section (above) prior to upgrading.
2. **Backup your website.**
3. Update any extensions that need to be updated.
4. Disable or uninstall any extensions that are not compatible with J6.
5. Turn Debug on (Global Configuration -> System tab -> Debug System setting to Yes).
6. **Backup your website again.**
7. **Test your backup to make sure it restores.** (Yes, do this. You’ll feel better.)
8. Go to System -> Update -> Joomla
![The system dashboard with update Joomla outlined](../../../en/images/migration/steps-5-to-6-system-dashboard-joomla.png)
9. Click on the Options button in the Top Toolbar on the right hand side.
![The Joomla update page with the Options button outlined](../../../en/images/migration/steps-5-to-6-joomla-update.png)
10. Change the Update Channel to Joomla Next.
![Joomla update options with update channel outlined](../../../en/images/migration/steps-5-to-6-joomla-update-options.png)
11. Click Save & Close from the Top Toolbar.
12. If your server meets the technical specifications, you will see the following screen with links on the left sidebar for Required Settings, Recommended Settings, and Extensions.
![Pre-update check with sidebar outlined](../../../en/images/migration/steps-5-to-6-pre-update-check-for-6.png)
13. Chances are good that your Required Settings and Recommended Settings will be fine since this screen will not display if your environment doesn’t meet the technical requirements. Extensions may not be fine. See the section in Planning (above) about the Pre-update check and why it may not have a green checkmark but still have all compatible extensions. You’ve already done your testing (correct?), so you already know if they’re compatible or not.
14. The Backward Compatibility 6 plugin is enabled in Joomla 5.4.x. In order to upgrade to J6, the Behaviour - Backward Compatibility plugin needs to be disabled.
15. **If you haven’t followed the instructions in Planning (above) for the Trial run, stop now and go back to the Planning section and follow the instructions. Planning is the most important part of this upgrade.**
16. Once you are sure that all of your extensions are compatible with J6 and you have tested the upgrade and the result was perfect, you may tick the button to Acknowledge the warnings about potentially incompatible extensions and proceed with the update, click OK in the popup box, then click the Update button.
![Acknowledge Warnings notice](../../../en/images/migration/steps-5-to-6-pre-update-warnings.png)
17. Then, your site will ask you again to confirm you’ve taken a backup (which you have and you tested it does restore).
![Upload and Update page to Joomla 6](../../../en/images/migration/steps-5-to-6-upload-and-update.png)
18. Your site will perform the upgrade to J6.
![Upgrade progress page](../../../en/images/migration/steps-5-to-6-joomla-update-progress.png)
19. A successful upgrade will show you a screen like this:
![Update Status page showing success](../../../en/images/migration/steps-5-to-6-joomla-update-success.png)
20. You will see your site being Joomla 6 in the top right corner of the screen.
21. Test the frontend of your site.
22. Test the backend of your site.
23. Turn off Debug in System -> Global Configuration -> Server tab.
24. Fix up your new Smart Search if required.
25. Enjoy a nice beverage and marvel at how wonderful you are.

## What if it goes wrong?

If you tested everything beforehand, it shouldn’t. But it’s possible something in the environment changed or some code in an extension changed between the time of your testing and your upgrade.

Because you enabled Debug before you started, you should be able to see the extension that causes the issue and disable it (this may need to happen from the database if you can no longer access the backend to disable it). That way your site will be up and running whilst you figure out what went wrong, and fix it.

Worst case, restore your backup so you have time to address what happened in a test environment.

Database Fix might resolve some of your issues. Navigate to the System Dashboard and click on Database.

![System Dashboard with Database link outlined](../../../en/images/migration/steps-5-to-6-system-dashboard-database.png)

In the Maintenance: Database page, it will show any database structure issues your site may have. Tick the appropriate checkbox and then click the Update Structure button in the Top Toolbar.

![Maintenance database page showing one problem](../../../en/images/migration/steps-5-to-6-maintenance-database.png)

## Other places to get help

- [Joomla Forum: Migration & Upgrade Board 6.x](https://forum.joomla.org/viewforum.php?f=866&sid=47959551fb677ee3690f8b61eece277b)
- [Joomla Community on Mattermost](https://joomlacommunity.cloud.mattermost.com/main/channels/town-square)
