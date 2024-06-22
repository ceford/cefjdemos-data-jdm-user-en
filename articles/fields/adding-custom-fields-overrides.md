<!-- Filename: J3.x:Adding_custom_fields/Overrides / Display title: Template Overrides -->

## Field Automatic Display

Each of the available fields has an option labelled *Automatic Display* which
may be set to one of the following:

* After Title
* Before Display Content
* After Display Content
* Do not automatically display

If the last of these items is selected then the field is not displayed unless
you create a template override to handle the display yourself. Or you could add
`{field ID}` in an article to place the field wherever you like. But you have
to remember to do this in every article.

This example shows how to create a template override for a Contact. The
methods also apply to Content and User components.

## Create a Template Override

From the Administrator menu:

* Select **System / Site Templates / Cassiopeia Details and Files**
* Select the **Create Overrides** tab.
* Select **com_contact** from the *Components* panel
* Select **Contact** from the list of available views. This is the layout for
a single contact.

In the **Editor** panel:
* Select **html / com_contact / contact / default.php** which is the file
that sets the overall layout of the single contact page.
* Scroll dowm this file and notice a series of `<php if (...) : ?>` blocks.
Each will show or hide a section of text depending the contact settings.
* Notice the lines containing
```
    <?php echo $this->item->event->afterDisplayTitle; ?> (line 73)
    <?php echo $this->item->event->beforeDisplayContent; ?> (line 98)
    <?php echo $this->item->event->afterDisplayContent; ?> (line 189)
```
One of these variables, or none of them, is populated depending on the value of
the Automatic Display field.

## Using fields in your override

You have all the fields corresponding to the current item accessible via a
`$this->item->jcfields` property, which is an array that holds the following
data for each field (this example is for an Editor field):

```php
    Array
    (
        [4] => stdClass Object
            (
                [id] => 4
                [title] => article-editor
                [name] => article-editor
                [checked_out] => 0
                [checked_out_time] => 0000-00-00 00:00:00
                [note] =>
                [state] => 1
                [access] => 1
                [created_time] => 2017-04-07 12:08:59
                [created_user_id] => 856
                [ordering] => 0
                [language] => *
                [fieldparams] => Joomla\Registry\Registry Object
                    (
                        [data:protected] => stdClass Object
                            (
                                [buttons] =>
                                [width] =>
                                [height] =>
                                [filter] =>
                            )

                        [initialized:protected] => 1
                        [separator] => .
                    )

                [params] => Joomla\Registry\Registry Object
                    (
                        [data:protected] => stdClass Object
                            (
                                [hint] =>
                                [render_class] =>
                                [class] =>
                                [showlabel] => 1
                                [disabled] => 0
                                [readonly] => 0
                                [show_on] =>
                                [display] => 2
                            )

                        [initialized:protected] => 1
                        [separator] => .
                    )

                [type] => editor
                [default_value] =>
                [context] => com_content.article
                [group_id] => 0
                [label] => article-editor
                [description] =>
                [required] => 0
                [language_title] =>
                [language_image] =>
                [editor] =>
                [access_level] => Public
                [author_name] => Super User
                [group_title] =>
                [group_access] =>
                [group_state] =>
                [value] => Bar
                [rawvalue] => Bar
            )
    )
```

## Render the field

The `FieldsHelper::render()` function is used to render each field. First add a
`use Joomla\Component\Fields\Administrator\Helper\FieldsHelper;` statement to
the list of `use` statements at the top of the override file:

```php
defined('_JEXEC') or die;

use Joomla\CMS\Helper\ContentHelper;
use Joomla\CMS\HTML\HTMLHelper;
use Joomla\CMS\Language\Text;
use Joomla\CMS\Layout\FileLayout;
use Joomla\CMS\Layout\LayoutHelper;
use Joomla\CMS\Plugin\PluginHelper;
use Joomla\CMS\Router\Route;
use Joomla\Component\Contact\Site\Helper\RouteHelper;
use Joomla\Component\Fields\Administrator\Helper\FieldsHelper;
```

Then, wherever you wish to place the fields in your template use the following
code:
```php
<?php foreach ($this->item->jcfields as $field) : ?>
	<?php echo FieldsHelper::render($field->context, 'field.render', array('field' => $field)); ?><br>
<?php endforeach ?>
```

Or for a raw override, which does not translate the label:

```php
<?php foreach ($this->item->jcfields as $field) : ?>
	<?php echo $field->label . ':' . $field->value; ?><br>
<?php endforeach ?>
```

## Loading individual fields

In order to add individual fields to your content, start by choosing
specific names for your custom fields, using the **Name** field, which
will be used to reference your field directly in the override code. In
the `Options` tab, select **No** in the `Automatic Display` field to
prevent it from being displayed automatically in any of the standard
positions.

Then, to enable direct access by name to custom fields in an override,
place the code below at the beginning of your file. You should do this
to every override PHP file that you want to place individual custom
fields on.

```php
<?php foreach($this->item->jcfields as $jcfield) {
    $this->item->jcFields[$jcfield->name] = $jcfield;
} ?>
```

And lastly, you should add the field placement code at the spot you want
the field label or value to be shown.

To add the **label** of the field to your override, insert the code
below, replacing `name-of-field` with the name of the field.

```php
<?php echo $this->item->jcFields['name-of-field']->label; ?>:&nbsp;
```

To add the **value** of the field to your override, insert the code
below, replacing `name-of-field` with the name of the field.

```php
<?php echo $this->item->jcFields['name-of-field']->rawvalue; ?>
```

You can add this code to any part of your override. Examples: The
content of a div, the src in an `img` tag, within a CSS class attribute,
etc.
