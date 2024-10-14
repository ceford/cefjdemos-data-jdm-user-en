<!-- Filename: J4.x:Article_Lists / Display title: Article: Edit - Lists -->

## List Types

HTML has three types of lists:

- Unordered lists are often styled with an indentation and a bullet,
  like this list.
- Ordered lists are similar but marked with numbers.
- Definition lists consist of Titles and Definitions.

The bullet points and numbers are applied by the browser from a
selection of styles. The user must not enter any bullet or number text
as that will be treated as part of the list. The TinyMCE editor has
icons to apply common bullet styles and types of numbers. Definition
lists are more complicated and need to be handcrafted.

Lists can contain other lists to any level, although deeply indented
lists become hard to read so it is best to stick to one or two levels.

## Screenshot

The following screenshot shows an unordered list with two levels of indentation.
It also shows the full tool set, opened by selecting the ellipsis button (...)
at the end of the first row of tool icons.

![Nested unordered lists](../../../en/images/articles/articles-edit-lists.png)

This screenshot will be used to explain how the bulleted list was created using
the *Bullet list* and *Increase indentation* or *Decrease indentation* tools:

## List Styles

### Bulleted lists

Three styles are available: 

- A filled circle is the default.
- An open circle.
- A filled square.

The down chevron to the right of the bullet list icon opens a small panel
allowing selection of the preferred style for a selected list item:

![Bullet list manipulation tools](../../../en/images/articles/articles-edit-list-bullets.png)

The list icon acts like a toggle. If the cursor is in a paragraph and a bullet
is selected the paragraph becomes a list item. If the bullet is selected again
the list item reverts to being a paragraph.

If two or more paragraphs are selected and a list icon is selected, each of the
paragraphs becomes a list item. To make an indented list select the 
*Increase indent* tool to the right of the List tools. By default, the indented
list item will adopt the next list style. 

So to explain how to create the indented lists in the screenshot:

- Type each of the terms as single word paragraphs.
- Select all of the paragraphs to be made into a bulleted list.
- Select the *Bullet list* icon.
- Select the first group if terms to be indented
- Select the *Increase indent* icon.
- Select the second group of terms to be indented.
- Select the *Increase indent* icon.

### Numbered lists

Six styles are available

- Numbers: 1, 2, 3 ...
- Letters: a, b, c ...
- Greek characters: &alpha;, &beta;, &gamma; ...
- Lower case Roman numerals: i, ii, iii ...
- Upper case Letters: A, B, C ...
- Upper case Roman numerals: I, II, III ...

![Number list manipulation tools](../../../en/images/articles/articles-edit-list-numbers.png)

Numbered lists work a little differently. When a list item is indented it takes
on the first numeric value and the numbers on the rest of the list move up so
that the list is always in correct numerical order.

### Mixed lists

The numbering system can be change in each level. For example, you could set 
the first level to use numeric values and the second level to use bullets, or
Greek characters, or anything else.

It is probably best to experiment with lists to see how they can be manipulated.

## Definition lists

Definition lists consist of a *Definition title* and one or more 
*Definition descriptions* followed by the next *Definition title* and its 
*Description*. They would be good for a *Glossary* or any sort of set of 
Key / Value pairs. To create a definition list:

- Select the *Toggle Editor* button to see the HTML article markup.
- Type in the Definition List mark up. Here is an example:
```html
<dl>
<dt>Amphibian</dt>
<dd>Cold-blooded vertebrate that lays eggs in water and has an aquatic laval stage.</dd>
<dt>Reptile</dt>
<dd>Cold-blooded vertebrate that lays eggs on land.</dd>
</dl>
```
Save and view the result in the Preview.
