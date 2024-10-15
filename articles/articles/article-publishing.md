<!-- Filename:  J6.x:_Article_Publishing / Display title: Article: Edit - Publishing -->

## Introduction

A key part of a Content Management System (CMS) is its ability to deliver
content to selected users for selected periods. Joomla! does that with Access 
levels and publishing start and finish dates. 

Start and finish dates can be set for *Featured* articles and *Unfeatured* 
articles alike. For example, a new article could be featured
for a set period, say 30 days, after which it would become an ordinary
unfeatured article. It would disappear from Featured article layouts but
still appear in other Blog or Single article layouts.

Mostly, articles are published on the day they are created and remain so
until unpublished, archived or deleted.

## Screenshot

![The article edit form publishing tab](../../../en/images/articles/articles-edit-publishing-tab.png)

The *Metadata* panel is explained in a separate article. This article covers
the *Publishing* panel.

## Publishing panel

Some of the fields in the form are intended for information and cannot be changed
directly in the form. They are shown with grey backgrounds. Other fields can be
changed if necessary.

### Start Publishing

This field is set to the current date and time when the article is first saved.
If you want the article to be embargoed until a future date and time you can
set its value using the Calendar tool or by directly editing the field values.

### Finish Publishing

By default, this field is blank. If you wish the article to disappear
after a specified date and time use the Calendar tool or type a future date and
time directly into the field. At that point the article will vanish from the
site. In the Articles list it will be marked as *Published, but has Expired*.

### Start Featured

If the article is marked as a *Featured Article*, this field can be set so that 
it appears in a *Featured Articles* layout on the specified date. Note that the
date will not be saved if the article is not marked as a *Featured Article*.

### End Featured

If the article is marked as a Featured Article, this field can be set so that
it disappears from a *Featured Articles* layout on the specified date. The
article remains published and may still appear in other layouts. In the Articles
list it will be marked as *Featured, but has Expired*.

### Created Date

This date is set when the article is first saved. You may wish to change it
if you have created a series of articles in random order and you wish to sort
them into a creation data order.

### Created By

The User Id of the creator is saved at the time of creation and the Name of
that user appears in this field. You can change the Creator by selecting the
person icon to reveal a *Select User* popup dialog from which you can find and
select a different user.

### Created by Alias

If you do not wish the creator Username to appear in the article information 
block you can insert an Alias here. Enter your alias, save the article and 
take a look with the Preview button in the Toolbar.

## Scheduling the Publishing of an Article

By default articles are set as **Published** as soon as they are saved.
The initial saving of the article creates the **Created Date** and
**Start Publishing** dates.

Scheduling an article involves manually setting a **Start Publishing**
date and time to delay publishing. You can also set dates and times to
**Finish Publishing**.

**Note:** For scheduling to work the article **Status** must be set to
**Published**.

Prior to the Start Publishing date articles are regarded as **Pending** and
after the Finish Publishing date they are regarded as **Expired**. Despite the
article itself being set to published, Joomla uses the start and finish
settings to override the default published state.

The date and time values cn be typed into the date fields or selected with the
Calendar tool, opened by selecting the calendar icon at the end of each date
field.

![Publishing dates](../../../en/images/articles-access/article-schedule-publishing.png)

The calendar moves between days, months and years using the keyboard forward, 
backward, up and down arrows. The **Today** button sets the current date. 
The **Clear** button clears the date and time.

* Select the required date.
* Set the time using the drop down boxes.
* Select the Calendar **Close** button to set the selected date and time.
* Select **Save** or **Save & Close** from the Toolbar to save the changes.

## List View Icons

In the Articles list the *Featured* icon is usually either a grey circle or
a yellow star. Similarly, the *Status* icon is usually a green tick or a grey
cross. Each has a Tooltip and the usual action is to toggle the state.

- Published and is Current: <span class="icon-publish" aria-hidden="true"></span>
- Unpublished: <span class="icon-unpublish" aria-hidden="true"></span>
- Featured: <span class="icon-featured" aria-hidden="true"></span>
- Unfeatured: <span class="icon-unfeatured" aria-hidden="true"></span>

The icons for articles with scheduled start and end dates are different.

- Published but is Pending: <span class="icon-pending" aria-hidden="true"></span>
- Published but has Expired: <span class="icon-expired" aria-hidden="true"></span>
- Featured but is Pending: <span class="icon-pending" aria-hidden="true"></span>
- Featured but has Expired: <span class="icon-expired" aria-hidden="true"></span>

In each case a Tooltip shows extra information about the dates scheduled.

## Tips

- You can schedule the publishing of articles from the front end too.
- It is also possible to schedule via the menu item for the article.
- Scheduling is also available for Contacts and Modules.
