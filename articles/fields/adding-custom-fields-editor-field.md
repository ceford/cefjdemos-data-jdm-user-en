<!-- Filename: J3.x:Adding_custom_fields/Editor_Field / Display title: Editor Field -->

## Purpose

The Editor field allows WYSIWYG data entry for some article related content in
addition to the main content.

## Field Creation

Special options within this field are

- **Buttons** Show or Hide the CMS Content dropdown list. For article
supplementary text it may not be appropriate to show some or all of the
buttons in the list. The plugin default is Hide.
- **Hide Buttons** If *Buttons* is set to *Yes* or the plugin default is *Show*
hide selected buttons in the CMS Content dropdown list.
- **Width and Height** values include space occupied by the editor toolbar so
they are probably best left empty initially.
- **Width** The value for width defines the width of the WYSIWYG editor in % or
pixels. The default value is 100%.
- **Height** The value for height defines the height (in pixels) of the WYSIWYG
editor. Default value for this is 250px. The value can be represented as a
fraction of the viewport height, for example 50vh.
- **Filter** Allow the system to save certain html tags or raw data.

![Editor field creation](../../../en/images/fields/fields-editor-edit.png)

**Note:** In this example, inclusion of the field type in the Title is for
demonstration purposes only. Leave it out in your own field titles.

## Data Entry

In the Article edit form the supplementary Editor field is similar to the main
content Editor field.

![editor field data entry](../../../en/images/fields/fields-editor-data-entry.png)

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

In the Article display the entered text appears below the heading but part of
the bullet list for that field item.

Look for the **Cultivation Notes** item.

![editor field site display](../../../en/images/fields/fields-editor-site.png)
