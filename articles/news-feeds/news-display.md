<!-- Filename: jdocmanual?manual=user&heading=news&filename=news-display.md / Display title: News Display -->

## The Feed Display Module

There is a core *Feed Display* module available to display news from other
sites. The following screenshot shows the data entry form with the URL of
the Joomla Announcements news feed. Notice the Word Count is set to 100.
Otherwise, the length of an announcement can be excessive for a sidebar module.

![Feed display module data entry](../../../en/images/news-feeds/news-joomla-news-form.png "Feed display module data entry")

The result can be ugly but can be improved with some custom styles in user.css:

![Feed display module data entry](../../../en/images/news-feeds/news-joomla-news-display.png "Feed display module data entry")

## Feed Display Pages

As an alternative to display of news in a module you can create a menu item
to display a news feed in a web page. From the Administrator menu:

* Select **Components / NewsFeeds / Feeds**. You could first create a Category
for news.
* Select the **New** button in the *Toolbar*.
* Fill out the **News Feeds: Edit** form:
    - The **Link** is the RSS link copied from a remote source.
    - The **Description** is optional.
    - The **Otions** tab has items to control the feed *Display*.
* **Save & Close**

![NewsFeed component data entry](../../../en/images/news-feeds/news-feed-data-entry.png "NewsFeed component data entry")

Create a menu item starting from the Administrator menu:

* Select **Menus / Main Menu** or any other menu for this item.
* Select **New** from the *Menus: Items* Toolbar.
* In the **Menu Item Type** use the **Select** button to find and select
*News Feeds / Single News Feed*.
* Fill out the rest of the form as appropriate.
* **Save & Close**

![NewsFeed menu item data entry](../../../en/images/news-feeds/news-feed-data-entry.png "NewsFeed menu item data entry")

Test it: go to the Site menu and select the Feed menu item.

![NewsFeed display](../../../en/images/news-feeds/news-feed-display.png "NewsFeed display")

Each item in the feed is a `<li>` within a `<ul>` tag so by default it appears
marked by a bullet. This is not so obvious if the items are long. You can apply
your own styles in *user.css*. The following will place each item in a distinct
box:

```
ul.com-newsfeeds-newsfeed__items {
  list-style-type: none;
  padding-left: 0;
}

ul.com-newsfeeds-newsfeed__items > li {
  padding: 1rem;
  margin-bottom: 1rem;
  border: 2px solid navy;
}
```
Which appears like this:

![NewsFeed custom display](../../../en/images/news-feeds/news-feed-custom-display.png "NewsFeed custom display")

## List News Feeds in a Category

The *Joomla! RSS News Feeds* page lists eight separate news feeds. You could
make a feed for some or all of them and assign them to a Category, say *Joomla
News*. Then you can create a menu item with *Menu Item Type* set to *List News
Feeds in a Category* and the Category set to *Joomla News*.

![News feed by category menu form](../../../en/images/news-feeds/news-feed-menu-category-form.png "News feed by category menu form")

Try it to see the outcome!