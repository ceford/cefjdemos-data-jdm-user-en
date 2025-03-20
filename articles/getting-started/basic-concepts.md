<!-- Filename: J4.x:Articles_and_categories / Display title: Basic Concepts -->

## Introduction

To get started with Joomla you need to be aware of some of the basic building blocks: Articles, Categories, Menu Items, Menus and Modules. They are briefly described here should you wish to take the plunge and create some content.

## Articles

In Joomla!, an Article is a self-contained unit of written information to be displayed on a web site. It normally contains some text and can contain pictures and other types of content. For many Joomla! sites, articles form the majority of the information presented.

It is important to understand that the content of the site is totally separate from the formatting of the site, the way it looks on the page. So it is best to think of articles as pure content independent of presentation. The same Article might be shown with different fonts, colours, headings, and background, and might be shown in different locations on the page, all depending on other settings in the Joomla! CMS.

## Categories

Imagine a library without a classification system: books are just placed on the shelves in the order in which they are received. That is not very helpful if the library has millions of books and you are looking for something on History, Gardening or Science. The same sort of argument applies to articles. If you have dozens, hundreds or thousands of articles you really need a method to classify them so that you can easily find what you need. That is what categories are for.

A Joomla! Category can contain both articles and categories in a tree-like structure. If a Category is in another Category it is called a sub-category of that Category. Sub-categories may have further sub-categories too, although it is unlikely that you will want to go beyond a depth of three or four.

For example, if your articles are about Nature you might classify them as follows:

- Animals
  - Birds
    - Hawks
    - Finches
    - Gulls
  - Mammals
    - Apes
    - Monkeys
    - Rodents
- Plants
  - Flowers
    - Daisies
    - Roses
  - Trees
    - Oaks
    - Elms

In this example, the Animals category might contain articles about animals in general as well as sub-categories for articles on different types of animal.

Categories also allow you to select what articles you want to display in each page of the website. Therefore, you may want to have in the same Category all the articles that are meant to be on the same page. 

An Article can only be in one Category in the category tree. For example, you might have a Category called Plants and in that category a subcategory called Trees and another called Flowers. Articles about flowers would be assigned to the Flowers Category and the ones about trees to the Trees Category. You cannot have one Article that is in both the Flowers and Trees categories. If you have an article that is about both you would put it in the Plants category. In some circumstances, you may need a more flexible way to classify your articles. That is where Tags come in useful. They are covered elsewhere.

Categories are also used by other components, including Banners, Contacts, and News Feeds. These categories are completely separate from Article categories and are set up in different Joomla! Administrator pages. So when you see something about categories, it might refer to Article categories or it might refer to categories for these other components.

## Menu Items

New articles may not be visible on the website. They need menu items to control their display. Menu items are the basic navigation units of a Joomla! site. After arrival on a page of the website, most menu items lead to other pages on the site.

There are many types of menu items. The simplest one is the Single Article menu item, which links to a page with just one article. Another kind of menu item is the Category Blog. This one leads to a page that displays all the articles of a category. In both cases, the url of the destination page is established by the menu item. The layout (i.e. how the content is organized within the page) of the destination page is also established by the menu item. For example, for the case of the Category Blog, it can show an introduction to each article. These introductions are called tasters. And these tasters can be displayed in one or more columns. Their order can be customized too. Articles can appear chronologically starting with the most recent one. In this case, when you assign a new Article to the selected Category, it will automatically show in the page as the first Article.

A site Home page is often a Category Blog menu item type or a Featured Articles menu item type.

## Menus

A Menu is a container for menu items. A standard installation of Joomla! creates a Main Menu for you with a single Menu item labelled Home. In many cases you will use only one Menu but you can have more than one. Menus can have a tree structure with some items being parents to others.

## Modules

Modules are small extensions used for special purposes. To display a Menu on the website, you have to assign it to a Menu Module. Then, you can specify the location of the Menu on the page (above, below or beside the main page content). A login form is another type of module often displayed to the right of the main content of a page.
