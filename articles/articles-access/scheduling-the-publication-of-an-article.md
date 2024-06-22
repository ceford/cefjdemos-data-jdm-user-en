<!-- Filename: J4.x:Scheduling_the_publication_of_an_article / Display title: Scheduling Publication -->

## Introduction

A key part of a Content Management System (CMS), is its ability to do
just that - manage content. Joomla! provides an easy way for you to
deliver your content to who you want and when you want by setting
publishing start and finish dates and times for your articles.

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

Priot to the Start Publishing date articles are regarded as **Pending** and
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

<img
src="https://docs.joomla.org/images/thumb/2/24/J4x_article_scheduling_tab-en.png/300px-J4x_article_scheduling_tab-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/2/24/J4x_article_scheduling_tab-en.png/450px-J4x_article_scheduling_tab-en.png 1.5x, https://docs.joomla.org/images/2/24/J4x_article_scheduling_tab-en.png 2x"
data-file-width="500" data-file-height="520" width="300" height="312"
alt="article publishing tab" />

To schedule the article there are four options:

**Start Publishing:** Use this field to schedule a future publishing
date and time of your choosing. If you only set this field the article
will be published on the date you set and then remain published.

**Finish Publishing:** Use this field to schedule a date to unpublish
(expire) the article. Note that in the **Article List** the article will
show as **Expired** but if you opened the article from the Article List
it's status would still show as published - this is normal.

**Start Featured:** Use this field to schedule a date and time for an
article to appear as a featured one. Note that the article **must** be
set as a featured article to use this field.

**Finish Featured:** Setting a date and time in this field will remove
(expire) it as a featured article. Note that in the Article List the
article will show as **Expired** in the Featured Column when the date
and time is reached.

In the following screenshot we set a future publishing date for the
article:

<img
src="https://docs.joomla.org/images/thumb/4/4f/J4x_article_scheduling_start-en.png/300px-J4x_article_scheduling_start-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/4/4f/J4x_article_scheduling_start-en.png/450px-J4x_article_scheduling_start-en.png 1.5x, https://docs.joomla.org/images/4/4f/J4x_article_scheduling_start-en.png 2x"
data-file-width="500" data-file-height="445" width="300" height="267"
alt="article publishing date start selection" />

At the end of the *Start Publishing* field select the calendar icon.

The calendar lets you move between months and years using forward or
backward arrows. The **Today** button sets the current date. The **Clear**
button clears the date and time.

* Select the date you require.
* Set the time using the drop down boxes.
* Select **Close** when you have set the date and time.

To set the **Finish Publishing** field the process is the same. The
**Start Featured** and **Finished Featured** fields work the same
but to use these fields the article **must** be set to **Featured**
using the toggle in the article settings. If not, when you save
the article, the dates you entered will be cleared.

Once you have scheduled the article as required select **Save & Close** in
the Toolbar.

<img
src="https://docs.joomla.org/images/thumb/b/be/J4x_article_scheduled-en.png/800px-J4x_article_scheduled-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/b/be/J4x_article_scheduled-en.png 1.5x"
data-file-width="1000" data-file-height="386" width="800" height="309"
alt="articles list status pending icon" />

In the Article List you will see that the article you have scheduled
shows an exclamation mark (!) in the **Status** column. If you hover
over the exclamation mark the scheduling details will be displayed
showing the article is **Pending**. When the scheduled date and time is
reached, the exclamation mark will be replaced with a tick showing the
article is **Published** and **Current**.

If an article has been scheduled to finish, when it does the
**Published** and **Current** tick will be replaced with the
**Expired** icon as below.

<img
src="https://docs.joomla.org/images/thumb/5/57/J4x_article_expired-en.png/800px-J4x_article_expired-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/5/57/J4x_article_expired-en.png 1.5x"
data-file-width="1000" data-file-height="261" width="800" height="209"
alt="article list status expired icon" />

Featured articles will show as pending or expired in the Featured
column.

## Quick Tips

- You can schedule the publishing of articles from the front end too.
- It is also possible to schedule via the menu item for the article.
- Scheduling is also available for Contacts and Modules.
