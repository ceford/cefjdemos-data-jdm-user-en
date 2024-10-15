<!-- Filename: J4.x:Scheduling_the_publication_of_an_article / Display title: Scheduling Publication -->

## Introduction

A key part of a Content Management System (CMS), is its ability to do
just that - manage content. Joomla! provides an easy way to
deliver content to who you want and when you want by setting Access levels
and publishing start and finish dates and times for your articles.

Joomla also allows you to set start and end times and dates for featured
articles. For example you could create an article about a type of dog that is
available via the dogs link in your menu and set the article as featured
to appear on your home page for a set period of time.

## How Scheduling Works

By default articles are set as **Published** as soon as they are saved.
The initial saving of the article creates the **Created Date** and
**Start Publishing** timestamps.

Scheduling an article involves manually setting a **Start Publishing**
date and time to delay publishing. You can also set dates and times to
**Finish Publishing**.

**Note:** For scheduling to work the article **Status** must be set to
**Published**.

Prior to the Start Publishing date articles are regarded as **Pending** and
after the End Publishing date they are regarded as **Expired**. Despite the
article itself being set to published, Joomla uses the start and finish
settings to override the default published state.

## Scheduling the Publishing of an Article

Under most circumstances you would normally schedule an article when you
create it. If you are scheduling an existing article:

- Select **Articles** From the Home Dashboard Site Panel. Or...
- Select **Content → Articles** from the Administrator menu. Then...
- Find and select the article you want to schedule.
- Select the article's **Publishing** tab.

To schedule the article there are four options:

**Start Publishing** Use this field to schedule a future publishing
date and time of your choosing. If you only set this field the article
will be published on the date you set and then remain published.

**Finish Publishing** Use this field to schedule a date to unpublish
(expire) the article. Note that in the **Article List** the article will
show as **Expired** but if you opened the article from the Article List
it's status would still show as published - this is normal.

**Start Featured** Use this field to schedule a date and time for an
article to appear as a featured one. Note that the article **must** be
set as a featured article to use this field.

**Finish Featured** Setting a date and time in this field will remove
(expire) it as a featured article. Note that in the Article List the
article will show as **Expired** in the Featured Column when the date
and time is reached.

The following screenshot shows Featured date range settings:

![Publishing dates](../../../en/images/articles-access/article-schedule-publishing.png)

The date and time values cn be typed into the date fields or selected with the
Calendar tool, opened by selecting the calendar icon at the end of each date
field.

The calendar moves between days, months and years using the keyboard forward, 
backward, up and down arrows. The **Today** button sets the current date. 
The **Clear** button clears the date and time.

* Select the required date.
* Set the time using the drop down boxes.
* Select the Calendar **Close** button to set the selected date and time.
* Select **Save** or **Save & Close** from the Toolbar to save the changes.

The **Start Publishing** and **Finish Publishing** values are set when the form
is saved. However, the **Start Featured** and **Finished Featured** dates 
require the article to be set to **Featured** using the toggle in the article 
*Content* tab. If not, when the article is saved, the dates entered will be 
cleared.

## List View Icons

In the Articles list the *Featured* icon is usually either a grey circle or
a yellow star. Similarly, the *Status* icon is usually a green tick or a grey
cross. Each has a Tooltip and the usual action is to toggle the state.

- Published: <span class="icon-publish" aria-hidden="true"></span>
- Unpublished: <span class="icon-unpublish" aria-hidden="true"></span>
- Featured: <span class="icon-featured" aria-hidden="true"></span>
- Unfeatured: <span class="icon-unfeatured" aria-hidden="true"></span>

The icons for articles with scheduled start and end dates are different.

- Pending: <span class="icon-pending" aria-hidden="true"></span>
- Expired: <span class="icon-expired" aria-hidden="true"></span>
- Featured: <span class="icon-pending" aria-hidden="true"></span>
- Unfeatured: <span class="icon-expired" aria-hidden="true"></span>

In each case a Tooltip shows extra information about the dates scheduled.

## Tips

- You can schedule the publishing of articles from the front end too.
- It is also possible to schedule via the menu item for the article.
- Scheduling is also available for Contacts and Modules.
