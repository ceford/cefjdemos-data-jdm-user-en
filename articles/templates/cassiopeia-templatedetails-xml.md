<!-- Filename: J4.x:Cassiopeia_templateDetails.xml / Display title: Cassiopeia templateDetails.xml -->

## Location and Purpose

You can see an example of a `templateDetails.xml` file listed in
**System **→** Site Templates **→** Cassiopeia Details and Files**. You
can edit it there too if you have good reason to do so. Otherwise, leave
it alone! Every template has such a file and a child template initially
consists of a file structure containing only this one file.

The `templateDetails.xml` file contains the data that Joomla! needs to
manage and display the template. This includes meta-data used to provide
information about the template, the locations of folders and files, the
template module positions and the user selectable configuration options.
The content of the templateDetails.xml file will differ from template to
template.

## Cassiopeia templateDetails.xml

Files in xml format have a well-defined structure. An xml file must be
have the correct syntax or it will not work!

### XML Format

The first line of every `templateDetails.xml` must start with the XML
doctype definition.

The next line tells Joomla! that the data in this file is for a site
template extension. All template data is contained within the opening
and the closing tags.

```xml
<extension type="template" client="site">
...
</extension>
```

### Metadata

The first section of template data usually defines template information,
for example: names, dates, contact information, copyrights, version
number and description.

```xml
<extension version="3.1" type="template" client="site">
	<name>cassiopeia</name>
	<version>1.0</version>
	<creationDate>2017-02</creationDate>
	<author>Joomla! Project</author>
	<authorEmail>admin@joomla.org</authorEmail>
	<copyright>(C) 2017 Open Source Matters, Inc.</copyright>
	<description>TPL_CASSIOPEIA_XML_DESCRIPTION</description>
	<inheritable>1</inheritable>
```

Notice that a template that can have child templates has the ineritable
value set to 1. Child templates have this value set to 0. This data is
used in the Templates: Templates (Site) listing as shown below.

<img
src="https://docs.joomla.org/images/thumb/d/da/J4x-templates-list-en.png/800px-J4x-templates-list-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/d/da/J4x-templates-list-en.png 1.5x"
data-file-width="1000" data-file-height="508" width="800" height="406"
alt="screenshot of site templates list" />

The description contains a language key and not the actual description
text string. The key is replaced by the text obtained from a language
file at run time. The language files are defined in the in the language
section of `templateDetails.xml`.

<img
src="https://docs.joomla.org/images/thumb/d/d6/J4x-templates-cassiopeia-language-string-en.png/800px-J4x-templates-cassiopeia-language-string-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/d/d6/J4x-templates-cassiopeia-language-string-en.png 1.5x"
data-file-width="1000" data-file-height="347" width="800" height="278"
alt="screenshot of templates edit style form" />

### Folders and Files

Folders and files for the Cassiopeia template are stored in two separate
places. The php and related files are stored in the site/templates
folder. The media files (css, images, js and scss) are stored in the
site/media folder. Those locations are defined in the xml file as
follows:

```xml
	<files>
		<filename>component.php</filename>
		<filename>error.php</filename>
		<filename>index.php</filename>
		<filename>joomla.asset.json</filename>
		<filename>offline.php</filename>
		<filename>templateDetails.xml</filename>
		<folder>html</folder>
	</files>
	<media destination="templates/site/cassiopeia" folder="media">
		<folder>js</folder>
		<folder>css</folder>
		<folder>scss</folder>
		<folder>images</folder>
	</media>
```

This is the pattern seen in all modern Joomla 4 templates. The structure
can be seen in the Templates: Customise (Cassiopeia) form:

<img
src="https://docs.joomla.org/images/thumb/8/88/J4x-templates-cassiopeia-customise-en.png/800px-J4x-templates-cassiopeia-customise-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/8/88/J4x-templates-cassiopeia-customise-en.png 1.5x"
data-file-width="1000" data-file-height="438" width="800" height="350"
alt="screenshot of templates customise cassiopeia page" />

### Module Positions

The available module positions are defined as follows:

```xml
	<positions>
		<position>topbar</position>
		<position>below-top</position>
		<position>menu</position>
		<position>search</position>
		<position>banner</position>
		<position>top-a</position>
		<position>top-b</position>
		<position>main-top</position>
		<position>main-bottom</position>
		<position>breadcrumbs</position>
		<position>sidebar-left</position>
		<position>sidebar-right</position>
		<position>bottom-a</position>
		<position>bottom-b</position>
		<position>footer</position>
		<position>debug</position>
	</positions>
```

Each tag creates a module position that is available from the position
list in a module edit form. The simple format of the position list means
it can be customized easily. For example, to add a new module position
to the list **in a child template**, simply add a new tag inside the tag
with a unique name using all lowercase letters with no spaces. Keep in
mind that this only adds the position to module edit forms and
additional development in other template files is required to render the
new position on the front end.

Cassiopeia has enough template positions! If you think you need an extra
one you are probably wrong. Remember that any number of modules can be
assigned to a single position and sorted into order in the Modules list
page. Available positions:

<img
src="https://docs.joomla.org/images/2/28/J4x-cassiopeia_template_explained_positions.png"
class="thumbborder" decoding="async" data-file-width="786"
data-file-height="980" width="786" height="980"
alt="screenshot of Template Positions" />

You can also see the module positions in any template: from
**System **→** Site Templates** selet the Options button in the Toolbar.
In the Options form set the Preview Module Positions field to Enabled.
Save and Close. Go to your site and add ?tp=1 to the end of any url (or
&tp=1 if there is already a ? in the url). Joomla will display all of
the available template positions, even those that have not been used:

<img
src="https://docs.joomla.org/images/thumb/e/e5/J4x-templates-cassiopeia-template-positions-en.png/800px-J4x-templates-cassiopeia-template-positions-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/e/e5/J4x-templates-cassiopeia-template-positions-en.png 1.5x"
data-file-width="1000" data-file-height="508" width="800" height="406"
alt="screenshot of site cassiopeia template positions" />

### Languages

Language files allow translation of static text in the template. The
tpl_cassiopeia.ini file contains key to text translations for text that
will be viewed by the User. The tpl_cassiopeia.sys.ini file contains key
to text translations for text that will be seen by the Administrator.

```xml
	<languages folder="language">
		<language tag="en-GB">en-GB/tpl_cassiopeia.ini</language>
		<language tag="en-GB">en-GB/tpl_cassiopeia.sys.ini</language>
	</languages>
```

The language files for the default English GB language are are stored in
site/language/en-GB/. Other languages would be stored similarly in files
with the appropriate ISO language code, for example fr-FR for French in
France or de-DE for German in Germany (which might be different from
Swiss German and Austrian German).

### Options

A template may offer display options that can be chosen by the
Administrator in the Template: Edit Style form. For example, the
Advanced tab of the Cassiopeia template allows an Administrator to
change the Brand, add a Logo, select a Fonts Scheme, and more.

<img
src="https://docs.joomla.org/images/thumb/8/83/J4x-templates-cassiopeia-edit-style-en.png/800px-J4x-templates-cassiopeia-edit-style-en.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/8/83/J4x-templates-cassiopeia-edit-style-en.png 1.5x"
data-file-width="1000" data-file-height="922" width="800" height="738"
alt="screenshot of templates edit style form advanced tab" />

The template options are defined within a structure that creates fields
within fieldsets. Each feildset appears as a tab in the edit form. This
is the structure that creates the Advanced tab seen above.

```xml
	<config>
		<fields name="params">
			<fieldset name="advanced">
				<field
					name="brand"
					type="radio"
					label="TPL_CASSIOPEIA_BRAND_LABEL"
					default="1"
					layout="joomla.form.field.radio.switcher"
					filter="boolean"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>
				...
			</fieldset>
		</fields>
	</config>
```

Individual options are defined with the `<field>` tag. Each `<fieldset>`,
and each `<field>` parameter within a `<fieldset>`, requires a unique
name defined by a **name** attribute. This name
defines the parameter itself and is used to pass settings to the front
end files. Each parameter also contain a **label** attribute and a
**description** attribute. The label text appears with the parameter in
the settings screen to identify what the setting is used for and more
detailed information can be included in the description.

A parameter field can be virtually any type of form input with
corresponding options. This is selected by the **type** attribute. Any
necessary options, such as radio button or select choices, are defined
in `<option>` tags. CSS class names can be defined with the **class** attribute and
a default value can be defined using the **default** attribute.

Below are the option definitions in the default Cassiopeia template. In
this example, all Labels, Descriptions and Options are using language
string definitions from the Language files defined in the previous
section, as well as some from the Joomla! core, so they can be
translated into different languages as necessary.

```xml
	<config>
		<fields name="params">
			<fieldset name="advanced">
				<field
					name="brand"
					type="radio"
					label="TPL_CASSIOPEIA_BRAND_LABEL"
					default="1"
					layout="joomla.form.field.radio.switcher"
					filter="boolean"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="logoFile"
					type="media"
					default=""
					label="TPL_CASSIOPEIA_LOGO_LABEL"
					showon="brand:1"
				/>

				<field
					name="siteTitle"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TITLE"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="siteDescription"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TAGLINE_LABEL"
					description="TPL_CASSIOPEIA_TAGLINE_DESC"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="useFontScheme"
					type="groupedlist"
					label="TPL_CASSIOPEIA_FONT_LABEL"
					default="0"
					>
					<option value="0">JNONE</option>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_LOCAL">
						<option value="media/templates/site/cassiopeia/css/global/fonts-local_roboto.css">Roboto (local)</option>
					</group>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_WEB">
						<option value="https://fonts.googleapis.com/css2?family=Fira+Sans:wght@100;300;400;700&amp;display=swap">Fira Sans (web)</option>
						<option value="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100;300;400;700&amp;family=Roboto:wght@100;300;400;700&amp;display=swap">Roboto + Noto Sans (web)</option>
					</group>
				</field>

				<field
					name="noteFontScheme"
					type="note"
					description="TPL_CASSIOPEIA_FONT_NOTE_TEXT"
					class="alert alert-warning"
				/>

				<field
					name="colorName"
					type="filelist"
					label="TPL_CASSIOPEIA_COLOR_NAME_LABEL"
					default="colors_standard"
					fileFilter="^custom.+[^min]\.css$"
					exclude="^colors.+"
					stripext="true"
					hide_none="true"
					hide_default="true"
					directory="media/templates/site/cassiopeia/css/global/"
					validate="options"
					>
					<option value="colors_standard">TPL_CASSIOPEIA_COLOR_NAME_STANDARD</option>
					<option value="colors_alternative">TPL_CASSIOPEIA_COLOR_NAME_ALTERNATIVE</option>
				</field>

				<field
					name="fluidContainer"
					type="radio"
					layout="joomla.form.field.radio.switcher"
					default="0"
					label="TPL_CASSIOPEIA_FLUID_LABEL"
					>
					<option value="0">TPL_CASSIOPEIA_STATIC</option>
					<option value="1">TPL_CASSIOPEIA_FLUID</option>
				</field>

				<field
					name="stickyHeader"
					type="radio"
					label="TPL_CASSIOPEIA_STICKY_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="backTop"
					type="radio"
					label="TPL_CASSIOPEIA_BACKTOTOP_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>
			</fieldset>
		</fields>
	</config>
```

In this example, the `<fieldset name="advanced">` tag encloses all of the
parameters and it uses the **name** attribute to
create the "Advanced" tab in the interface. All that is necessary to
create another tab in the interface is another `<fieldset>` tag with a
different **name** attribute. With this in mind, it is
relatively simple to create as many additional tabs and parameters as
necessary in a template.

One potential use of extra parameters is in overrides or layouts for
either parent or child templates.

## Summary

This is the templateDetails.xml file used by Cassiopeia:

```xml
<?xml version="1.0" encoding="utf-8"?>
<extension type="template" client="site">
	<name>cassiopeia</name>
	<version>1.0</version>
	<creationDate>2017-02</creationDate>
	<author>Joomla! Project</author>
	<authorEmail>admin@joomla.org</authorEmail>
	<copyright>(C) 2017 Open Source Matters, Inc.</copyright>
	<description>TPL_CASSIOPEIA_XML_DESCRIPTION</description>
	<inheritable>1</inheritable>
	<files>
		<filename>component.php</filename>
		<filename>error.php</filename>
		<filename>index.php</filename>
		<filename>joomla.asset.json</filename>
		<filename>offline.php</filename>
		<filename>templateDetails.xml</filename>
		<folder>html</folder>
	</files>
	<media destination="templates/site/cassiopeia" folder="media">
		<folder>js</folder>
		<folder>css</folder>
		<folder>scss</folder>
		<folder>images</folder>
	</media>
	<positions>
		<position>topbar</position>
		<position>below-top</position>
		<position>menu</position>
		<position>search</position>
		<position>banner</position>
		<position>top-a</position>
		<position>top-b</position>
		<position>main-top</position>
		<position>main-bottom</position>
		<position>breadcrumbs</position>
		<position>sidebar-left</position>
		<position>sidebar-right</position>
		<position>bottom-a</position>
		<position>bottom-b</position>
		<position>footer</position>
		<position>debug</position>
	</positions>
	<languages folder="language">
		<language tag="en-GB">en-GB/tpl_cassiopeia.ini</language>
		<language tag="en-GB">en-GB/tpl_cassiopeia.sys.ini</language>
	</languages>
	<config>
		<fields name="params">
			<fieldset name="advanced">
				<field
					name="brand"
					type="radio"
					label="TPL_CASSIOPEIA_BRAND_LABEL"
					default="1"
					layout="joomla.form.field.radio.switcher"
					filter="boolean"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="logoFile"
					type="media"
					default=""
					label="TPL_CASSIOPEIA_LOGO_LABEL"
					showon="brand:1"
				/>

				<field
					name="siteTitle"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TITLE"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="siteDescription"
					type="text"
					default=""
					label="TPL_CASSIOPEIA_TAGLINE_LABEL"
					description="TPL_CASSIOPEIA_TAGLINE_DESC"
					filter="string"
					showon="brand:1"
				/>

				<field
					name="useFontScheme"
					type="groupedlist"
					label="TPL_CASSIOPEIA_FONT_LABEL"
					default="0"
					>
					<option value="0">JNONE</option>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_LOCAL">
						<option value="media/templates/site/cassiopeia/css/global/fonts-local_roboto.css">Roboto (local)</option>
					</group>
					<group label="TPL_CASSIOPEIA_FONT_GROUP_WEB">
						<option value="https://fonts.googleapis.com/css2?family=Fira+Sans:wght@100;300;400;700&amp;display=swap">Fira Sans (web)</option>
						<option value="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100;300;400;700&amp;family=Roboto:wght@100;300;400;700&amp;display=swap">Roboto + Noto Sans (web)</option>
					</group>
				</field>

				<field
					name="noteFontScheme"
					type="note"
					description="TPL_CASSIOPEIA_FONT_NOTE_TEXT"
					class="alert alert-warning"
				/>

				<field
					name="colorName"
					type="filelist"
					label="TPL_CASSIOPEIA_COLOR_NAME_LABEL"
					default="colors_standard"
					fileFilter="^custom.+[^min]\.css$"
					exclude="^colors.+"
					stripext="true"
					hide_none="true"
					hide_default="true"
					directory="media/templates/site/cassiopeia/css/global/"
					validate="options"
					>
					<option value="colors_standard">TPL_CASSIOPEIA_COLOR_NAME_STANDARD</option>
					<option value="colors_alternative">TPL_CASSIOPEIA_COLOR_NAME_ALTERNATIVE</option>
				</field>

				<field
					name="fluidContainer"
					type="radio"
					layout="joomla.form.field.radio.switcher"
					default="0"
					label="TPL_CASSIOPEIA_FLUID_LABEL"
					>
					<option value="0">TPL_CASSIOPEIA_STATIC</option>
					<option value="1">TPL_CASSIOPEIA_FLUID</option>
				</field>

				<field
					name="stickyHeader"
					type="radio"
					label="TPL_CASSIOPEIA_STICKY_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>

				<field
					name="backTop"
					type="radio"
					label="TPL_CASSIOPEIA_BACKTOTOP_LABEL"
					layout="joomla.form.field.radio.switcher"
					default="0"
					filter="integer"
					>
					<option value="0">JNO</option>
					<option value="1">JYES</option>
				</field>
			</fieldset>
		</fields>
	</config>
</extension>
```
