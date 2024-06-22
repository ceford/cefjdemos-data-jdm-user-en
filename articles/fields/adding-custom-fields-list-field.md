<!-- Filename: J3.x:Adding_custom_fields/List_Field / Display title: List Field -->

## Purpose

The list form field type provides a drop down list or a list box of
custom-defined entries. If the field has a saved value this is selected
when the page is first loaded. If not, the default value (if any) is
selected.

## Field Creation

Special options within this field are:

- **Multiple** Allow multiple values to be selected. If set to *No* one item is
displayed in the list. If set to *Yes* three items are displayed. The list
scrolls to allow any one or more items to be selected.
- **List values** Add items as required and use the drag icon to change their
order. Start the list with Text set to *- Select -* and Value empty. This
provides an empty default resulting in this list being absent from the Article.
- **Field Class** Set to *w-auto* to make the list just wide enough for its
list of labels.

![List field creation](../../../en/images/fields/fields-list.png "List Field Creation")

## Data Entry

Simple: just select an item from the list or more items if *Multiple* is *Yes*.

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

The output is a single item or a comma separated list.

Look for the **Origin** item.

![Display of all fields](../../../en/images/fields/fields-display.png "Fields display")
