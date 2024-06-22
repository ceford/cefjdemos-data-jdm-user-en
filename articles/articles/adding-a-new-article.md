<!-- Filename: J4.x:Adding_a_New_Article / Display title: Adding a New Article -->

## Introduction

This article covers the methods for adding a new article after logging in
to the Administrator Dashboard and is based on a standard Joomla installation
using the default content editor, TinyMCE.

A new article edit form may be opened from the Home Dashboard or from the
Articles list page. Either of these options will open an article edit
form entitled **Articles: New** ready for input.

### From the Home Dashboard

<img
src="https://docs.joomla.org/images/thumb/4/4e/J4x_add_article_at_home_dashboard-en.png/800px-J4x_add_article_at_home_dashboard-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/4/4e/J4x_add_article_at_home_dashboard-en.png 1.5x"
data-file-width="1000" data-file-height="254" width="800" height="203"
alt="add article from home dashboard" />

1.  In the Administrator Menu select the **Content** link, then from the
    dropdown menu select the **plus (+) symbol** to the right of the
    Articles link.
2.  If it is displayed, in the Home Dashboard Site panel select the
    **plus (+) symbol** to the right of the Articles icon.

### From the Articles list

<img
src="https://docs.joomla.org/images/thumb/2/24/J4x_home_dashboard_add_article_en.png/800px-J4x_home_dashboard_add_article_en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/2/24/J4x_home_dashboard_add_article_en.png 1.5x"
data-file-width="1000" data-file-height="147" width="800" height="118"
alt="add article from articles list" />

1. Select the **New** button in the *Toolbar*.

## Data Entry

The article edit form has tabbed panels. A new article has the **Content**
tab selected by default. Otherwise, the last opened tab is selected.

<img
src="https://docs.joomla.org/images/thumb/0/05/J4x_add_article_basic_en.png/800px-J4x_add_article_basic_en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/0/05/J4x_add_article_basic_en.png 1.5x"
data-file-width="1000" data-file-height="341" width="800" height="273"
alt="new article form" />

It is possible to save a new article with only one piece of required
information, a Title.

1.  Enter a title in the *Title* field. This is **Required** and is used
    wherever the article title is displayed. The *Alias* field next to
    the title field is not a required field as if it is left blank
    Joomla will create the alias when the article is saved. The alias is
    used to refer to the article in internal and external links.

All other fields have default values. Even the Article Text field defaults
to an empty string. However, you will almost certainly wish to fill out
some of the field.

### The Content Tab

The **Content** tab is mostly occupied by the TinyMCE editor where you create
your textual content.

Alongside the content, there are fields to manage publishing, how and where
the article will be displayed and who can see it when published. In many
cases some of these settings may be left at their default values.

<img
src="https://docs.joomla.org/images/thumb/b/bc/J4x_add_article_info_right_en.png/300px-J4x_add_article_info_right_en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/b/bc/J4x_add_article_info_right_en.png 1.5x"
data-file-width="392" data-file-height="629" width="300" height="481"
alt="add article right information panel" />

1.  **Status**: Published, Unpublished, Archived, or Trashed - the default
    is *Published*.
2.  **Category** This is a **Required** field but will default to the
    *uncategorised* category. You can add a new category in this field
    by typing it in and **pressing enter**.
3.  **Featured** Toggle between ***No*** and ***Yes*** to display the article
    on the home page if that uses a Featured Articles layout.
4.  **Access** The access level can be changed to restrict the article to
    specific User Groups: Public, Registered, Super Users, etc.
5.  **Tags** Start typing to find and select pre-defined tags or you can add
    a new one by typing it in and **pressing enter**.
6.  **Note** Any comment on this article which will be visible under the Title
    in the Articles list page.
7.  **Version Note** Add comments to indicate what changed in this version.
    This is displayed in the Versions modal dialog and the field reverts to
    empty after saving.

### Other Tabs

**You may not see all of the following tabs** as a Site Administrator may
hide some to help maintain the consistency of article layout across the
website. You may also see additional tabs for *Custom Fields* if they have
been set up.

1.  **Images and Links** allows you to set an intro and featured image
    and/or links to appear in predefined positions. This may be used if
    your article will be displayed within a category blog.
2.  **Options** allows you to specify the layout of the article and
    associated information such as title, category, tags, publishing
    details etc. This is normally set globally but can be article
    specific through these options.
3.  **Schema** is a method to add metadata to an article. It is used by
    robots but not seen by humans.
3.  **Publishing** allows you to set publishing dates and times to
    schedule publishing of an article. By default, when an article is
    saved it will be published straight away. You can also set the
    Metadata for the article.
4.  **Configure Edit Screen** allows you to show or hide parameters for
    the article.
5.  **Permissions** shows the permissions for each user group that control
    what can or cannot be done.

## Saving the Article

Once you have added the required information and content you can save
the article. There are a number of ways to do this depending on what you wish
to do next in Joomla.

To save the article you can choose to *Save* or *Save & Close*. The latter
has dropdown options to *Save & New*, *Save to Menu* and *Save as Copy*.

<img
src="https://docs.joomla.org/images/thumb/1/1b/J4x_add_article_saving_en.png/300px-J4x_add_article_saving_en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/thumb/1/1b/J4x_add_article_saving_en.png/450px-J4x_add_article_saving_en.png 1.5x, https://docs.joomla.org/images/1/1b/J4x_add_article_saving_en.png 2x"
data-file-width="500" data-file-height="234" width="300" height="140"
alt="article save button" />

1.  Select the **Save** toolbar button to save your changes. This will
    keep the article open. It is good practice to regularly save your
    work on longer articles.
2.  Select the **Save & Close** toolbar button to save the article and
    take you to the Articles list. The Save & Close button has further
    drop-down options:
    * Select **Save & New** to save the article and then open an
    **Articles: New** page. This option saves time when adding multiple
    articles.
    * Select **Save to Menu** to add the article to a menu by opening a
    **Menus: New Item** page.
    * Select **Save as Copy** to save the article then open up an
    **Articles: Edit** page with a number in brackets appended to the title
    and the same number following a dash, -2 for example, in the alias field.
    You can change the title and change or delete the alias of the new article
    which has already been created.

A system message will indicate that the article has been successfully
saved.

### Errors on attempting to save:

- If you have not completed the required fields, a red error message
  will appear indicating the missing information you must add.
- You will see an error message if the article has an alias that already
  exists. You can overcome this by amending the alias field.

## Quick Tips

- If you are not the Super User or Administrator, take time to
  understand how the website is set up. Just because you have saved an
  article doesn't mean it is visible on the website. If Category Blog
  pages are being used, assigning the correct category will display the
  article. Otherwise an article needs to be assigned to a menu item. You
  can do this in the article or via Administrator **Menus** menu.
- Try to keep article titles short and specific.
- Whilst it can be done, if there are several users adding articles to
  the website avoid creating new categories and tags in articles.
  Spelling errors and differences can easily prevent articles from
  displaying where they were intended. Creating categories and tags in
  their respective list page ensures consistency across the website.
- If there is a need, make use of article notes. They can be very
  helpful, especially where several people add articles.
- Wherever you are in Joomla you can add an article without going to the
  Home Dashboard - use the Joomla Administrator Menu.
