<!-- Filename: J5.x:Improving_SEO_with_Strict_Routing_and_SEF_URLs / Display title: SEO Strict Routing -->

## Introduction

The Strict Routing option, introduced in Joomla 5.2, enhances the platform’s SEO performance by allowing for stricter routing rules using a switch in the *System - SEF* plugin. It helps to eliminate duplicate content by enforcing more consistent URLs and redirecting duplicates to the correct URL with a 301 redirect.

![system sef plugin settings](../../../en/images/seo/seo-system-sef-plugin.png)

### Enforcing Suffixes

Currently, Joomla allows access to URLs with or without a suffix when this option is enabled in the *Global Configuration* options. 

The **Enforce a suffix by redirect** option in the *System - SEF* plugin enforces consistent suffix behavior. When enabled, it redirects GET requests to a URL with a suffix if it is missing. It will also redirect URLs with a query format parameter to the cleaner URL, replacing the suffix with the format parameter where needed.

This feature is expected to become the default behavior in Joomla 6.0, where the option to enable or disable it will be removed, and this functionality will be integrated into the core routing system. For now, this option allows users to test the behavior on live systems and disable it if unforeseen issues arise during the transition period from Joomla 5.1 to 6.0.

## How to Access

To enable strict routing for SEO:

1. Select the **Plugins** item in the *Home Dashboard*.
1. Find and open the **System - SEF** plugin.
2. Set **Strict Routing** to *Yes* to enable stricter URL handling.
3. Set **Enforce a Suffix by Redirect** to Yes or No depending on your preference for enforcing URL suffixes.

Once enabled, Joomla will automatically redirect duplicate URLs to the correct one with a 301 redirect, improving SEO by consolidating content under a single, authoritative URL.

## Additional Notes

This feature is designed to work as a preparatory step for further SEO improvements and is automatically enabled for new Joomla 5.2 installations. It lays the groundwork for future enhancements to Joomla’s routing system. 