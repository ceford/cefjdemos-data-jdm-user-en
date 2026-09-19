<!--
{
  "source": "https://docs.joomla.org/J4.x:How_To_Use_Content_Tags_in_Joomla",
  "title": "Content Tags",
  "description": "", 
  "author": ""
}
-->

## Introduction

Tags provide an easy to use and efficient way to organise and display content. 
The **Tags Component** allows individual tags to be used across different 
content types including articles, categories, contacts and newsfeeds. It also provides for creation of parent and child tags.

Unlike Joomla **Categories**, where only one category can be assigned to
an item, multiple tags may be assigned to a single item but it is not a 
requirement to assign tags to items.

Once an item is tagged with a specific tag, clicking the tag button on
content displaying tags will take you to a page that displays a list of
all items that have been tagged with that particular tag. For this
reason, tags are often used as a way to present *filtered* lists of
content.

Tags can be added in several places, giving flexibility in tag creation.

## Considerations

Before starting, consider the purpose of tags on the website, especially
if others will be adding content. Unless they are added and managed
correctly, tags can become counter productive. Common problems include
content writers adding new unnecessary tags and miss-spelled tag names.
Some Site Administrators may choose to change Access permissions so that 
only specific users can add new tags.

The following screenshot shows tags used on a site containing articles on 
UNESCO World Heritage Sites. In this case each tag has a distinctive colour. 

![the tags list page](../../../en/images/tags/content-tags/01-tags-example.png)

When tags are created they will display as links in the tagged items. 
The tag styles and positions are defined by the site template. They are often 
styled as buttons or labels.

Tag display may be turned off for individual articles or all articles! This 
may seem illogical but it is a useful feature where tags are used, for 
example, to filter content for specific use cases.

## The Tags List

- Select **Components → Tags** from the Administrator menu.

This screenshot shows tags in a structure used for a multilingual site.
Each language has a list of tags with a language tag as the parent. 
The parent tag is used in the *Popular Tags* and *Similar Tags* modules.

![the tags list page](../../../en/images/tags/content-tags/02-tags-list.png)

However tags are created, they can be found in this list.

- Select the **New** button in the Toolbar to create a new tag.
- Select a tag **Title** to edit an existing tag.

### The Tag Details tab

![tag edit form options tab showing bootstrap css classes](../../../en/images/tags/content-tags/03-edit-tag-details-tab.png)

- **Title** This is the only *required* field. 
- **Alias** This is created from the Title on save.
- **Description** It is always best to add a Description. It is displayed in 
  Administrator forms and can be helpful when a lot of tags are in use.
- **Parent** Leave set to *None* if this is a tag that has no parent. Or choose a 
  parent tag from the list to make this a child tag.
- **Status** This field is set to *Published* by default. It can be set to 
  *Unpublished*, *Archived* or *Trashed*.
- **Access** The Access level is Public by default.
- **Note** and **Version Note:** If required you can add notes.
- **Save & Close** If you are creating multiple tags you can choose to select **Save & New** to create new tag.

### The Options tab

- **Layout** There may be several layouts to choose from and you can create your own layout with a template override.
- **CSS Class for tag link** By default, tags are displayed as a blue button. You can enter class statements here to customise tag appearance to give different tags different colours. Example: `bg-danger-subtle border border-danger` are Bootstrap classes that produce a pink button with a red border.
- **Teaser Image and Full Image** Set images for the tag - a teaser image for the tag list and/or a full image for the tag page.

![tag edit form options tab showing bootstrap css classes](../../../en/images/tags/content-tags/04-edit-tag-options-tab.png)

### The Publishing tab

- Set Metadata for the tag page for Search Engine Optimisation (SEO).

## Alternative Creation Methods

### From within an Article

It is possible to add new tags whilst creating or editing an article. In
the article Content tab **Tags Field** enter the name of the new tag and
press **Enter** to save and assign the tag to the article.

### From within a Category

Tags can be added when creating or editing category. In the **Category** tab
enter the tag name in the **Tags Field** and press **Enter** to create
and assign the new tag.

### From within a Contact

Tags can be added when creating or editing a Contact. In the 
**New/Edit Contact** tab enter the tag name in the **Tags Field** and press 
**Enter** to create and assign the new tag. You can also add new tags when creating Contact Categories.

### From within a Newsfeed

Tags can be added when creating or editing a new Newsfeed. In the 
**New/Edit News Feed** tab enter the tag name in the **Tags Field** and press
**Enter** to create and assign the new tag. You can also add new tags when 
creating Newsfeed Categories.

## Managing Tags

Wherever you add new Tags within Joomla, they will all appear in the Tags list.
Use the Tags list to find, open and adjust tag settings.

You can manipulate the list in a number of ways:

- Search for a tag by using some or all of its title or alias in the Search field.
- Reorder the list using drag and drop to optimise the output order.
- Publish or Unpublish tags using the button in the Status column.
- Select one or more tags and use the **Actions** button to Publish, Unpublish, 
  Archive, Check-in or Trash the selected tags.
- Select one or more tags and use the **Actions → Batch** button to set the
  Language or Access Level.

## Tag Outputs

Once tags have been created on your site they are available for use in content and in modules such as **Popular Tags** and **Similar Tags**. The following examples show how these might look on a site using the default **Cassiopeia** Template.

![tags displayed in an article and popular tags and similar tags modules](../../../en/images/tags/content-tags/05-tag-modules-site-view.png)

When you select one of the tags you will be taken to a page that lists
all items assigned to that particular tag:

![tags usage site example black labrador](../../../en/images/tags/content-tags/06-items-with-cultural-site-tag.png)

The list of items is a filtered list of website content with the selected tag.
A filter box is provided to make it easier to find items as the list grows. 
You can also set the number of results you want to see in a single view.

## Tags Configuration

Individual tags inherit settings from the Tags component options. Select the 
**Options** button in the Tags list page Toolbar to see the available default 
tag options.

The Tags Component configuration options can be overridden at the content item and/or menu item levels.

## Tips

- Remember that Tags are used across multiple content types.
- You can add more than one Tag to an item.
- Use the Toolbar Help button when unsure.
