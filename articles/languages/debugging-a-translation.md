<!-- Filename: Debugging_a_translation / Display title: Debugging a Translation -->

## Joomla Language Files

Whenever text is to be output to the screen Joomla coders insert a language
constant such as JYES or JNO. During the rendering process language files
are loaded with translations in the appropriate langauge. The language files
all end in `.ini`. You can look in languages/en-GB/joomla.ini for some basic
examples. Lines starting with a semi-colon are ignored. They can be used for
comments. The remaining lines consist of key="value" pairs. Each language has
the same set of keys but values are the appropriate translations.

Each Joomla extension has its own language files so there are hundreds in
total. Sometimes, there are problems such as missing language constants,
mis-spelled language constants or sytntax errors in the translation strings
that can render a whole language file invalid.

## Debug Language

Joomla provides some useful debugging mechanisms that can make it easier
to locate untranslated strings and diagnose problems with language
translations in installed extensions. To try it out:

From the Home Dasboard:

* Select the **Global Configuration** button in the *System* panel.
* Select the *System* panel and set **Debug Language** to **Yes**.
* **Language display** is normally set to **Value**. If set to **Constant**
the layout is disrupted by long constants that do not wrap.

With Debug Language active all translatable values are shown surrounded
with special characters that indicate their status:

* `**Joomla CMS**` Text surrounded by two asterisks indicates that a match
has been found in a language file and the constant has been translated.
* `??Joomla CMS??` Ttext surrounded by pairs of question marks indicates that
the constant is translatable but no match was found in a language file.
* `Joomla CMS` Text with no surrounding characters indicates that the value is
not translatable.                                                           |

## Debug System

Additional language debugging information can be obtained by activating
System debugging.

From the Home Dasboard:

* Select **Plugins** and then find and enable the **System - Debug** plugin.
* Select the Home Dashboard again and then...
* Select the **Global Configuration** button.
* Select the *System* panel and set **Debug System** to **Yes**.

With **System Debug** active all screens have additional debugging information
at the bottom of each page. It can be expanded from a Joomla icon and the top
border dragged vertically to show more lines.

The debug information comes under several headings:

* **J! Info** Basic installation information.
* **Request** Server Request fields.
* **Session** Session information
* **Profile** The amount of time taken to execute code up to various mark
points in the code.
* **Queries** The SQL queries executed in the process of building the page.
* **Loaded.** A list of all the language files loaded in the process of
building the page, including full path information. This can be useful to
check that the expected files have been loaded.
* **Untranslated** A list of all the untranslated constants found and the
likely file location given where the translation call was made.
* **Errors**

## System - Debug Plugin

This system plugin controls what is displayed when debugging is
activated in **Global Configuration**. There are three settings of interest
to translators.

In the **Language** tab:

![plugin system debug](../../../en/images/languages/languages-debug-plugin.png)

* **Errors When Parsing Language Files** Display an error if a language file
fails to load.

- **Language Files**. If set to *Show* then ...
- **Language String** If set to *Show* then ...
- **Strip First Word**.
- **Strip From Start**
_ **Strip From End**

**The following Explanation needs revision!**

Note that untranslated strings will only display the value passed to the
appropriate **Text** method. For example, with the following code:

    echo Text::_( 'Reports Import Configuration' );

If untranslated will display as:

    # /administrator/components/com_reports/views/reports/tmpl/default.php
    REPORTS IMPORT CONFIGURATION=Reports Import Configuration

If the Strip Key Prefix is set to "Reports", then the display would
change slightly to:

    # /administrator/components/com_reports/views/reports/tmpl/default.php
    REPORTS IMPORT CONFIGURATION=Import Configuration

Note that the path shown is only a best guess based on a call to the PHP
*debug_backtrace* function. Sometimes it is accurate, sometimes it is
not and there are also cases where no file could be determined. In those
cases you have to use your best judgement.
