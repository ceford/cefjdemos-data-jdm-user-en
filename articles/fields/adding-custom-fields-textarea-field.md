<!-- Filename: J3.x:Adding_custom_fields/Textarea_Field / Display title: Textarea Field -->

## Purpose

The Textarea Field an area for entry of multi-line text. A simple textarea does
not have a WYSIWYG Editor.

### Options

Special options within this field are:

- **Rows** The height of the visible text area in lines. If omitted the height
is determined by the browser. The value does not limit the number of lines that
may be entered. The rows are active in the backend while creating an article
or a contact or a third party component that supports custom fields. This
option has no impact on the size of the field in the frontend.
- **Columns** The width of the visible text area in characters. If omitted the
width is determined by the browser. The value does not limit the number of
characters that may be entered. The cols are active in the backend while
creating an article or a contact or a third party component that supports
custom fields. This option has no impact on the size of the field in the
frontend.
- **Maximum Length** The maximum number of characters that can be entered.
- **Filter** Allow the system to save certain html tags or raw data.

## Data Entry

Simple: enter the text to display.

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

Look for the **Classification** item.

![Display of all fields](../../../en/images/fields/fields-display.png "Fields display")

The field label starts a single block of text unless you have entered HTML
tags such as `<p>...</p>`.

