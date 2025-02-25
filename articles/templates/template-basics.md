<!-- Filename: J4.x:Template_Basics / Display title: Template Basics -->

## Introduction

In Joomla! a template is a collection of files that together define the
website appearance. Joomla 4 provides two templates: Atum is the
Administrator template used for site management; and Cassiopeia is the
Site template used for site visitors. Many more site templates are
available from independent suppliers, either free or for a modest
charge. Indeed there is a whole industry based on the provision of
specialist site templates.

A typical site template contains PHP files to lay out the content and
CSS files to style the content. There are often additional files such as
images used in the layout and JavaScript files used to interact with
site features such as links and buttons. The following screenshot shows
the Cassiopeia template folders and files in a new Joomla 4
installation:

![templates customise cassiopeia page](../../../en/images/templates/templates-customise-cassiopeia.png)

Note the the php files are in the site /templates folder and the media
files are in the site /media folder.

## Template Positions

The site template defines the positions of the main content, for example
an individual article or a blog layout of featured articles, and any
modules to be displayed above, below, to the left or to the right of the
main content. The following illustration shows the positions available
in Cassiopeia:

![template positions diagram](../../../en/images/templates/cassiopeia-template-positions.png)

Also, you can see the template positions in any template by setting
Preview Module Positions to Enabled in the Template: Options form and
then appending ?tp=1 to the url. If there is already a query string
appended to the url then append &tp=1 instead.

## User Styling

Cassiopeia has some options that you can change to alter site appearance
(there is a separate article on Cassiopeia Customisation). That may not
be enough for your purposes. You can make your own changes to appearance
with a user.css style sheet. You have to create this yourself in the
Templates:Customise form. Just select New File and enter File Name:
user, select File Type: .css, and select css from the list of folders.
Then select the newly created user.css file in the Edit form and enter
some styles, for example, to make headings dark green:
```css
    h1, h2, h3, h4, h5, h6 {
      color: darkgreen;
    }
```
## Template Overrides

In addition to the overall layout defined by the site template, each
component or module has a template to define its appearance within the
overall layout. Such templates are located in a tmpl folder within the
component or module. Some plugins also have templates. And there are
layouts that may be called from any type of extension.

Sometimes one of these *extension* templates is not quite to your
liking. In which case you can create a template override. This is a copy
of the code used to generate the extension layout for you to change to
suit your own purposes. The following screenshot shows the Template:
Customise Create Overrides form:

![template overrides](../../../en/images/templates/cassiopeia-customisation-create-overrides.png)

Cassiopeia has some overrides already installed. That may seem to be a
problem. If you change any of the default Cassiopeia files your changes
will be overwritten (hence lost) at the next Joomla update. The solution
is child templates.

## Alternative Layouts

A template, or a template override, defines the appearance of an
extension in a specific file, such as default.php. In some cases you may
wish to choose between the default layout and an alternative layout. For
example, a menu in a top position usually needs a different layout from
the same menu in a side position. In a menu module there is a Layout
parameter in the Advanced tab of the module edit form that allows you to
select from available alternative layouts. There is a separate tutorial
on Template Alternative Layouts.

## Child Templates

A child template uses the files in its parent template except for any
files that are in the child template. For example, you could have
different user.css files in parent and child so that different pages
could have different colour schemes. Or you could copy the index.php
file from the parent to the child and change the child to produce a
different layout from the parent. There is a separate tutorial on child
templates.
