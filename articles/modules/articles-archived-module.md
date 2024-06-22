<!-- Filename: J4.x:How_to_Show_a_Calendar_Month_List_of_Archived_Articles_Using_a_Module / Display title: Archived Articles -->

## Introduction

Archiving articles is one of the ways Joomla! helps to manage a website’s
articles as it helps to reduce clutter in the backend. But what website
visitors should be able to access archived articles?

One way to do this is to show a calendar month list of archived articles
using one of Joomla’s core Modules. In this example an **Articles Archived
Module** will be set to display in the website sidebar.

## Create the *Articles - Archived* Module

Use one of the following methods:
* Select the **Modules** item from the Home Dashboard. Or...
* Select the **Content / Site Modules** from the Administrator menu.
* Select the **Archived Articles** item from the Modules (Site) list.

This will create the new module and open the module for configuration.

## Configuring the Module

**For standard usage of the module there are just a few settings:**

**Title**: Enter a name for the module.

**\# of Months**: Set the number of Months you want to display. These
will appear as links on the frontend. Set by using the up/down arrows or
directly enter a number into the field.

**Title Show/Hide:** Choose whether or not to show the title by toggling to
*Show* or *hide*.

**Position**: Set a position where you want to display the module on the
front end. Positions are dictated by your template. This example uses Joomla’s
Cassiopeia template *Sidebar Right* position.

**Status**: By default, the module status is **Published**. Other options are
**Unpublished** and **Trashed**.

**Start Publishing**: You can schedule the start of publishing of the
module.

**Finish Publishing**: You can schedule when to stop publishing the
module.

**Access**: If you want to control who can see the module on the
frontend you can choose an access level.

**Ordering**: Used to control where the module displays within the
position you have selected. For example, you may have a number of
modules in the sidebar and want this one to be at the top or bottom – or
somewhere between others in the sidebar. It can be a little confusing at
first as the field shows a numbered position and a module name. The name
can be a module that is unpublished. The thing to remember is that the
lowest number will be at the top and highest number is at the bottom.

**Note**: Can be helpful to use the note field if for example you are
using the same module type in several places.

### Menu Assignment Tab

By default the module will be published **On all pages**.

Alternatively you can choose via a drop down list **No pages**, **Only
on the pages selected** or **On all pages except those selected**. The
last two options provide you with a menu tree of the menus used on the
website where you can select/deselect pages.

### Other Settings

The **Advanced** tab has settings related to layout of the module when it is
output.

The **Permissions** tab allows you to control what user groups can do with
the module.

## Publishing the Module

When you are ready, select the **Save & Close** button.

The module will be published in the sidebar of the website and display a
list of links dictated by the number of months to display set the module.

![Archived Articles Module Example](../../../en/images/modules/modules-archived-articles.png "Archived Articles Module Example")

## Quick Tips

The more archived articles you have the greater the number of the links
displayed by the module. It may be more appropriate to limit the number
of links by using categories or you can use multiple Archived Articles
Modules named accordingly.
