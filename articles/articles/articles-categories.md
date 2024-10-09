<!-- Filename: J4.x:Create_and_Manage_Article_Categories / Display title: Articles: Categories -->

## Introduction

Imagine a library without a classification system: books are just placed
on the shelves in the order in which they are received. That is not very
helpful if the library has millions of books and you are looking for
something on History, Gardening or Science. The same sort of argument
applies to Articles. If you have dozens, hundreds or thousands of
articles you really need a method to classify them so that you can
easily find what you need. That is what Categories are for.

A Joomla! category can contain both articles and sub-categories in a
tree-like structure nested to any depth, although it is unlikely that
you will want to go beyond a depth of three or four. For example, if
your articles are about Nature you might classify them as follows:

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

In this example the *Animals* category might contain articles about
animals in general as well as sub-categories for articles on different
types of animal.

Joomla provides a single default category named Uncategorised. Any
article not assigned to a specific category that you have created
becomes a member of the Uncategorised category. You create categories as
required to suit the nature of your articles.

An article can only be in one category. In some circumstances that is
not quite enough. Suppose for example you wish to look for books of all
sorts written in a particular language, or all plants that are poisonous
or all animals that are dangerous. That is where Tags come in useful.
They are covered elsewhere.

### Using Categories

In the administrator *Articles* page the *Filter Options* form has a 
**- Select Category -** drop-down list that displays a category tree
allowing you to filter for articles in a selected Category. You can
also create *Category Blog* and *Category List* menu item types to display
articles from a selected category to site visitors.

## Adding Categories and Sub Categories

There are several routes to the *Articles: New Category* page:

- Via the **Home Dashboard** Select the **plus (+) symbol** to the right of 
  the *Articles Categories* link. The latter leads to the *Articles: Categories*
  list page.
- Via the **Administrator Menu** Select the *Content* item to expand the list 
  and then select the **plus (+) symbol** to the right of the *Categories* 
  link.
- Via the **Content Dashboard** Select the Dashboard icon to the right of the
  *Content* link in the Administrator menu and then in the dashboard *Content*
  panel select the **plus (+) symbol** to the right of the *Categories* link.
- Via **Articles: Categories** Follow any of the routes to the list page and
  select the **New** button in the Toolbar.

The following screenshot shows the Home Dashboard *Article Categories* link to 
the list of categories and adjacent *Plus Symbol* that leads to the 
*Articles: New Category* form.

![The add category icon highlighted in the home dashboard](../../../en/images/articles/category-add-via-home-dashboard.png)

## The Articles: New Category form

![The articles new category edit form](../../../en/images/getting-started/article-category-edit.png)

The screenshot above shows the form completed, There are only two fields that
need some content. Everything else has default or null values that you can leave
for now and fill in later as the need arises.

- **Title** This is the only compulsory field. It should be short but 
  descriptive of the category.

### The Category tab

- **Description** Although not compulsory, this field can be displayed in site
  category list pages controlled by menu items. You may need to come back and
  update the Description later.
- **Parent** If set to *- No parent -* this new item is a potential parent 
  category for other categories. If another category is selected as a parent
  this new item is a sub-category. 
- **Status** By default, a new category is set to *Published*. You can change a
  category status to *Published*, *Unpublished*, *Archived* or *Trashed*.
  [ToDo] Explain what happens when a Category is Unpublished...
- **Access** By default access is set to *Public*. Other options to
  restrict access are *Guest*, *Registered*, *Special* and *Super Users*.
  [ToDo] Explain how Access to a Category is might be used...
- **Language** In multi-lingual sites setting this to *All* will make the
  new category independent of the site Language. If set to a specific language
  it will only be available on pages using that language.
- **Tags** If you use them, you can add one or more tags to the category.
  Setting tags at category level is a good way to maintain consistency. For this
  tutorial a *Nature* tag was created and used to filter lists to show only
  items related to the tutorials.
- **Note** and **Version Note** Use these to add relevant notes if required.

### The Options tab

Settings in this tab affect the appearance of this Category in site pages.

- **Layout** This refers to placement of content on the page. There may be a
  choice of layouts depending on the component and template in use.
  [ToDo] Examples...
- **Image** You may wish to use an image to act as an icon so this category can
  be instantly recognised in a list of categories. If used for such a purpose
  an *Image Description (Alt text)* is not needed but the  *No Description* 
  check-box should be checked.

### Save & Close

- **Save & Close** To finish editing this category. Or in the dropdown list...
  - **Save & New** Save this category and open a new edit form for a new 
    category. For example, you may wish to start building a category tree by
    adding an *Apes* category with *Mammals* as its parent.
  - **Save to Menu as List** ...
  - **Save to Menu as Blog** ...
  - **Save as Copy** ...

Closing the edit form leads to the **Articles: Categories** list page.

![A categories list filtered by Nature tag](../../../en/images/articles/categories-list.png)

### Save to Menu as List

Selection of this item from the *Save & Close* drop down list will save and 
close the category edit form and open a new menu item form with all the data 
needed to create a *Category List* for this category. You may wish to change 
the *Title*. For example, it could be *Mammal Articles List* to make it
clear that it is likely to be a list of articles.

In the *Page Display* tab try setting the *Show Page Heading* field to *Show*.
That shows *Mammal Articles List* as a bold heading at the top of the page 
giving it an overall more complete appearance.

### Save to Menu as Blog

Selection of this item from the *Save & Close* drop down list will save and 
close the category edit form and open a new menu item form with all the data 
needed to create a *Category Blog* for this category. You may wish to change 
the *Title*. For example, it could be *Mammal Articles blog* so that the latest 
articles on mammals are featured.

In the *Page Display* tab try setting the *Show Page Heading* field to *Show*.
That shows *Mammal Articles Blog* as a bold heading at the top of the page 
giving it an overall more complete appearance.

The following screenshot shows site view of a category blog page in development.

![Mammals category blog page](../../../en/images/articles/article-mammals-articles-blog-site-view.png)

## Tips

- You can also create article categories from within an article.
- Remember that you can only assign an article to one category.
- As both parent categories and sub-categories can have further
  sub-categories, plan and organise categories carefully. A complicated
  category hierarchy can become a challenge to manage.
- Another method of grouping content in Joomla is the use of the
  **Tags** Component allowing you to add multiple tags to your articles.
  Using categories and tags can help minimise the number of
  sub-categories and provides an efficient way to structure website
  content and provide visitors with more features to navigate 
  website content.
