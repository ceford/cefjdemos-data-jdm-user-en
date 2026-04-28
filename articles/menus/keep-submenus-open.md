<!-- Filename: https://guide.joomla.org/user-manual/menus/keep-submenus-open / Display title: Keep Submenus Open -->

A menu module can be used to display a horizontal menu (usually at the top of the page) or a vertical menu (usually in a sidebar, left or right). In a horizontal (top) menu it is not desirable to keep the submenu open. That is why the default behaviour of a menu module is to close the submenus on page load.

## Toggle status *open* behavior

However, in a vertical (sidebar) menu, it is often desirable to leave a submenu open when it contains the active menu item. In Joomla 6.0 a new CSS class, `nav-active-open`, was introduced specifically to allow control over whether submenus are automatically opened on page load for the active menu item. Setting this class now makes it possible to achieve this. The class is set in the module via the backend.

![menu class setting in backend for nav-active-open for toggle stay open on active menu](../../../en/images/menus/keep-submenus-open-menu-class-setting.png)
 
## How to make a sidebar menu without dropdown toggle

If you want to keep all submenus open, you don't need a dropdown toggle. Instead, use a [template override](jdocmanual?article=user/templates/template-overrides).

This is how this particular template override is accomplished:

1. Start by selecting System → Templates → Site Templates in the Administrator menu and then select the Cassiopeia Details and Files item. That will open the Templates: Customise (Cassiopeia) form.

2. Switch to the Create Overrides tab and and select mod_menu:

![module menu template override selection](../../../en/images/menus/keep-submenus-open-create-override-select-mod-menu.png)

3. Go back to the editor tab and expand the entries under HTML → mod_menu.  Here you will find the  `default.php` file . Open the file and start editing your override:

![mod_menu override edit tab - open default.php](../../../en/images/menus/keep-submenus-open-edit-mod-menu.png)

4. To display the menu as a plain list - without the toggle function and without the associated accessibility buttons - remove the code lines listed here:

![Diff view after removing the code lines for the toggle functionality](../../../en/images/menus/keep-submenus-open-edit-mod-menu-diff-view.png)

Remove lines 15 - 20

```php
/** @var Joomla\CMS\WebAsset\WebAssetManager $wa */
$wa = $app->getDocument()->getWebAssetManager();
$wa->getRegistry()->addExtensionRegistryFile('mod_menu');
$wa->usePreset('mod_menu.menu');
```

Remove lines 66-71

```php
    // The next item is deeper - add toggle only here it is a heading or separator
    if ($item->deeper && (int) $item->level === $startLevel && in_array($item->type, ['separator', 'heading'])) {
        // Add a toggle button.
        echo '<button class="mod-menu__toggle-sub" aria-expanded="false">';
    }
```

Remove lines 93 - 94

```php
                    echo '<span class="icon-chevron-down" aria-hidden="true">' .
                        '</span></button>';
```

Replace lines 98 - 101 with `break`

```php
                    echo '<button class="mod-menu__toggle-sub" aria-expanded="false">' .
                 break;
                    '<span class="icon-chevron-down" aria-hidden="true"></span>' .
                    '<span class="visually-hidden">' . Text::sprintf('MOD_MENU_TOGGLE_SUBMENU_LABEL', $item->title) . '</span>' .
                    '</button>';
```

## Result

The result is a plain list, without toggle functionality for the side menu module:

![result with template override - plain list without toggle buttons and functionality](../../../en/images/menus/keep-submenus-open-site-result.png)

## Best Practice Tip

Before you start creating overrides in your template, first create a child template. Do not edit the original template that comes with Joomla!, as this may be overwritten during the next update. The changes in your child template will be preserved.
