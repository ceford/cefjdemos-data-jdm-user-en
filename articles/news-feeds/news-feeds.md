<!-- Filename: jdocmanual?manual=user&heading=news&filename=news-feeds.md / Display title: News Feeds -->

## Introduction to News Feeds

Once upon a time it was common practice for one website to display news items
from remote websites in a page or panel. Browsers even had built-in News
Readers to do just that. Times change and the major browsers no longer offer
that option. And there are new methods to share site content, espcially with
social media sites.

The method to share news is *Really Simple Syndication*, usually abbreviated to
**RSS**, and this still has a place in website promotion. The following
screenshot shows *NetNewsWire*, a free and open source RSS reader for Mac.
Other RSS readers are available for other platforms. The illustration shows
the **Joomla! Announcements** RSS feed selected. Ten announcements are listed
with Title and brief description. The selected announcement is shown in full
in the right column.

![RSS feed of Joomla Announcements](../../../en/images/news-feeds/news-netnewswire-display.png)

Imagine what one or more RSS feeds might do for your website!

## Setting up a News Feed

Your website has News Feeds set up out of the box. A newly installed Joomla 5
website has these two lines near the top of the Home page source:

```
<link href="/j51/index.php?format=feed&amp;type=rss" rel="alternate" type="application/rss+xml" title="Home">
<link href="/j51/index.php?format=feed&amp;type=atom" rel="alternate" type="application/atom+xml" title="Home">
```
These lines allow automated systems to use either RSS or Atom Feeds. Atom is a
later and slightly different news syndication specification. The lines will be
present in all **Featured** pages and **Category Blog** pages but not in most
other page types. You may disable inclusion of these RSS feeds if you wish.

## Toggle RSS Feed Link

The Global setting of the RSS Feed Link is found in the **Integration** tab
of the Articles: Options page. Set to *Show* or *Hide* as you see fit. The
default is **Show**.

The Global setting can be overridden in a Category blog menu item. Again,
select the *Integration* tab and set the *RSS Feed Link* to *Show* or *Hide*.

The RSS Feed cannot be hidden in a Featured Articles Home page (bug?)!

## The Syndication Feeds Module

There is a core module that you can place on Featured or Category Blog pages
to provide a Syndication link. Fill in the fields in the Module tab. Most have
suitable defaults. If the Label field is left blank the default English label
is *Feed Entries*. In the *Menu Assignment* tab select **On all pages**. The
module will only appear on Featured and Category Blog pages.

![Syndication feeds data entry](../../../en/images/news-feeds/news-syndication-feeds-form.png)

Remember to assign the module to a *Position* and maked it *Published*.

In the Site page view the module displays a link. It is not intended for
clicking unless you have a local Newsreader configured. The link needs to be
copied for use in a Newsreader on another site or Newsreader application.

![Syndication feeds display](../../../en/images/news-feeds/news-syndication-feeds-display.png)

Note that the link is for the items on that page. So if your site has several
category blog pages you will have several different RSS feeds.