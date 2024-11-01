<!-- Filename: jdocmanual?manual=user&heading=modules&filename=module-styles.md / Display title: Module Styles -->

## Style Concepts

A module data entry form has an **Advanced** tab. Its fields vary with the type
of module and you can see this for yourself by selecting a Menu module and
comparing that with a Login module or Breadcrumbs module. You will see the
following three form fields related to styling:

* **Module Class** is a text field that allows you to add your own CSS class
to the module container tag, usually a `<div>`.
* **Header Class** is a text field that allows you to add your own CSS class
to the Header Tag, by default a `<h3>` tag.
* **Module Style** is a list that allows you to select one from a number of
standard styles. The list contains none, html5, outline, table, card and
noCard. The default is card from the Cassiopeia template styles.

You can try out the *Module Style* options by editing a module and changing
the value to see what it does to the site display.

* **html5** gives `<div class="moduletable ">`
* **none** removes the outer `<div>` completely and also the module `<h3>` tag.
* **outline** gives `<div class="mod_preview_info">`, with position and style
information replacing the module `<h3>` tag.
* **table** gives a table layout starting `<table class="moduletable ">` with
the former h3 tag now a `<th>` tag.
* **card** gives `<div class="sidebar-right card ">`, the default.
* **noCard** gives `<div class="sidebar-right no-card ">`

## The Module Class

At this stage you need to know a little about Cascading Style Sheets or CSS.
If you enter a single word in the Module Class field, say **green** as CSS
classes are by convention all lower case, and with the Module Style set to
**inherited**, the output contains `<div class="sidebar-right card green">`.

There is no visible change in the Site appearance because the class green is
not defined. To define it, make an entry in the template's user.css file.

From the Administrator menu:
* Select **System / Site Templates / Cassiopeia Templates and Files**.
* Select **New File** from the *Toolbar*
* Select **css** in the left column, the destination for the new file.
* Type **user** in the File Name field.
* Select **css** from the File Type list.
* Select the **Create** button.

You can now open the css folder to find and open the user.css file for editing.
Enter these style statements and notice the US spelling of *color*:
```
.sidebar-right.card.green {
    background-color: #ddffdd;
}
.sidebar-right.card.green .card-body {
    background-color: #eeffee;
}
```
The style could have used only `.green` but that might have affected other tags
with that style on other pages.

## The Header Class

Back to the module edit form and add **blue** in the Header Class field. The
module has no visible change on the site but the heading now shows as
`<h3 class="card-header blue">`. Back to edit the user.css file to add an entry
for the heading style:
```
.card-header.blue {
    color: navy;
}
```
The module heading is now in dark blue. There are several ways to specify
colour in CSS. The most common are hexadecimal and standard colour names.
Read all about it elsewhere!

## CSS Challenge

* Change the module border colour to navy!
* Change the heading bottom border too.
* Apply this style to several modules instead of one at a time

![Archived Articles Module Example](../../../en/images/modules/modules-archived-articles.png)
