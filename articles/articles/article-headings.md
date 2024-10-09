<!-- Filename: J4.x:Article_Headings / Display title: Article Headings -->

## Heading Semantics

Headings define a sematic structure for a page. They may be used to
create an automatic table of contents and as navigational aids for users
with disabilities. Heading levels range from h1 to h6. A single page
should contain only one h1 heading which is usually the page title. A h1
heading should not be used in an article. Within an article, headings
should be nested to create a structure in which each heading level
introduces a well-defined section. Example, where the h1 page title is
Animals:

```
    ... text on animals in general ...
    <h2>Amphibians</h2>
    ... text on amphibians in general ...
    <h3>Frogs</h3>
    ... text on frogs ...
    <h3>Newts</h3>
    ... text on newts ...
    <h2>Reptiles</h2>
    ... text on reptiles in general ...
    <h3>Crocodiles</h3>
    ... text on crocodiles ...
    <h3>Turtles<h3>
    ... text on turtles ...
```
Headings help with ease of reading. Long blocks of text in web pages are
off-putting! Save them for Novels.

Headings should be short, the shorter the better. One word will do.
Whole sentences do not make suitable headings! Headings should not end
with a full stop.

Semantic headings should not skip levels, for example by including a h4 in a
h2 block just to achieve an appearance.

## Insert an Article Heading

Open the article you wish to edit. Notice that the default text container is a 
paragraph, marked by a letter `P` in an Information bar below the text area
at the bottom of the edit window. The default container can be changed in the 
Editor Options but that is covered elsewhere. When you type a newline followed
by some text that text is contained in a paragraph. To create a heading:

- Position the cursor at the start of an existing paragraph or at the
  bottom of the text if you are creating a new section.
- Type the heading followed by a newline.
- Select the line to be made into a heading.
- From the editor format buttons, where *Paragraph* is shown selected:
  - Select **Headings → Heading X** where X is the appropriate value
    your hierarchy.
- The selected paragraph will become a heading and appear in bold text.
- At the bottom of the screen the container indicator will show HX.
- You can double click any selected text to make a quick change, say from 
  P to H2 (toggle) or H2 to H3 using a popup bar as in the following screenshot:

![article edit form with h3 selected](../../../en/images/articles/articles-edit-headings.png)

Note: by convention, all HTML tags use lower case letters. If you select
*Toggle Editor* button to look at the source you will see the paragraphs and
headings set in tags with lower case.

## Tips

- Double click any text selection to see a popup with a list of formatting
  options. *Heading* and *Block quote* selections are applied to the whole 
  paragraph. *Bold*, *Italic* and *Underline* are applied to the selected 
  characters.