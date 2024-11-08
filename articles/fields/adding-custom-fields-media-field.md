<!-- Filename: J3.x:Adding_custom_fields/Media_Field / Display title: Media Field -->

## Purpose

The Media Field allows insertion of an image from a specific directory. Upload
is allowed for users with appropriate permissions.

## Field Creation

Special options within this field are:

- **Directory** The image directories available for this field. The default is
the site /images directory. The list contains the subdirectory tree of the
images directory. Select the directory containing the images you wish to use
for this field. Only one directory may be selected.
- **Preview** Shows or hides the thumbnail preview of the selected image.
- **Image class** The class added to the img tag on output. A class of *w-25*
will reduce the width of the image to 25% of its parent container.

![media field creation](../../../en/images/fields/fields-media-edit.png)

**Note:** In this example, inclusion of the field type in the Title is for
demonstration purposes only. Leave it out in your own field titles.

## Data Entry

The data entry form is a simple version of the Media  select fotm.

![media field data entry](../../../en/images/fields/fields-media-data-entry.png)

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

![media field site display](../../../en/images/fields/fields-media-site.png)
