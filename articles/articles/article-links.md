<!-- Filename: J4.x:Article_Links / Display title: Article Links -->

## Accessible Links

Select a link in a document and your browser opens the linked document,
either in the same window, a new window or a new tab. A person using a
screen reader my be navigating by links alone so link text needs to be
meaningful.

The following is an example of **good practice** because it states what the
link will lead to:

- To find out more, read our [Manifesto](#)

The following is an example of **bad practice** because it gives no clue to the
nature of the destination and it may be one of several similar links in the
same page:

- To find out more, click [here](#)

To find out more about accessible links see this article on 
[Creating valid and accessible links](https://www.a11yproject.com/posts/creating-valid-and-accessible-links/).

## Embedded Links

This article is about links embedded in the content of an article. There is a
separate article on using the [Images and Links](jdocmanual?article=user/articles/article-images-and-links)
tab to include links associated with an article.

Links embedded in an article may be to other pages within the site (internal 
links) or to other sites (external links). The procedure for inserting the two 
types differs. They are each described below.

## Insert an Internal Link

The process to insert a link to an article in the same website is simple:
- Type in the sentence containing the link text. For example:
  
  *For more information, please see the page on Frogs.*
- Select the link text: *Frogs*

The link may be to a single article or to a menu item for a category blog,
category list or featured articles.

### A Single Article Link

- Select *Article* from the *CMS Content* drop-down list.
- Select the required article title from the Article dialog. 
- Save the article and try it out using the Preview button in the Toolbar.

### A Menu Item Link

- Select *Menu* from the *CMS Content* drop-down list.
- Select the required Menu item from the Menu dialog. 
- Save the article and try it out using the Preview button in the Toolbar.

## Insert an External Link

For an external link it is best to copy the link from the browser url bar. 
For this purpose it is helpful to have separate windows or tabs open for 
your site *Articles: Edit* form and the remote site you are creating a link to.
Procedure:

- Find or create a sentence that contains the text to be used for the link text. 
  For example:

  *For more information visit see the Wikipedia article on Green Tree Frogs.*
- Select the word or words to be linked, in this case *Green Tree Frogs*.
- Then use either of the following methods: 
  - Select **Insert → Link** from the Article Text menu (the first Toolbar at
    the top of the Content tab).
  - Double click the selected text to open a small popup menu that contains a
    link icon to select.

Either method will open an Insert/Edit Link dialog box to be filled in as
follows:

- In the *URL* field, paste the link copied from the destination window url bar.
- The *Text to display* field should contain the text you selected
  before opening the dialog. If not, any text you type here will be
  inserted into the article so needs to be something that makes
  contextual sense. Reminder: avoid *Click here* or *Read more*.
- The *Title* field creates a link Title attribute but its use by
  browsers is inconsistent and controversial for accessibility purposes.
  If in doubt, leave it blank.
- The *Rel* field has a number of options. If in doubt, leave it set to
  *None*. There is a list of options available in the *mdn web docs* article on 
  [HTML attribute: rel](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel).
- The *Open link in...* field is a simple choice between
  *Current Window* and *New Window*. The browser settings control
  whether that results in a new separate window or a new tab.
- Save the article and try it out using the Preview button in the Toolbar.

## Link Check

In the site view of the page, check that the link looks good and works properly. 
Also, try it with a  Screen Reader!

## Remove a Link

There are several ways to remove a link. Method 1:
- Click on the link.
- Select the ellipsis icon (...) to open the editor's expanded menu.
- Select the *Remove Link* icon.
- Save. The text remains but the link is gone.

Method 2:
- Double click on the link.
- Select the Link icon in the small popup.
- In the Insert/Edit Link dialog, delete the content of the URL field.
- Save. The text remains but the link is gone.

Method 3:
- Deleted the text containing the link. The link and text are both gone.

Method 4:
- Select the link. 
- Select the TinyMCE Edit / Link button.
- In the Insert/Edit Link dialog, delete the content of the URL field.
- Save. The text remains but the link is gone.

## Change a Link

Using any of the methods described above to open the Insert/Edit Link dialog,
paste in a new link URL. Remember: it is always best to copy the URL from the
URL bar of a browser window or tab displaying the destination page and paste
that into the URL field of the Insert/Edit Link form. 
