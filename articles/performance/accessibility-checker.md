<!-- Filename: jdocmanual?manual=user&heading=performance&filename=accessibility-checker.md / Display title: Accessibility Checker -->

## System - Joomla Accessibility Checker

This is a core plugin that can be used to check accessibility whilst creating
article content. The following screenshot shows some plugin settings:

![Plugin form settings](../../../en/images/performance/performance-jooa11y-plugin-form.png "Plugin Settings")

With the **Show Always** option set to *On* the report icon appears on every
page of the site. That is useful for development but should never be left on
for a live site. Set it to **Off**!

With the *Show Always* option set to *On* each site page has an icon at the
bottom right with a count of the number of issues. The following screenshot
shows the icon selected to show a panel of information. It includes a Page
Outline, Readability comments and Warnings, which can be selected one by one.
The first issue has been selected.

![Site accessibility check](../../../en/images/performance/performance-jooa11y-site-display.png "Site accessibility check")

The *Articles: Edit* form has an **Accessibikity Check** button in the Toolbar.
It shows the check for an individual article in a popup window:

![Editor accessibility check](../../../en/images/performance/performance-jooa11y-admin-display.png "Editor accessibility check")

## Fixing Problems

The Accessibility Checker is a tool to identify problems. It does not correct
problems. That is up to you. The checker has some settings you can toggle On/Off
as required. They include Contrast, Form Labels, Links (Advanced) AAA,
Readability AAA, Dark Mode and Colour Filter with simulation of four types of
faulty colour vision.

For more information see the Sa11y Overview

For example, on Readability, it says:

>Sa11y can estimate the readability score from all paragraphs and list content.
A good readability score is an indication that your writing is understandable
and easy to digest. It is based on the average length of sentences and words
on your page, using a formula known as the Flesch reading-ease test
(Wikipedia). A "good" reading score is between 60 and 100. Sometimes it may be
difficult to achieve a good readability score. Most of your pages may say
"difficult". Remember that this feature is only used to estimate the
readability of your content. It should only be used as a reference, and not
an indication of conformance. Sa11y calculates the readability score based
on all paragraph (`<p>` tags) and list content (`<li>` tags). A low score does
not affect the pass or fail state of Sa11y.

