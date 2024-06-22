<!-- Filename: J3.x:Adding_custom_fields/Parameters_for_all_Custom_Fields / Display title: Field Parameters -->

## Field Data Entry Form

There are 16 or more field types available from the Type selection list
in the Field data entry form. Most of the form fields are the same for all
field types but others change for the selected type. This article describes
the common parameters for all fields. The data entry form is also the same
for **Article**, **Contact** and **User** fields and their Category fields.

A Fields list will be empty initially. To get started, for example with
Article fields:
* Select **New** from the Toolbar in the Articles: Fields list.

The form consists of a Title field and four tabs.

## Title

The title is displayed in the *Articles: Fields* list page where it can be
selected to open the field for editing. The title is not displayed when you
create an article or in the frontend. However, the Label may be created from
the Title and it is displayed in the Article data entry form and may be
displayed in the Article display.

### General tab

#### In the left panel:

- **Type** Select one of the 16 field types from the dropdown list. When
you save the field this type is permanent. You can not change it later.
- **Name** The name will be used to identify the field. Leave this blank and
Joomla will fill in a default value from the title.
- **Label** Use a descriptive label for the field. This text is not
translatable. If you do not enter any text for a label the title text will
used as label text.
- **Description** Text that will be shown as a tool tip to describe the
purpose of the field during data entry. This text is not translatable and
will not be displayed in the frontend.
- **Required** Set to *Yes* if this is this a mandatory custom field that has
to be filled before submitting an article.
- **Only Use In Subform** Explanation required
- **Default Value** Set a default value if appropriate. This text is not
translatable.
- **Filter** Choose one of the available options from the dropdown list. More
explanation required.
- **Maximum Length** Set this to limit the length of text data that can be
entered.

### In the right panel:

- **Status** Set a publication state selected from *Published*, *Unpublished*,
*Archived* or *Trashed*.
  - Published: The field is visible while editing an article or an
    contact. And it is visible in the Frontend.
  - Unpublished: The field is will not be visible to users while editing
    an article or an contact.
  - Archived: The field will no longer show on edition an article or an
    contact. You can open it in the field manager when you set the
    filter to archived.
  - Trashed: The field is deleted but still in the database. It can be
    permanently deleted from the database with the Empty Trash function
    in Field Manager.
- **Field Group** Select None or a Group selected from a predfine list. Groups
appear as separate tabs in the Article data entry form.
- **Category** You can assign a field to one or more field categories. Note
  that the default 'All' does not include 'uncategorised' articles.
- **Access** The viewing Access Level for this field.
- **Language** Select the language for this custom field. If you are not using the
  multi-language feature of Joomla, keep the default of *All*.
- **Note** An optional field to make your personal notes for the field.

### Options tab

#### Form Options

- **Placeholder** A placeholder text which will appear inside the custom field
as a hint for the input. The placeholder is active in the Backend while
creating an article. You do do not see it in the Frontend.
- **Field Class** The class attributes of the field when the field is rendered.
If different classes are needed, list them with spaces.
- **Label Class (Form)** The class attributes of the field in the edit form. If
different classes are needed, list them with spaces.
- **Editable In** On which part of the site should the field be shown: Site,
Administrator or Both.
- **Showon Attribute** Conditionally show or hide the field depending on the
value of other fields. The syntax to use here, for example:
  - `list-of-items:value1[OR]list-of-items:value2` where
  - list-of-items: The name of an already created field on which this field
depends.
  - value1: The value needed in the list of items field for this field to be shown.
  - [OR] To create a choice among multiple fields. In the example, this field will
show when the list-of-items field has a value of value1 OR value2.
  - [AND] To combine multiple fields. This field will show only when the
list-of-items fields have the value value1 AND value2.
  - You can also use value 'does not equal' as in list-of-items!:value1. The
syntax will show this field only when list-of-items is not equal to value1
  - To show this field when list-of-items field has been selected and does not
have an empty value, use the syntax list-of-items!: (without a value specified).
  - Note: Subform fields handle the list-of-items name differently.
If you create a Subform field and you add this conditional field for a field
you are creating there, you need to use field[ID] instead of list-of-items,
where ID is the id of the field list-of-items. Therefore, the showon
attribute for this conditional field you are creating needs to be:
field36:value1[OR]field36:value2 where 36 is the ID of the field 'List of items'.
This needs clarification!

#### Display Options

- **Display Class**  The class of the field container in the output.
- **Value Class**  The class of the field value in the output.
- **Label** Show or Hide the label.
- **Label Class(Output)** The label output class if the label is displayed.
- **Automatic Display** Joomla offers some content events which are triggered
during the content creation process. This is the place to define how the custom
fields should be integrated into content. You can choose 'After Title',
'Before Display Content', 'After Display Content' or 'Do not automatically
display'.
- **Prefix** Fixed text to be displayed before a field, for example £.
- **Suffix** Fixed text to be displayed after a field, for example EUR.
- **Layout** Select a layout from available templates and overrides.
- **Display When Read-Only** Select from Inherit, Yes or No. If the field is
read only (perhaps the user doesn't have the access level) should the field
be displayed or hidden.

#### Smart Search

- **Search Index** Select from list of options. Warning: When 'Make searchable'
is selected, content from the field is indexed with the viewing permissions of
the content item. This might lead to unexpected information disclosure.

### Publishing tab

Self-explanator set of fields.

### Permissions tab

Self-explanator set of fields.
