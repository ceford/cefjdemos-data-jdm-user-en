<!-- Filename: J3.x:Adding_custom_fields/Color_Field / Display title: Colour Field -->

## Purpose

The Colour field provides a picker for visual selection of a colour. The field
shows the resulting hex value.

## Field Creation

Special options for this field:

- **Field Class** Set to *w-auto* to make the field just wide enough for the
swatch and value.

## Data Entry

You can type in a hex colour value if you know that hex numbers run from 0 to 9
and then a to f and the pairs of numbers are red, green and blue. So #00ff00 is
no red, maximum green and no blue. Or you can use a cursor to select a colour
visually.

![Colour picker](../../../en/images/fields/fields-colour-entry.png "Colour picker")

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

The default data display is the hex colour value, which is not much use. The
easy solution is to create a template override for the fields / color plugin.
Just replace this line:
```
echo htmlentities($value);
```
with these lines:
```
$value = htmlentities($value);
echo '<span style="background-color: ' . $value . ';"> ' . $value . '</span>';
```
And the hex value will be preceded by a swatch with the background colour of
the value.

Look for the **Flower Colour** item.

![Display of all fields](../../../en/images/fields/fields-display.png "Fields display")

