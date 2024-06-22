<!-- Filename: Help4.x:Components_Version_History / Display title: Version History -->

## Description

The Version History screen allows you to manage prior versions of the
item being edited. Version history is available for Articles, Banners and
Clients, Contacts, News Feeds, User Notes, and all Categories.

Each time you save the item with new changes, a new version is created
automatically. You can control how many versions to keep for each item
in the Options for the component. You can also choose to keep one or
more versions forever. If so marked, these versions will not be deleted
automatically, even if you exceed the maximum number of versions you
have entered in the options.

Note: If you use versioning, custom fields
are not stored in different versions.

## How to Access

Click the **Versions** button on the toolbar while editing the item.

## Screenshot

<img
src="https://docs.joomla.org/images/thumb/6/69/Help-4x-Components-Version-History-screen-en.png/600px-Help-4x-Components-Version-History-screen-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/thumb/6/69/Help-4x-Components-Version-History-screen-en.png/900px-Help-4x-Components-Version-History-screen-en.png 1.5x, https://docs.joomla.org/images/thumb/6/69/Help-4x-Components-Version-History-screen-en.png/1200px-Help-4x-Components-Version-History-screen-en.png 2x"
data-file-width="1610" data-file-height="977" width="600" height="364"
alt="Components Version History screen" />

## Column Headers

- **Checkbox**. Check this box to select one or more items. To select
  all items, check the box in the column heading. After boxes are
  checked, click a toolbar button to take an action on the selected
  items.
- **Date**. The time and date that the version was saved. Clicking on
  this link opens the Preview of that version in a pop-up window. Note
  that one of the dates will be followed by a star symbol. This
  indicates that this is the version that is currently saved and being
  edited.
- **Version Note**. When you edit an item, you have the option to enter
  in a Version Note. This can be used to help you remember which version
  has which information. If you entered a Version Note before saving the
  item, it will show in this column.
- **Keep Forever**. This column shows whether you have marked the
  version as Keep Forever. Normally, each version will be retained
  according to the settings in the component options screen. The default
  settings are to keep a maximum of 10 prior versions for an item. In
  this case, when you save an item that already has 10 saved versions,
  the oldest version is deleted. If a version is marked as Keep Forever,
  it will not be counted as one of the saved versions and will not be
  deleted when the maximum number is reached.To toggle the Keep Forever
  on or off, check the version's check box and then click the Keep
  On/Off button in the toolbar.
- **Author**. The user who saved this version.
- **Character Count**. The total characters saved in this version. Note
  that this includes the database column names as well as the actual
  characters typed in.

## Toolbar

At the top of the page you will see the toolbar shown in the
Screenshot above. The functions are:

- **Restore**. The current version of the item is marked with a star to
  the right of the Date. If you wish to restore one of the other saved
  versions, check the check box for the desired version and click on the
  Restore button. The current version of the item will be replaced with
  the selected version, and the edit screen will reload with the
  restored version loaded in the editor.
- **Preview**. To preview a version, either click on the Date column of
  the desired version or check the check box and click on the Preview
  button. A separate browser window will load showing the selected
  version of the item, similar to the screenshot below.

  <img
  src="https://docs.joomla.org/images/thumb/c/cc/Help-4x-Version-History-Help-preview-en.png/600px-Help-4x-Version-History-Help-preview-en.png"
  decoding="async"
  srcset="https://docs.joomla.org/images/thumb/c/cc/Help-4x-Version-History-Help-preview-en.png/900px-Help-4x-Version-History-Help-preview-en.png 1.5x, https://docs.joomla.org/images/thumb/c/cc/Help-4x-Version-History-Help-preview-en.png/1200px-Help-4x-Version-History-Help-preview-en.png 2x"
  data-file-width="1602" data-file-height="1204" width="600" height="451"
  alt="Version History Help preview" />

  When you are done
  viewing the version, close the browser window.
- **Compare**. To compare two versions to see what was changed, click
  the check boxes for each of the versions and click on the Compare
  button. A new browser window will open, as shown in the screenshot
  below.

  <img
  src="https://docs.joomla.org/images/thumb/d/d9/Help-4x-Version-History-Help-compare-en.png/600px-Help-4x-Version-History-Help-compare-en.png"
  decoding="async"
  srcset="https://docs.joomla.org/images/thumb/d/d9/Help-4x-Version-History-Help-compare-en.png/900px-Help-4x-Version-History-Help-compare-en.png 1.5x, https://docs.joomla.org/images/thumb/d/d9/Help-4x-Version-History-Help-compare-en.png/1200px-Help-4x-Version-History-Help-compare-en.png 2x"
  data-file-width="2002" data-file-height="1204" width="600" height="361"
  alt="Version History Help compare" />

  The first column
  is the field name, the second is the older version, the third is the
  newer version, and the last column highlights the differences between
  the two versions.
- **Keep On/Off**. This button allows you to toggle on or off the Keep
  Forever feature for a version. Normally, the oldest version of an item
  will be deleted automatically when the maximum number of versions (set
  in the Options for the component) has been exceeded. If you set the
  Keep Forever property for a version, it will never be automatically
  deleted.
- **Delete**. This button allows you to manually delete one or more
  versions. Check the check box for the versions you wish to delete and
  the click on the Delete button. Note that this does *not* delete the
  item being edited. It only deletes the version history for the item.
