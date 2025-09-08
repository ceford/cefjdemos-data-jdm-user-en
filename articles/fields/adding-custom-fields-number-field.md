<!-- Filename: localhost / Display title: Number Field -->

## Purpose

The Number field provides a method to enter a real number with an option to attach a currency or other symbol before or after the number. The control allows for use as an integer field with increment and decrement arrows with a default range of 1 to 100. However, real values, positive or negative can be entered into the field. Example: `99.99` could be formatted to appear as `£99.99` to the end user. Or `-273.15` could appear as `-273.15C` to the end user.

## Field Creation

### General tab

![Number field creation](../../../en/images/fields/fields-number-edit.png)

- **Type** Number, which cannot be changed after selection.
- **Name** The unique name of the field.
- **Label** A translatable label for the field.
- **Description** An optional translatable field description.
- **Required** Set to *Yes* if this field is required?
- **Only Use in Subform** *Yes or *No*.
- **Default Value** An optional default value.
- **Minimum** Minimum value that can be chosen using the up/down arrows, default is 1. 
- **Maximum** Maximum value that can be chosen using the up/down arrows, default is 100. 
- **Step Increment** The size of the increment added or subtracted to current field value using the up/down arrows.
- **Format as Currency** If selected there are additional fields:
    - **Currency Symbol** This can be a single symbol, such as `£` or `$`, or a character string, such as `&deg;C` which appears as *&deg;C*.
    - **Symbol Position** Select *Before* or *After* the number.
    - **Number of Decimels** Typically 2 for currencies but could be something else in other contexts.

### Options tab

#### Form Options panel:

- **Placeholder**  Placeholder text which will appear inside the field as a hint to the user for the required input.
- **Field Class** An optional class added to the data entry form field.
- **Label Class** An optional class added to the data entry form label.
- **Editable In** Allowed editing interfaces: *Site*, *Administrator* or *Both*. 
- **Showon Attribute** Conditionally show or hide the field depending on the value of other fields. 

#### Display Options panel:

- **Display Class** The class of the field container in the output.
- **Value Class** The class of the field value in the output.
- **Label** *Show* or *Hide* the label in the out put. If set to Show:
    - **Label Class (Output)** A class for the output label.
- **Automatic Display** Whether and where to display the field:
    - **After Title**
    - **Before Display Content**
    - **After Display Content**
    - **Do not automatically display**
- **Prefix** Text that will appear before the field value.
- **Suffix** Text that will appear after the field value.
- **Layout** a list of available layouts.
- **Display When Read-Only** Choice of *Inherit*, *Yes* or *No*.

#### Smart Search panel

- **Search Index** Choice of search or not and search method.

### Publishing and Permissions tabs

The content of these tabs are self-evident and covered elsewhere.

## Data Entry

Data entry: simply type in the value you want. This example is the boiling point of Argon:

![Number field data entry](../../../en/images/fields/fields-number-data-entry.png)

## Data Display

The following image shows the display of an item with a negative value:

![Number field site display](../../../en/images/fields/fields-number-site.png)
