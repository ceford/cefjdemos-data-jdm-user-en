<!-- Filename: J3.x:Adding_custom_fields/Url_Field / Display title: Url Field -->

## Purpose

The URL Field provides a URL link to another document. If you would prefer to
use an anchor tag such as `<a href="url">Explantory Text</a>` use a text field.

## Field Creation

Special options within this field are:

- **Schemes** The allowed schemes are HTTP, HTTPS, FTP, FTPS, MAILTO, URL and
FILE. All are allowed by default. Any selected in the list are allowed while
those not selected are disallowed. This is evident during data entry: when an
unselected type is entered, for example http://, there is an error message and
the field is not saved.
- **Relative** Use this option to determine whether or not relative URLs are
allowed.
- **Show URL** If set to *No*, on Article display the URL is replaced with the
words *Visit Site*.

![url field creation](../../../en/images/fields/fields-url-edit.png)

**Note:** In this example, inclusion of the field type in the Title is for
demonstration purposes only. Leave it out in your own field titles.

## Data Entry

Simple: just enter a destination URL.

![url field data entry](../../../en/images/fields/fields-url-data-entry.png)

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

![url field site display](../../../en/images/fields/fields-url-site.png)

The URL follows the field Label.
