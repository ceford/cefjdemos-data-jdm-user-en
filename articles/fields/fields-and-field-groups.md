<!-- Filename: J4.x:Fields_and_Field_Groups / Display title: Fields and Field Groups -->

## Introduction

Fields are used to display additional attributes of Articles, Contacts
or Users. The data are entered in an Administrator Edit form and
displayed in the Site. An example:

Suppose you write articles about aspects of nature, sometimes Flowers,
sometimes Animals. One field you might wish to record and display for
both is the Latin Name, requiring a text field. Another might be
Habitat: Woodland, Pond, Meadow, and so on, requiring a drop-down list.
For flowers you might wish to record Flowering Season using 4 checkboxes,
one for each season, or 12 checkboxes, one for each month.

Empty fields in the input form are not displayed in the Site output, so
you could keep all fields in one long list. However it is usually better
to use categories for your Articles, say Flowers and Animals. Fields can
be assigned to more than one Category. So Latin Name and Habitat fields
would be assigned to both but Flowering Season would only be assigned to
the Flowers category.

If a field is not assigned to a group it will appear in the Edit form in
a Fields tab. If a field is assigned to a group it will appear in a tab
with that name. So for the Flowers group it seems appropriate to create
a field group named Flower Data (or just Flowers, although using the same name
for different things gets confusing). And for the other common fields
you could use a Nature group.

## A Worked Example - Nature Notes

For articles on Nature the article category and sub-categories for each branch 
of the living world might appear as in the following example:

![Article categories for nature](../../../en/images/fields/fields-articles-categories-list.png)

Some obvious features of Nature to note:

- The Nature category is for articles that are about nature in general rather 
  than specific types of plant or animal.
- The sub-categories are for articles that are more specific and they may need
  their own sub-categories.
- All life forms have Common names and Latin Names.
- Flowers and Trees have a Flowering Season, Height and Spread but Birds
  and Mammals do not.
- Birds have Wingspan, and Length whilst Mammals have Height and Length.
- Colour may be constant or varied. 

The point here is that it may be necessary to set up Field or Field Groups for 
common features, such as Latin Name, and separate Field Groups for each category
of nature.

## Field Groups

Creating Field Groups for Articles is very simple: 

- Select **Content → Field Groups** from the Administrator menu
- Select the **New** button in the toolbar. 
- Enter a suitable **Title**.
- Enter a **Description**. This appears beneath the field in the article edit
  form when *Toggle Inline Help* is selected.
- Select **Save & Close** from the toolbar. 

![Content field groups list](../../../en/images/fields/fields-field-groups-list.png)

### Ordering

In the article data entry from the field groups will appear in the order seen
in this list. Drag and drop items to change the order.

## Fields

To create a new article Field select **Content → Fields** from the
Administrator menu and fill in the form. Some examples are illustrated
below.

### Text - Latin Name

Note that in the screenshot below this field has been assigned to the Nature
Field Group and to the Nature category. This ensure that it always appears in 
articles in the Nature category and any sub-category.

![Text field - latin name in nature group](../../../en/images/fields/fields-latin-name.png)

### Checkboxes - Flowering Season

Checkboxes appear in the Article Edit form for you to tick to select the
flowering season. In the article display only those with a tick will be
listed. For example, if you tick Spring and Summer the output will show
Flowering Season: Spring, Summer.

Note that in this screenshot the Field has been assigned to the Flowers
group and to the Flowers Category. That should ensure that the field is
only present in articles bout flowers.

![Checkbox field - flowering season](../../../en/images/fields/fields-flowering-season.png)

### Colour - Color

Just to be confusing, the name of the field type is Color (US Spelling)
but the label in documentation is Colour (British Spelling).

![Colour field](../../../en/images/fields/fields-colour.png)

The Colour field is assigned to the Nature field group and the Nature category
as it is not unique to flowers.

### Integer - Hardiness

The hardiness of a plant can be represented as an integer from 1 to 7. There 
is no field for a real number so length and width could be integers with a scale 
(cm or m or ft) included in the label. There are *Prefix* and *Suffix* settings
in the *Options* tab. If there is no obvious upper limit then leave the *Last:*
field empty.

![Hardiness field](../../../en/images/fields/fields-hardiness.png)

RHS Hardiness is a property usually applied to flowers!

There is a problem with the integer field. It always has a value and so always
appears in the output. You can get around that problem with a template override
for *Plugins / Integer*. For example, you could use a value above or below the
expected limits to omit the field from the output.

## Article Edit Form

When an Articles: New form is opened the default Category is
Uncategorised and the form tabs do not include Fields and Flowers.
Select the Flowers category and the form is reloaded with those tabs
present.

### Nature Tab

![Bluebell article nature tab](../../../en/images/fields/field-article-bluebell-nature-tab.png)

- **Latin Name** The is a text entry field so it is just a matter of typing in
  the latin name of whatever lif-form the article covers. However, the Nature
  category covers life in general as well as specific animals or plants. So this
  is not a *required* field.
- **Color** The colour selection field can take either keyboard entry of a
  hex colour value or a colour selected from the colour chooser tool. The hex
  number is xrrggbb where rr are red values, gg are green values and bb are blue
  values. On output the site displays the hex value, which is not very helpful!

### Flowers Tab

![Bluebell article nature tab](../../../en/images/fields/field-article-bluebell-flowers-tab.png)

- **Flowering Season** The checkbox field - bluebells are well-known Spring 
  flowers so selection of one checkbox is appropriate. 
- **Hardiness** The integer field. There is a problem here - there is no method
  available to leave this field empty. So it is always present in the output,
  even for more general articles on flowers where is is not appropriate. There
  is a workaround involving a template override.

## Site Result

Take a look at the result seen in your site. In this example a single article
menu item was created:

![Bluebell article site view](../../../en/images/fields/field-article-bluebell-site.png)

### The hex Colour

The default data display is the hex colour value, which is not much use. The
easy solution is to create a template override for the fields / color plugin,
which is what is shown in the screenshot above.

Just replace this line:
```
echo htmlentities($value);
```
with these lines:
```
if (is_array($value)) {
  $list = [];
  foreach ($value as $v) {
    $x = htmlentities($v);
    $list[] = '<span class="ps-5 pe-5" style="background-color: ' . $x . ';">&nbsp</span> ' . $x;
    echo implode(', ', $list);
  }
} else {
    $x = htmlentities($value);
    echo '<span class="ps-5 pe-5" style="background-color: ' . $x . ';">&nbsp</span> ' . $x;
}
```
And the hex value will be preceded by a swatch with the background colour of
the value.
