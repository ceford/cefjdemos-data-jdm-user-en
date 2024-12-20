<!-- Filename: J4.x:Menu_Item_Order / Display title: Menu Item Order -->

## Introduction

When a new menu item is created its default position is at the end of
the list of menu items. Often this is not the most suitable place and an
individual menu item needs to be moved, along with any child items if it
is a parent menu item. There are two methods available to change the
order of a menu item:

- Drag and Drop
- List Select

Both methods move child menus with their parent menus. Child items
cannot be moved to another parent using these methods.

## Drag and Drop Method

Starting from the Administrator menu:

- Select **Menus **→** Main Menu** or whichever menu contains the item
  to be moved.
- Select the **Ordering** symbol in the heading of the list of menu
  items. It is the heading of the second column and has no visible
  label. If the ordering column is selected a second time the sort order
  is reversed. Select so that the symbol at the head of the column is a
  chevron pointing upwards. This is the normal sort order.
- When the ordering symbol is selected grab handles appear in that
  column. They are marked with vertical ellipsis symbols.
- Select and drag the symbol of the item you wish to move.
- Drop the dragged item into its new position.

![menu item order drag](../../../en/images/menus/menus-menu-item-order-drag.png)

This method can be inconvenient if there are parent menu items with many
children. You can move a parent item more easily by hiding the children:

- Select **Filter Options**
- Set **- Select Max Levels -** to 1
- Drag and Drop

This does not work if a child menu item order is to be changed. In this
case:

- Select **Filter Options**
- Set the **- Select Parent Menu Item -** filter to the appropriate parent
- Drag and Drop

## List Select Method

Starting from the Administrator menu:

- Select **Menus → Main Menu** or whichever menu contains the item
  to be moved.
- Select the title link of the menu item you wish to move to open the
  menu item edit form.
- In the Menus: Edit Item form **Ordering** field select the item after
  which you wish to place the item being moved, or the *- First -* or
  *- Last -* positions.

![menu item order list](../../../en/images/menus/menus-menu-item-order-list.png)

- **Save** or **Save & Close**

## Site Check

Go to your site and reload any page that contains the altered menu to
check the items are in the desired order.
