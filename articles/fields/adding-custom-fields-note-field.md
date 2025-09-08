<!-- Filename: localhost / Display title: Note Field -->

## Purpose

The note form field type makes it possible to create titles, texts, descriptions and even alert boxes. It also allows you to bring order in the settings for extensions, by separating them with useful titles. Or adding descriptions for certain settings (without having to rely on the tooltips). Or adding any other text you want.

## Field Creation

### General tab

![Note field creation](../../../en/images/fields/fields-note-edit.png)

- **Type** Number, which cannot be changed after selection.
- **Name** The unique name of the field.
- **Label** A translatable label for the field.
- **Description** An optional translatable field description.
- **Only Use in Subform** *Yes or *No*.
- **Note Heading** This will be seen in the data entry form.
- **Note Content** The text of the note.
- **Note Class** Any existing or new classes. The default *alert alert-info* produces a Boostrap alert box.
- **Heading Tag** Select from the list of heading levels.
- **Show Close Button**  This field controls the display of an "x" to close the note. It takes a value of 'true' (for alerts) or the value for the data-dismiss of the Bootstrap close icon.

### Options tab

- **Automatic Display** Whether and where to display the field:
    - **After Title**
    - **Before Display Content**
    - **After Display Content**
    - **Do not automatically display**
- **Layout** a list of available layouts.
- **Display in Frontend** *Yes* or *No*.

## Data Entry

In the data entry form, the note field appears amongst other fields as text styled according to the style choices set in the field. It might contain instructions or information.

![Number field data entry](../../../en/images/fields/fields-note-data-entry.png)

**Tip:** Use the Field sort mechanism to sort the Note order amongst other fields. You may have several different Note fields to provide structure and information for your fields.

## Data Display

If *Display in Frontend* is set to *Yes* then the Note field appears amongst other fields in the frontend. There it might contain some general information common to a group of articles.

