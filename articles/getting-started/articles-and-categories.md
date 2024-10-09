<!-- Filename: J4.x:Articles_and_categories / Display title: Articles and categories -->

## Introduction

What are articles and categories? What are they used for in Joomla! sites?

## Articles

In Joomla!, an Article is a self-contained unit of written information
to be displayed on a web site. It normally contains some text
and can contain pictures and other types of content. For many Joomla!
sites, articles form the majority of the information presented.

It is important to understand that the content of the site is totally
separate from the formatting of the site, the way it looks on the page.
So it is best to think of Articles as pure content independent of
presentation. The same Article might be shown with different fonts,
colours, headings, and background, and might be shown in different
locations on the page, all depending on other settings in the Joomla! CMS.

## Categories

Categories in Joomla! provide an optional method for organizing 
articles. A Category may contain articles and other Categories rather
like a file system tree. If a category is in another category it is called a 
subcategory of that category. An Article can only be in one Category in the
category tree. 

For example, you might have a Category called *Pets* and in that
category a subcategory called *Dogs* and another called *Cats*. Articles
about dogs would be assigned to the *Dogs* Category and ones about cats
to the *Cats* Category. You cannot have one Article that is in both the
*Cats* and *Dogs* categories. If you have an article that is about both
cats and dogs you would put it in the *Pets* category.

There are two good reasons to organize Articles in categories:

- To take advantage of standard layouts.
- To find selected articles in what might become a long list of articles.

### Blog and List Layouts

A *layout* is a method of organising content in a page controlled by a menu item.
There are many different menu item types. For example, there is *Single Article*
type that displays a single article. That works well when a site has just a few
articles but becomes impractical, except for a few important articles, when a
site has hundreds or thousands of articles.

Joomla has *Category Blog* and *Category List* menu item types that show 
articles from selected categories in well-designed layouts. As new articles 
are created and assigned to categories they are automatically placed 
according to the parameters set for each menu-controlled layout page.

For example, say you have a Category Blog layout for the *Pets*
Category, and say you have it set to order articles starting with the
most recent one first. When you add a new Article to the *Pets*
Category, it will automatically show in the *Pets* blog page as the
first Article. You don't have to do anything other than add the Article
and assign it to the *Pets* Category.

A Category Blog layout often displays one article taster prominently at the 
top of a page and several more article tasters in rows and columns below. This 
type of layout is often used for a site *Home* page. The articles may be
selected from a single category, for example *News*.

A Category List layout is designed to display lists of articles, often with a 
search filter to help find articles of interest. For example, if you have 200
articles in your site, you can filter articles by Category so the list
will be limited to those in the selected Category.

### Categories versus Menus

Menus also have a tree structure with some items being parents to others. It 
is important to understand that the structure of a Category tree (for example 
**Organisms → Animals → Pets → Dogs**) is unrelated to the structure of a menu
tree even if the menu has the same structure and the items have the same names.

### Other Types of Categories

Categories are also used by other components, including Banners,
Contacts, and News Feeds. These categories are completely separate from
Article categories and are set up in different Joomla! Administrator
pages. So when you see something about categories, it might refer to
Article categories or it might refer to categories for these other
components.
