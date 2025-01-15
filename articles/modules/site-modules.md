<!-- Filename: J4.x:Site_Modules / Display title: Site Modules -->

## Introduction

Modules are lightweight and flexible extensions used to render snippets
of information in **boxes** arranged around a component on a page. A
well-known example is the login module. Modules are assigned per menu
item, so you can decide to show or hide a module depending on which page
the user is currently viewing.

Some modules are linked to components. For example, the **latest News**
module links to the content component to display links to the newest
articles. Modules do not need to be linked to components. They don't
even need to be linked to anything and can be just static HTML or text.

There can be multiple instances of the same module. For example, you may
use one instance of the Random Image module for some pages and another
instance for other pages, each using a different image folder to select
images from.

## Module Positions

Modules are assigned to a position on a page defined by the template in
use. The following illustration shows a schematic layout of the
Cassiopeia template:

![Cassiopeia template position diagram](../../../en/images/modules/cassiopeia-template-positions.png)

And the following list shows the available module positions by name:

```xml
    <positions>
        <position>topbar</position>
        <position>below-top</position>
        <position>menu</position>
        <position>search</position>
        <position>banner</position>
        <position>top-a</position>
        <position>top-b</position>
        <position>main-top</position>
        <position>main-bottom</position>
        <position>breadcrumbs</position>
        <position>sidebar-left</position>
        <position>sidebar-right</position>
        <position>bottom-a</position>
        <position>bottom-b</position>
        <position>footer</position>
        <position>debug</position>
    </positions>
```

## Add a Core Module

Core modules are those supplied with a new Joomla installation. There
are thousands of additional modules available from third party
suppliers. Suppose you would like to show a random image to make your
site more interesting for visitors. From the Administrator menu select
**Content → Site Modules** to see the list of site modules already
in use:

![Site Modules List](../../../en/images/modules/cassiopeia-modules-list.png)

Select the New button to see a list of site modules available to
install:

![Site Modules available](../../../en/images/modules/cassiopeia-modules-available.png)

Scroll down and select the Random Image module. That will open the
**Modules: Random Image** edit form ready for you to fill in.

![Random image module](../../../en/images/modules/cassiopeia-module-random-image.png)

- **Title** This is a compulsory field.
- **Image Type** The default is jpg.
- **Image Folder** Enter a path to a folder that actually contains images of
  the type you have selected.
- **Link** A URL to redirect to if the image is selected.
- **Width** Forces all images to be displayed with this width in pixels.
- **Height** Leave empty to maintain the image aspect ratio.
- **Position** Select a module position for the module to actually appear on a
  page. In the illustration, sidebar-right has been selected.
- **Save & Close** Or use the Help button in the Toolbar to find out what the
  other fields do.

## Module Order

After saving you may need to change the order of the modules in the
chosen position. Proceed as follows:

- in the Modules list, select the Column Ordering icon in the modules
  table heading, it is a combined up/down triangle. That will sort the
  table and show item grab symbols, a vertical ellipsis. Select again to
  reverse the sort order! The column sort symbol changes: up triangle to
  indicate normal sort order, down triangle to indicate reverse sort
  order.
- Grab and drag the Random Image ellipsis to move it up or down. Release
  when it is in your preferred position.

## View the Site

![Random image module site view](../../../en/images/modules/cassiopeia-module-random-image-site.png)

Check the Site appearance. In this case it might be a good idea to
centre the image. That can be done as follows:

- Go back to the edit form and select the Advanced Tab.
- In the Module Class field enter text-center and Save.
- View the result by reloading the Site page.

All done?

## Core Modules List

- **Articles - Archived** This module shows a list of the calendar
  months containing Archived Articles. After you have changed the status
  of an Article to Archived, this list will be automatically generated.
- **Articles - Categories** This module displays a list of categories
  from one parent category.
- **Articles - Category** This module displays a list of articles from
  one or more categories.
- **Articles - Latest** This module shows a list of the most recently
  published and current Articles.
- **Articles - Most Read** This module shows a list of the published
  Articles which have the highest number of page views.
- **Articles - Newsflash** The Newsflash Module will display a fixed
  number of articles from a specific category.
- **Articles - Related** This module displays other Articles that are
  related to the one being viewed. These relations are established by
  the Keywords. All the keywords of the current Article are searched
  against all the...
- **Banners** The Banner Module displays the active Banners from the
  Component.
- **Breadcrumbs** This module displays the Breadcrumbs.
- **Custom** This module allows you to create your own Module using a
  WYSIWYG editor.
- **Feed Display** This module allows the displaying of a syndicated
  feed.
- **Footer** This module shows the Joomla! copyright information.
- **Language Switcher** This module displays a language switcher on your
  website of available content languages.
- **Latest Users** This module displays the latest registered users.
- **Login** This module displays a username and password login form. It
  also displays a link to retrieve a forgotten password. If user
  registration is enabled (in Users → Manage → Options),...
- **Menu** This module displays a menu on the Frontend.
- **Random Image** This module displays a random image from your chosen
  folder.
- **Smart Search** This is a search module for the Smart Search system.
- **Statistics** The Statistics Module shows information about your
  server installation together with statistics on the website users and
  the number of Articles in your database.
- **Syndication Feeds** Smart Syndication Module that creates a
  Syndicated Feed for the page where the Module is displayed.
- **Tags - Popular** This module displays tags used on the site in a
  list or a cloud layout. Tags can be ordered by title or by the number
  of tagged items and limited to a specific time period.
- **Tags - Similar** The Similar Tags Module displays links to other
  items with similar tags. The closeness of the match can be specified.
- **Who's Online** The Who's Online Module displays the number of
  Anonymous Users (Guests) and Registered Users (users logged-in) that
  are currently accessing the website.
- **Wrapper** This module shows an iframe window to specified location.
