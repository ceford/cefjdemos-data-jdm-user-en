<!-- Filename: jdocmanual?manual=user&heading=plugins&filename=about-plugins.md / Display title: About Plugins -->

## Introduction

Plugins are Joomla! extensions that do something *behind the scenes* in
response to a trigger. There are about 160 core plugins in over 20 groups.
Third party developers provide many more. The following image shows
the start of the plugins list with the list length set to 5 for the convenience
of the screenshot.

![Plugins list](../../../en/images/plugins/plugins-list.png "Plugins list")

## Plugin Types

In the plugins folder of your site you will see the types. For example, you
will see a **content** folder, which contains plugins that manipulate content,
and a **user** folder, which contains plugins to do with users. You can filter
the list by Type or by Element, such as *contact*, which  may include several
Types.

## Plugin Parameters

Plugins may have few or many parameters. For example, the *Content - Email
Cloaking* plugin offers a choce of two cloaking methods wheras the *Editors -
TinyMCE* plugin has a long list of optional parameters. All of the plugins have
suitable defaults. Often all that needs to be done is *Enable* or *Disable* a
particular plugin as need arises.

## Plugin Execution

Plugin execution is triggered by an *event*. For example, the code that
assembles an article for display has events named `onContentAfterTitle`,
`onContentBeforeDisplay` and `onContentAfterDisplay`. They are used to position
any user-defined fields in the selected locations.

## Individual plugins

Very few of the individual plugins are documented here. They are covered by
Type in the Help page of each plugin.

