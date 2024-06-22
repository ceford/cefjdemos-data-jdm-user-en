<!-- Filename: How_do_you_put_a_module_inside_an_article%3F / Display title: Modules inside Articles -->

## Introduction

You will usually want to associate modules with articles in some way.
Modules are usually allocated to module positions and the module positions
appear somewhere on the web page as determined by the template. However,
it is sometimes useful to have a module actually embedded within an
article. Joomla has a plugin named *Content - Load Modules* to do that. When
enabled, a module may be embedded in an article in three different ways:

- {loadposition position,\[style\]}
- {loadmodule mod_type,the title,\[style\]}
- {loadmoduleid moduleId}

Where *style* is one of the Module Style values from the Advanced tab of the
module data entry form, for example html, outline, table, card or noCard.

## loadposition

To insert a module inside an article, you publish the module to a
position and load that position in the article as follows:

1.  Create a module and set its position to ***myposition***.
    ***myposition*** can be any value that doesn't conflict with an
    existing template position. In the module edit form, type in the
    position ***myposition*** and press enter instead of selecting it
    from the drop-down list.
2.  Assign the module to **All** the Menu Items. This will make sure
    that it always appears, no matter how the visitor got to the
    article. The module will not show unless you use the command to load
    the module in an article.
3.  Edit the article and insert the text ***{loadposition myposition}*** at
    the place where you want the module to appear.

**Note:** If the *Content - Load Modules*  plugin is disabled, the text
*{loadposition myposition}* will show unchanged in the article. Also, the name
of the position should be all lowercase. CamelCapitalization will fail.

## loadmodule

The *{loadmodule yyy}* syntax looks for the first module who's **type**
matches the string 'yyy'. So you could load a *mod_login* module by
placing {loadmodule login} in your text. The type is not so obvious! For
example, the Language Switcher is type **languages**. To find the type you
need to look through the list of module folders with a file manager/eplorer and
drop the *mod_* part of the folder name.

If you wish to load a specific instance of a module, because you have more
than one login module e.g. titled as Login 1, Login 2, etc. you have to use
{loadmodule mod_modType, modTitle} where **mod_modType** would be mod_login and
**modTitle** would be the name/title given to your instance of that module.
So in the example above you end up with **{loadmodule mod_login Login 2}**.

You can also add the style that is used for rendering the module. To do
so, add the style as the third parameter like {loadmodule login,Login 2,xhtml}.
If you don't add a style, then "none" is used.

## loadmoduleid

The *{loadmoduleid z}* syntax looks for the module who's `id` matches the
number `z`. So you could load the module with id 200 by placing
*{loadmoduleid 200}* in your text. This variant does not use additional
parameters like the `style` parameter.

## Editor Button

If the editor-xtd plugin *Button - Module* is activated you can use the
editor button *Module* to insert the above described tags more easily into
the editor text. The Module list has a button in the Title column to insert
by id and a button in the Position colum to insert by position.

## Modules within Modules

It is possible to include a module within a *Custom HTML* module. They are
processed by content plugins in the same way as articles.

There may be formatting issues as the style of the *Custom HTML* module will
surround the style of the included module. That's the reason why the *Module*
editor button is not available in modules of type *Custom*.
