<!-- Filename: Help4.x:Components_Version_History / Display title: Article: Versions -->

## Introduction

In the Joomla article edit form, each time an article is saved a new version 
is created automatically. The number of versions to keep for each article can
be set in the *Articles: Options* page, *Editing Layout* tab. The default is 10.
Not that this is not the *Options* tab of the *Articles: Edit* page. The current
version is usually the last version saved.

One or more versions can be marked to *Keep Forever*. Such versions will not be 
deleted automatically, even if the maximum number of versions is exceeded.

The *Versions* popup dialog is used to manage prior versions of the
item being edited. Similar Version histories are available for Articles, 
Banners and Clients, Contacts, News Feeds, User Notes, and all Categories.

Note: Custom fields are not stored in different versions.

## How to Access

Select the **Versions** button on the Toolbar while editing the item.

## Screenshot

![Versions popup dialog](../../../en/images/articles/articles-versions.png)

## Column Headers

- **Checkbox** This checkbox is used to select or deselect all visible versions
  in the list. If any checkbox is selected the Toolbar buttons are activated
  and can be used to take an action on the selected items.
- **Date** The time and date that the version was saved. Clicking on
  this link opens a Preview of that version in a pop-up window. Note
  that one of the dates will be followed by a star symbol. This
  indicates that this is the version that is currently saved and being
  edited.
- **Version Note** When you edit an item, you have the option to enter
  a Version Note. This can be used to help you remember which version
  has which information. If you entered a Version Note before saving the
  item, it will show in this column.
- **Keep Forever** This column shows whether you have marked the
  version as Keep Forever. Normally, each version will be retained
  according to the settings in the component options page. The default
  settings are to keep a maximum of 10 prior versions for an item. In
  this case, when you save an item that already has 10 saved versions,
  the oldest version is deleted. If a version is marked as Keep Forever,
  it will not be counted as one of the saved versions and will not be
  deleted when the maximum number is reached.To toggle the Keep Forever
  on or off, check the version's check box and then select the *Keep On/Off*
  button in the toolbar.
- **Author** The user who saved this version.
- **Character Count** The total number of characters saved in this version. 
  This includes the database column names as well as the item characters.

## Toolbar

At the top of the page you will see the toolbar shown in the
Screenshot above. The functions are:

- **Restore** The current version of the item is marked with a star to
  the right of the Date. If you wish to restore one of the other saved
  versions, check the check box for the desired version and select the
  *Restore* button. The current version of the item will be replaced with
  the selected version, and the edit screen will reload with the
  restored version loaded in the editor.
- **Preview** To preview a version, either select the item in the Date column 
  or check the check box and click on the Preview button. A separate browser 
  window will load showing the selected version of the item, similar to the 
  screenshot below. After viewing the version, close the browser window.
![Versions preview dialog](../../../en/images/articles/articles-versions-preview.png)
- **Compare** To compare two versions to see what was changed, click
  the check boxes for each of the versions and click on the Compare
  button. A new browser window will open, as shown in the screenshot
  below. The first column is the field name, the second is the older version, 
  the third is the newer version, and the last column highlights the differences 
  between the two versions.
![Versions compare dialog](../../../en/images/articles/articles-versions-compare.png)
- **Keep On/Off** This button allows you to toggle on or off the Keep
  Forever feature for a version. Normally, the oldest version of an item
  will be deleted automatically when the maximum number of versions (set
  in the Options for the component) has been exceeded. If you set the
  Keep Forever property for a version, it will never be automatically
  deleted.
- **Delete** This button allows you to manually delete one or more
  versions. Select the check box for the versions you wish to delete and
  then select the Delete button. Note that this does *not* delete the
  item being edited. It only deletes the selected version of the item.
