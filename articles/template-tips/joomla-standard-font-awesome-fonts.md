<!--
{
  "source": "https://docs.joomla.org/J4.x:Joomla_Standard_Font_Awesome_Fonts",
  "title": "Font Awesome Icon Fonts",
  "description": "", 
  "author": ""
}
-->

## Icons in standard templates

The standard templates, Cassiopeia (site) and Atum (backend), offer a set of free icons from Font Awesome.
For historical reasons we have two different CSS classes to access the icons. Furthermore the Font Awesome *prefix* class is different for standard ***Joomla*** icons and the ***Brand*** icons.

## How to Use the Icons

### Font Awesome Standard Icons

Font Awesome icons can be used in HTML in any of the following forms:

```html
    <i class="fa fa-!name!"></i>
    <i class="fa fa-!name! large-icon"></i>
    <i class="fa fa-!name!" style="font-size: 48px;"></i>

    <span class="fa fa-!name! large-icon"></span>
```

The `<i>` element with containing classes is preferred to the `<span>` element!

Please replace `!name!` with one of the icon names from the **FA Icons - Joomla** list. If a font size class or style is not specified the icon font will be at the same size as its container (paragraph, list, heading, ...)

The actual `fa-!name!` class is accompanied by a prefix class. The prefix class `fa` is short for `fas` which is short for `fa-solid` which can be used instead.

### Font Awesome Brand Icons

Font Awesome brand icons differ from standard icons in the first part of the class name, which is `fab` rather than `fa`. 

```html
    <i style="font-size: 48px;" class="fab fa-!name!"></i>

    <span class="fab fa-!name! large-icon"></span>
```

Please replace `!name!` with one of the icon names from the **FA Icons - Brands** list.

The prefix part is "fab" which is short for "fa-brands" which can be used instead

### Font Awesome replacements for IcoMoon Icons

Icons from J3! (IcoMoon) were replaced by a smaller subset of Font Awesome icons. They can be used in the following forms:

```html
    <i style="font-size: 48px;" class="icon-!name!"></i>

    <span class="icon-!name! large-icon"></span>
```

Please replace `!name!` with one of the icon names from the **FA Icons - IcoMoon** list.

The prefix part is `icon-` (examples `icon-calendar`, `icon-file`). Either of the following forms will show the Joomla! icon:

```html
    <span class="icon-joomla large-icon"></span>

    <span class="icon-joomla" style="font-size:24px;"> </span>
```

## Font Size

Because the icons are fonts, you can control the size of them with an added `class` or `style` statement. You will have to define the class in your .css or .less stylesheet file.

## CSS sources

In joomla the css files may be found in following paths:

Template Atum:

```
    media\templates\administrator\atum\css\vendor\fontawesome-free\fontawesome.css
```

Template Cassiopeia:

```
    media/system/css/joomla-fontawesome.css

    media/system/scss/joomla-fontawesome.scss 
```
## Available Icons in Joomla!

Font Awesome Free 6.7.2

Please see the separate lists for:

- Font Awesome standard Jooomla Icons
- Font Awesome Brand Icons
- Font Awesome Icomoon Replacement Icons