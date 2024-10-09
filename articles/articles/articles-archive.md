<!-- Filename: J4.x:How_to_Archive_an_Article / Display title: Articles: Archive -->

## Introduction

As your website content grows it is likely that some of that content
will need to be updated or replaced. You might choose to unpublish some
articles but you may have a requirement to keep them in a way that people
can still view them.

Joomla! makes archiving of articles a simple process by allowing you to
change the status of an article to **Archived**. A benefit of archiving
is that it makes content management easier and archiving is structured
by year.

This status based approach is a key part of Joomla’s ability to
effectively and efficiently manage content. Once archived, Joomla
provides methods to access and display the archived content.

## Archiving Articles

You can archive an article in several places:

- A previous article on
  [Adding an Article](jdocmnaual?article=user/getting-started/adding-an-article)
  showed a screenshot of the *Articles* list page with an article selected and
  the *Actions* list in the Toolbar open to show the options available. One of
  them is *Archive*. That is probably the best way to archive an article. Note 
  that you can archive several articles at once. Selecting one or more articles 
  will enable the **Actions** dropdown list.
- Each article has a *Status* setting in the article edit form. *Archived* 
  can be set there.
- From Within a *Single Article* menu item type. The *Select Article* field 
  has an *Edit* option that opens a popup *Edit Article* form where the *Status*
  field can be set as in a standard article edit form. The single
  article menu item still links to the archived article.

Archived articles no longer appear in the *default* Articles list. Select the
*Filter Options* button and then *Archived* from the *- Select Status -* filter
to see the list of archived articles.

## Site view of Archived Articles

Once articles have been archived, there are several ways to view them from the
Site frontend.

### Via a menu

There is an [Archived Articles](jdocmanual?article=user/menus/menu-item-type-archived-articles)
menu item type that you can use to create a link in your menu to archived
articles.

### Via a module

There is an  [Articles – Archived](jdocmanual?article=user/modules/articles-archived-module)
module that you can use to display in a one of your website template module 
positions.

The following screenshot shows an *Archived Articles* page obtained with
a menu item. There are filters for *Month* and *Year* and a list limit with 
settings from 5 to 100 and All. Always beware of using *All*. If you return
thousands of results your page may be slow to load and unresponsive. You may 
run out of time or memory leading to a server error being returned.

![Archived articles page view](../../../en/images/articles/articles-archived-site.png)

At the foot of the right column is the *Archived Articles* module.

## Un-archive Articles

To un-archive an article the same process applies - the status of the
article is changed from **Archived** to **Published**.

## Tips

* Remember, archived articles are filtered from view in the *Articles*
list. You must change the *Status* filter to *Archived* to view them.
* Archiving does not unpublish an article.
* You can also archive articles from the frontend when logged in for
frontend editing.
