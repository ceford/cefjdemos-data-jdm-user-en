<!-- Filename: jdocmanual?manual=user&heading=fields&filename=subform.md / Display title: Subform Field -->

## Purpose

The Subform Field allows a selection of fields to be grouped together in a
repeatable list.

## Field Creation

First create the fields needed in the subform. In the example described here
there is a Calendar field (Acquisition Date), a Text field (Price) and a Color
field (Flower Colour) to be used for a list of several specimens.

**Bug:** There is a bug in the Calendar field code that leads to a fatal error
when saving an article a second time. To avoid this problem set the Calendar
field *Show Time* value to *Yes*.

Special options for this field:

- **Title** and **Label** In this example these are set to *Specimens*.
- **Fields** Add the fields required in the subform one by one. Each row
has a dropdown list of available field and a Render Values Yes/No toggle.
The item order can be changed with the drag icon.

![Subform creation](../../../en/images/fields/fields-subform.png "Subform creation")

## Data Entry

In the data entry form you need to add rows for each specimen. Each row
contains a Calendar field, a Text field and Colour field.

![Subform data entry](../../../en/images/fields/fields-subform-entry.png "Subform data entry")

## Data Display

In the Article, the subform entitled Specimens has one row for each specimen.
Look for the **Specimens** item in this screenshot:

![Display of all fields](../../../en/images/fields/fields-display.png "Fields display")

