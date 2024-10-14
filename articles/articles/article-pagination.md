<!-- Filename: J4.x:Article_Pagination / Display title: Article: Edit - Pagination -->

## Long Articles

The only limit on the length of an article in Joomla is the size of the
database field used to contain the article text. That is very large!
Long articles may contain many images and and take time to process,
which may prove an inconvenience for the reader and the website. So
there is a simple mechanism to break long articles into separate pages
with a table of contents.

## Insert a Page Break

To add page breaks, first open an article in the text editor, TinyMCE
is the default, and proceed as follows:

- Position the cursor at the location where a page break is to occur.
- From the **CMS Content** drop-down list select the *Page Break* item.
- In the Page Break dialog box enter:
  - *Page Title* - this will be appended to the existing page title.
    Example: Page 2
  - *Table of Contents Alias* - this will be used as text in the Table of
    Contents. Example: Chapter 2
- Select the **Insert Page Break** button.

![Page break dialog form](../../../en/images/articles/articles-edit-pagination.png)

- Repeat for each page break you wish to create.
- Save the article and have a look at the Preview or Site view.

![Article pagination site view](../../../en/images/articles/articles-site-pagination.png)

## Edit or Move a Page Break

You can select a page break and delete it. However, you can't cut and
paste it and you can't open an existing page break in the Page Break
form. So to move or change a page break use the Source Code editor as
follows:

- Select the text editor's **Tools -> Source code+** item.
- The source code editor shows the source HTML with syntax highlighting.
- Scroll down to the page break you wish to edit or move.
- To move a page break:
  - Select and Cut the line containing the page break.
  - Place the cursor at the new position and Paste the cut line.
- To edit:
  - Change the title text and/or the alt text as you see fit.
- Select **Save**.
- Save the article and have a look at the Preview or Site view.

The Source code editor is located in a popup dialog:

![Source code editor](../../../en/images/articles/articles-edit-pagination-source-code.png)

