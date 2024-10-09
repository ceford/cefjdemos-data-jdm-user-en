<!-- Filename: J6.x:Articles:_Filter_Options / Display title: Articles: Filter Options -->

## Introduction

After creating your first article, described in the Getting Started article
on [Adding an Article](jdocmanual?article=user/getting-started/adding-an-article),
your articles list will contain a single article. A year later you may have a 
thousand articles and need to use the *Filter Options* to find what you need.

The following screenshot shows the articles used to prepare this set of 
tutorials. The list Batch Size has been set to 5 to curtail the length of
the screenshot.

The *Filter Options* have been opened to show the filters available.

![Articles list](../../../en/images/articles/articles-filter-options.png)

This list contains over 20 articles created from installation of the 
*Multilingual Sample Data* and a few more articles added later.

## Sort Order

Note that the default sort order is *ID Descending*. This puts the latest
article at the top of the list, which is usually what you want. 

## Pagination

If the number of articles is greater than the *Batch Size*, a pagination bar 
is displayed beneath the list. It has icons to go to the *First page, 
*Previous page*, *Next page* or *Last page*. The numbers lead to articles 
on that numbered page. The pagination bar is useful if you need to browse the 
list of articles.

## Filters

All of the filters operate *On Change* but the filters are remembered and
the *Filter Options* stay visible as long as any one filter is selected.

### Select Featured

- **- Selected Featured -** Selects both Featured and Unfeatured articles.
- **Unfeatured Articles** Selects only Unfeatured articles.
- **Featured Articles** Selects only Featured articles.

### Select Status

The default selection of articles includes *Published* and *Unpublished*.
This allows the publication state to be toggled using the icon in the *Status*
column. *Trashed* and *Archived* items are only included if *All* is selected.

- **Trashed** Selects only Trashed articles. The *Status* icon shows a trash 
  can icon that can be used to Publish the item. A *Delete* button in the
  Toolbar allows complete deletion of any selected article. There is a 
  warning message. After deletion use the *Clear* button to return to the
  unfiltered list.
- **Unpublished** Selects only Unpublished articles.
- **Published** Selects only Published articles
- **Archived** Selects only Archived articles. The Status icon allows the 
  article status to be changed to Unpublished. Archived articles are no longer
  required but can be made available via an *Archived Articles* menu item.
- **All** Selects all articles irrespective of Status.

If an article needs its status changed other than by use of the icon in the
Status column it can be done from the article edit form.

### Select Category

The drop-down list shows all site categories in a tree similar to that used
in the *Articles: Categories* list page. If you select a single category all
articles in that category will be selected along with all articles in its
sub-categories unless the *Select Max Levels* filter is set. 

You can select multiple categories that are not in the same category tree.

### Select Access

The drop-down list allows selection of articles in specified *Access Levels*.
Access control is covered in a separate article. In brief, this restricts
site visibility of articles as follows:

- **Public** Articles available to everyone.
- **Guest** Articles available to anyone who is not logged in.
- **Registered** Articles available to anyone who is logged in.
- **Special** Articles available to anyone who is logged in and belongs to
  a User Group assigned Special Access. 
- **Super Users** Articles restricted to anyone logged in as a Super User.

### Select Author

The drop-down list allows selection of articles by a specific author.

- **None** This is a special case where an article exists but the original
  author does not. There may be multiple authors who contributed articles but
  no longer have user accounts.
- **Created by me** A list of your own articles.
- **Author name** A list of named article authors that could be quite long.
  The real name is used rather than the login name. Select an author as 
  required to see articles by that author.

### Select Language

This filter is only present in Multilingual sites. When an article is created
it can be assigned to *All* languages or to one specific language which has
the language name and country code in the *Language* field of the data entry
form, for example *English (en-GB)* or *Spanish (es-ES)*. In the language filter:

- **All** This filters articles that have been assigned to *All* languages. It
  does not mean all articles!
- **Language name (xx-YY)** A list of the installed languages. Select a 
  specific language to see articles assigned to that language.

### Select Tag

A list of tags. Select any tag to see articles that have that tag. Multiple
tags can be selected.

### Select Max Levels

This restricts the list of articles to the specified number of levels in a
hierarchy. When no value is selected all levels are included. If set to 1,
only articles in the first level of a category tree will be included.

## Multiple filters

On large, complex sites you may need to use multiple filters. The filters are
remembered within a session, until logout or the session expires due to
inactivity. 
