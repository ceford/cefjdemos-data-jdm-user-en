<!-- Filename: J4.x:How_To_Use_Content_Tags_in_Joomla / Display title: Content Tags -->

## Introduction

Tags provide an easy to use and efficient way to organise and display content. 
The **Tags Component** allows tags to be used across different content types 
including articles, categories, contacts and newsfeeds. It also provides for  
creation of parent and child tags.

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

When tags are created they will display as links in the tagged items.  
The tag styles and positions are defined by the site template. They are often 
styled as buttons or labels.

Tag display may be turned off! This may seem illogical but it is a useful 
feature where tags are used, for example, to filter content for specific use 
cases.

## The Tags List

- Select **Components → Tags** from the Administrator menu.

![the tags list page](../../../en/images/tags/tags-list.png)

However tags are created, they can be found in this list.

## Adding Tags

### Via the Tags List

Select the **New** button in the Tags list Toolbar.

![new tag named predator](../../../en/images/tags/new-tag-predator.png)

- **Title** This is the only *required* field. 
- **Alias** This is created from the Title on save.
- **Description** It is always best to add a Description. It is displayed in 
  Administrator forms and can be helpful when a lot of tags are in use.
- **Parent** Leave set to *None* id this is a root parent tag. Or choose a 
  parent tag from the list if this is a child tag.
- **Status** This field is set to *Published* by default. It can be set to 
  *Unpublished*, *Archived* or *Trashed*.
- **Access** The Access level is Public by default.
- **Note** and **Version Note:** If required you can add notes.
- **Save & Close** The new tag will appear in the Tags List. If you are 
  creating multiple tags you can choose to click **Save & New** instead to 
  create another.

Once saved the tag will be available for use across the various content
types that use them.

### From within an Article

It is possible to add new tags whilst creating or editing an article. In
the article Content tab **Tags Field** enter the name of the new tag and
press **Enter** to save and assign the tag to the article.

### From within a Category

Tags can be added when creating or editing category. In the **Category** tab
enter the tag name in the **Tags Field** and press **Enter** to create
and assign the new tag.

### From within a Contact

Tags can be added when creating or editing a Contact. In the **New/Edit Contact**
tab enter the tag name in the **Tags Field** and press **Enter** to
create and assign the new tag. You can also add new tags when creating
Contact Categories.

### From within a Newsfeed

Tags can be added when creating or editing a new Newsfeed. In the 
**New/Edit News Feed** tab enter the tag name in the **Tags Field** and press
**Enter** to create and assign the new tag. You can also add new tags when 
creating Newsfeed Categories.

## Managing Tags

Wherever you add new Tags within Joomla, they will all appear in the Tags list.
Use the Tags list to find, open and adjust tag settings.

### The Tags List Filter

![tags list filter by type](../../../en/images/tags/tags-list-filter.png)

You can manipulate the list in a number of ways:

- Search for a tag by using some or all of its title in the Search field.
- Reorder the list using drag and drop to optimise the output order.
- Publish or Unpublish tags using the button in the Status column.
- Select one or more tags and use the **Actions** button to Publish, Unpublish, 
  Archive, Check-in or Trash the selected tags.
- Select one or more tags and use the **Actions → Batch** button to set the
  Language or Access Level.

### Tag Settings

 - Select a tag **Title** to make changes to a its settings.

In the tag Edit form:

- The **Tag Details** tab settings were covered above.
- The **Options** tab:
  - Change the layout of the tag's page (the page that appears when you
    click on the tag link - for example, mysite.com/tags/my-tag). This
    layout is normally the default setting and template dependant.
  -  Add a CSS Class to apply a different style (appearance) to the link
    for the tag. This would normally only be used by the Site
    Administrator.
  - Set images for the tag - a teaser image for the tag list and/or a
    full image for the tag page.
- The **Publishing** tab: Set Metadata for the tag page for Search Engine 
  Optimisation (SEO).

## How Joomla Outputs Tags

Once tags have been created on your site they are available for use not
only in content but also in some useful modules such as **Popular Tags** and
**Similar Tags**. The following examples show how these look on a
standard installation using the default **Cassiopeia** Template.

![tags usage site example yellow labrador](../../../en/images/tags/tag-examples-yellow-labrador.png)

When you click on one of the tags you will be taken to a page that lists
all items assigned to that particular tag:

![tags usage site example black labrador](../../../en/images/tags/tag-examples-black-labrador.png)

Clicking a tag will take you to a page that outputs a list of all items
assigned with that particular tag - in effect it is a filtered list of
your tagged website content. A filter box is provided to make it easier
to find items as the list grows. You can also set the number of results
you want to see in a single view.

## Tags Configuration

Individual tags inherit settings from the Tags component options. It is
covered in a separate tutorial. [ToDo] Select the **Options** button in the 
Tags list page Toolbar.

Tags Component configuration can be overridden at menu item level.

## Tips

- Remember that Tags are used across multiple content types
- You can add more than one Tag to an item
- Use the Help button when unsure
