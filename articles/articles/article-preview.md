<!-- Filename: J4.x:Article_Preview / Display title: Article: Preview -->

## Introduction

It can be useful to preview an article before publishing. There is a *Preview*
button in the Toolbar of the backend *Article: Edit* form for this purpose. 
However, this feature uses the saved article and not the content of the editor 
form. The Preview feature is not available in the frontend article edit form.

You may not wish to make an article visible until it is finished. For this 
purpose, different strategies are needed for frontend and backend editors.

## Frontend Preview

The only way to keep an article semi-private from the front-end is to set
its Access to *Registered* so that only logged in users can see it.

- Login to the website frontend.
- Select the *Edit* link for an article to be updated. Or...
- Select the *New Article* button beneath blog layouts.
  - Set the article Access level to *Registered* until it is ready for publication.
  - You could add an *Alert* notice stating that the article is under
    construction: `<div class="alert alert-warning">Under Construction</div>`.
- *Save & Close* to see the article.

## Backend Preview

After login to the Administrator interface:

- Select an article to edit or create and save a new one.
- To keep a new article private for now, set the Status to *Unpublished* or
  leave it *Published* and adjust the *Start Publishing* date.
- Make changes and *Save* the article.
- Select the *Preview* button in the Toolbar. A popup Preview window
  should appear.
- If you get a *The requested page can't be found* message, login to the
  Frontend and try again.
- To close the Preview window select the *X* button at the top right
  corner.

![The preview window](../../../en/images/getting-started/article-edit-preview.png)
