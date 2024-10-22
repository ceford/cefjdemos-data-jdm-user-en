<!-- Filename: J4.x:Deleting_an_Article / Display title: Articles: Delete -->

## Introduction

In Joomla, deletion of an article is a two stage process. The first stage sends 
it to the *Trash* from where it may be restored. The second stage deletes it
from the Trash after which the article is removed permanently.

## Considerations

Consider why you want to delete the article:

- Is it no longer needed? If so, deletion is most likely the right
  course of action.
- Is it an article that could be re-used in the future? It can be very
  frustrating to know you had an article that would have been a good
  starting point for another but you deleted it - consider archiving it
  instead.

## Moving the Article to Trash

- Select **Content -> Articles** from the Administrator menu.
- Select the checkbox to select the article you want to delete. An article 
  **must** be selected to enable the **Actions** button in the toolbar.
- Select the **Actions** button in the Toolbar.
- Select **Trash** in the dropdown menu.

![Article selected for trashing](../../../en/images/articles/articles-selected-to-trash.png)

There will be a confirmation message and the article will have disappeared from 
the current list of articles as it does not normally include trashed items.

## Filter to Restore or Delete

At this stage of the process the article has not been completely removed. This 
is a helpful feature in case you deleted the article by mistake.

To see the list of trashed articles:

- Select the **Filter Options** button to open the list of filters.
- Select **Trashed** from the *-- Select Status --* list.

![Article trash view](../../../en/images/articles/articles-trash-list.png)

### To Restore

If you have change your mind you can select the **Trashed** symbol in the
*Status* column. The article will return to the *Published* state and disappear
from the list of trashed articles.

### To Delete

Select the checkbox in the left column of article data. That will enable the
*Actions* and *Delete* buttons in the Toolbar. The *Actions* button allows you
to apply the same action to all of the selected articles. If you are really sure: 

1.  Select the *Delete* button in the Toolbar. A message box will appear:<br>
    <div class="alert alert-light">
    Are you sure you want to delete? Confirming will permanently delete the 
    selected item(s)!</div>
2.  Select **OK** to confirm and the article will be deleted from the Trash. The 
    article will be deleted from the database. It is gone, permanently!
3.  Select the **Clear** button at the side of **Filter Options** to return to 
    the unfiltered **Articles** list.

## Tips

- Remember, deleting an article is not the same as archiving an article.
  Once it has been deleted from Trash it has gone for good.
- If you delete an article by mistake but have not deleted it from
  Trash, you can change its status. You have the options to set it as
  *Archived*, *Published* or *Unpublished*.
- Joomla will not let you save more than one article with the same
  alias. If an article is deleted but left in the Trash, it still exists. If
  you try to save an article and you get an error stating the alias
  already exists, it may be in the Trash! You should therefore either
  empty it from trash or you can enter a different alias for your new
  article.
- Joomla keeps previous versions of an article unless Versions is disabled. If
  you are deleting an article because it somehow "broke", try reverting
  it back to a previous version.
