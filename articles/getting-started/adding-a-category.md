<!-- Filename: J4.x:Getting_Started:_Adding_a_Category / Display title: Adding a Category -->

## Introduction

Website owners with more than a handful of articles should think about
how best to present content for ease of navigation. For example, if you
have a zoo, a museum, a mineral collection or just a large garden you
may have perhaps 1000 specimens to describe. One article for each
specimen, with photographs, needs some organisational structure. If the
articles were files you would probably put them in a file hierarchy. In
a CMS, articles are not files but categories provide for a similar
tree-like structure. Example :

| Category   | Sub-categories                         |
|------------|----------------------------------------|
| Mammals    | Apes, Monkeys, Ungulates, Dogs, Cats   |
| Reptiles   | Snakes, Lizards, Crocodiles, Turtles   |
| Amphibians | Frogs, Toads                           |
| Birds      | Raptors, Ducks, Gulls, Finches, Tits   |
| Arthropods | Spiders, Butterflies, Bees, Locusts    |
| Fish       | Sharks, Salmon, Cod, Herring, Mackerel |

Sub-categories may have further sub-categories too. A maximum manageable depth
seems to be about seven. For the table above, a museum might add more 
parent categories:

```text
nature -> life -> animals -> mammals...
nature -> life -> plants -> trees...
nature -> minerals...
history -> egypt...
science -> astronomy...
science -> chemistry...
```

Imagine how many specimens a national or small town museum holds!

## Menu Item Types

There are several menu item types designed to work with Categories:

- **Category Blog** This is a page layout that has one or two leading
  article tasters, often full page width, then several more article tasters in
  two or three columns, and finally a pagination mechanism to link to
  more articles in the same category. The taster is the content before
  a page-break, often the first one or two paragraphs. A site *Home* page is 
  often a category blog that includes *All Categories*. A *Featured Articles* 
  layout is similar to a category blog and often used as a Home page too.
- **Category List** This is a list layout that displays a list of
  articles in a category. It can be displayed with a Search filter to allow
  searching for articles by Title, Author, Hits, Tags or Month published.
- **List All Categories in an Article Category Tree** This layout lists a 
  category tree starting from a chosen parent. Each branch is collapsible and
  is most useful for large, complex category tree structures.

Menu items are covered in a later article.

## Create a Category

The following example uses a Mammals category inspired by the list above to
demonstrate how to create a new Category:

![Category edit form](../../../en/images/getting-started/article-category-edit.png)

- Select the **Content** item from the Administrator menu to expand it.
- Select the **+** icon alongside the *Categories* menu item to open the 
  Category edit form. 
- The **Articles: New Category** form has only one compulsory field:
  the *Title*, in this case *Mammals*.
- The **Description** field is optional but it is best to fill it in as
  it used in some lists. Suggestion:<br>
  *Mammals are warm-blooded animals that give birth to live young.*
- The **Parent** field specifies whether this is a primary category 
  (-No Parent-) or a sub-category selected from the list of categories.
- **Save and Close** to return to the **Articles: Categories** list page.

This category is now available for use with articles.
