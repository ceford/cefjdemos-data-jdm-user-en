<!-- Filename: jdocmanual?manual=user&heading=help&filename=administrator-help.md / Display title: Administrator Help -->

## Introduction

Almost all Joomla Administrator pages have a Toolbar containing a **Help**
button near the top right of the page. Only Dashboards lack a Toolbar and hence
a Help button.

Many pages also have a button labelled **Toggle Inline Help**.
This simply displays or hides a field description if one is available. Its
purpose is to reduce clutter but provide a reminder mechanism where this
would be helpful. It is not covered further here.

The **Help** button triggers opening of a new window using a URL embedded in
the button. An example:
```
data-url="https://help.joomla.org/proxy/index.php?keyref=Help51:Articles&lang=en"
```
In this case the content of the Help page comes from an external source.

## The Help Source - a MediaWiki site

MediaWiki is the software used by WikiPedia. It is a Free Open Source Software
(FOSS) package that uses PHP and MySQL, just like Joomla. You can download and
install it yourself. In theory you could create your own Help server and use
that instead of the communal Joomla Help Server. In practice you need to know
that MediaWiki pages need some processing to make them suitable for display as
Help pages.

That is where the **proxy** comes in. It fetches the required page from the
MediaWiki installation and prepares it for display as a Help page. You can see
an original MediaWiki page in this example at https://docs.joomla.org/Help5.x:Articles
and you can edit it if you see something wrong.

## The Global Help URL

The **configuration.php** file in the root of a Joomla installtion contains a
$helpurl variable:

```
	public $helpurl = 'https://help.joomla.org/proxy/index.php?keyref=Help{major}{minor}:{keyref}&lang={langcode}';
```
When a Help button is selected, each of the items in curly braces is replaced.
The {major} and {minor} values are the version settings for your installation.
The {langcode} is the code of your currently selected Administrator language,
which might be en, de or fr.

The {keyref} variable is the filename of a page on the Help server, less its
namespace. So for the Articles page the relevant filename happens to be
*Articles*.

**Note:** `https://docs.joomla.org/` is the site for editing Help pages. But
`https://help.joomla.org/proxy` is the site for recovering Help pages.

There is no provision for changing the default Help server URL from within the
Administrator Global Configuration forms but you can change it with a text
editor.

The complete list of available substitution codes is:

| Code          | Will be substituted by                                                         |
|---------------|--------------------------------------------------------------------------------|
| {app}         | Application name (e.g. "Administrator" in the Joomla CMS back-end)             |
| {component}   | Component name (e.g. "com_content" in the Article Manager)                     |
| {keyref}      | Help screen key reference (after passing through the translation system)       |
| {major}       | Joomla major revision number (e.g. "5" in Joomla 5.6).                         |
| {minor}       | Joomla minor revision number (e.g. "1" in Joomla 5.1)                          |
| {maintenance} | Joomla maintenance revision number (e.g. "3" in Joomla 5.1.1).                 |
| {language}    | Full language code (e.g. "en-GB")                                              |
| {langcode}    | Language tag part of the language code (e.g. "en" if the full code is "en-GB") |
| {langregion}  | Region tag part of the language code (e.g. "GB" if the full code is "en-GB")   |

## Global Help in the Future

The use of a MediaWiki site for delivery of Help pages is a something of a
burden for those who maintain documentation and the procedure may change in
the future. If there is a change, it is likely the source will consist of
prebuilt HTML files accessed with a simple change of $helpurl source domain.

## Custom Component Local Help

If you have a custom component and you are comfortable with editing php
source code and creating content you can create your own individual help pages.
Take the Jdocmanual component as an example. As a custom component there are no
Help pages on the docs.joomla.org MediaWiki site. Third party components are
not allowed to serve Help pages from there.

Have a look at this code fragmant from administrator/components/com_jdocmanual/src/View/Manual/ViewHtml.php:
```
        $tmpl = $app->input->getCmd('tmpl');
        if ($tmpl !== 'component') {
            ToolbarHelper::help('jdocmanual', true);
        }
```
The specification of the ToolbarHelper::help call is as follows:
```
@param $ref: The name of the target file (excluding the file extension).
@param $useComponent: Use the help file in the component directory.
@param $url: Use this URL instead of any other.
@param $component: Name of component to get Help (null for current component)
function Toolbar::help(
    string $ref,
    bool $useComponent = false,
    string $url = null,
    string $component = null
): HelpButton
Writes a help button for a given option (opens a popup window).
```
In this example **$ref** is a file name to use, in this case `'jdocmanual'` (it
must match the case of the target file) and **$useComponent** is `true`, meaning
that the Help page to use will be located within the component files at
administrator/component/com_jdocmanual/help/en-GB/jdocmanual.html

Using a help file within the component should mean that Help is never missing
and perhaps always up to date.

## Custom Component Remote Help

In the creation of the Help button you could set $useComponent = false and set
the url to point so a specific location on your own site or a remote site.

```
    ToolbarHelper::help('jdocmanual', false, 'http://example.com/help/en-GB/jdocmanual.html');
```

So all that is needed is an HTML page with the correct name in the correct
place.
