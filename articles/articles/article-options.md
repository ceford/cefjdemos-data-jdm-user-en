<!-- Filename:  J6.x:_Article_Options / Display title: Article: Edit - Options -->

## Introduction

The word *Options* is ambiguous in Joomla! It is sometimes inter-changeable
with *Parameters* and most component list views have an *Options* button in
the Toolbar. That leads to an Options page where parameters for the component
as a whole are set. In addition, many component item edit forms have a tab
labelled *Options* used to set parameters for that single item.

This article is about the *Options* tab in the *Article: Edit* form. It is
where parameters are set that affect the overall appearance of the article
being edited. The options for articles as a whole are covered in a separate
article.

## Screenshot

The *Options* tab of the *Article: Edit* form has a series of panels mostly
with a choice of *Use Global (Hide or Show)*, *Hide* or *Show*. The following
partial screenshot shows the general layout.

![Article edit options tab](../../../en/images/articles/articles-edit-options-tab.png)

## Layout panel

An article, or part of it, may appear as a single page or in a category blog
layout controlled by a menu item. In a blog menu item most of the layout fields
have *Use Global*, *Yes/No* or *Show/Hide* and *Use Article Settings* options.
The options in this panel have no effect in blog layouts unless the 
*Use Article Settings* option is selected in the menu item.

Otherwise, these options affect the single article appearance of the article 
being edited. 

- **Layout** In a default installation two choices are offered: 
  - **---From Global Options--- / Use Global** This refers to the 
    *Articles: Options* setting available from the *Options* button in the
    Toolbar of the *Articles* list view. Its *Choose a Layout* value is set
    to *Default*, the only choice available although more may be available in
    custom layouts.
  - **---From Component--- / Default** This refers to the setting in the
    *Articles: Options* settings. As above, but ...
  - **Neither setting has any effect!**
- **Title** It is normal to show the title of an article but there may be
  circumstances where that is not appropriate. Select *Hide* to omit the
  article title from the page display.
- **Linked Titles** The default behaviour is to make an article title a link
  to the article where it appears in blog or list layouts. This setting is
  controlled by the menu item. It may be set to *Use Global (Yes)*,
  *Use Article Settings*, *No* or *Yes*. If the menu item is set to 
  *Use Article Settings* then the *Linked Titles* value in the article will
  be used. Otherwise this setting has no effect. If the title is not linked
  you could use a *Read More* link to access the article from a blog or list
  layout.
- **Tags** Show or Hide tags on the single article page.
- **Intro Text** Show or Hide the Intro text on the single article page. There
  are some circumstances where you may wish to have completely different Intro 
  text for blog layouts that is left out in the full article text.
- **Position of Article Info** This refers to the block of information about
  an article headed with *Details* and containing the *Author*, *Category*,
  *Published* and *Hits* information. The default is to have this above the
  article text. Set to Below to move to below the article text in a single
  article view. If set to *Split* the *Hits* item moves to below the article
  text.
- **Article Info Title** Show or Hide the word *Details* above the list
  of article information in single article view.

## Category panel

The field in this panel work as you might expect. In blog views the menu item 
settings take precedence unless set to *Use Article Settings*.

- **Category** Show or Hide the Category name.
- **Link Category** Link (Yes or No) the Category name. If set to *Yes* the
  Category name is linked to its category blog.
- **Parent Category** If set to Yes the parent category appears as a separate 
  item above the Category in the article information *Details* in the single 
  article layout.
- **Link Parent Category** If set to Yes the Parent category name links to its
  category blog page.

## Associations panel

This panel is only present in Multilingual sites.

- **Associations** If set to Show an extra item is placed in the article
  information starting *Also available:* followed by flags to represent the
  versions of this article available in other languages.
- **Use Image Flags** This item appears if *Associations* is set to *Show*. 
  The default *Yes* displays buttons as language flags. The alternative 
  *No* displays buttons as language codes, for example *en-GB*. 

## Author panel

- **Author** Show or Hide the name of the author of this article in single
  article view. The line in the article informations reads 
  *Written by: Authorname*
- **Link to Author's Contact Page** Yes or no to link the Authorname to the
  author contact page if there is one.

## Date panel

Joomla articles store several dates. If displayed, each of the following occur
as separate lines in the article information for a single article. Remember,
blog layouts use the settings from the menu item unless it is set to 
*Use Article Settings*. The data format is 03 November 2024 but that can be
altered ...[ToDo]

- **Create Date** Hidden by default.
- **Modify Date** Hidden by default.
- **Publish date** Displayed by default.

## Options panel

- **Navigation** For an article that is one of a number of articles in a
  category, there are *Prev* and *Next* buttons beneath the article text to
  navigate to the previous or next pages. If set to *Hide* the navigation
  buttons are not displayed on single article pages.
- **Hits** The total number of times the article has been displayed as a
  single article, displayed in the article information list.
- **Unauthorised Links** This affects blog layouts so the relevant category
  blog menu item must have its *Options: Unauthorised Links* value set to
  *Yes* or *Use Article Settings*. Then if this article *Access* is set to
  *Registered* and the setting in the article is not *No* the *Intro Text*
  for the article will show in the blog layout but the Read more button label 
  will be *Register to read more...*. Clicking on the Read more link will 
  require log in to view the full article content.
- **Position of the links** This refers to the positioning of the links in the
  Images and Links tab, Links A, B and C. The default position is above the 
  article text. This option allows the links to be placed below the article 
  text or not displayed at all.
- **Read More Text** The normal text, *Read More:* followed by the article 
  title is take from the Language key/string values. A custom override for this
  article only can be entered here, for example *See full article:* followed
  by the article title.
- **Browser Page Title** The page title is usually the article title. If that 
  is inconvenient an alternative page title can be entered here for use in
  the single article page. It appears in the browser tab and the 
  `<head>...</head>` area of the page. It will be used by Search Engines.