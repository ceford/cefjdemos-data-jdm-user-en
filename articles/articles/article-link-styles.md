<!-- Filename: J5.x:Add_a_class_selector_to_the_create_link_dialog / Display title: Article: Edit - Link Styles -->

## Description

Custom link classes added to the TinyMCE editor options allow you to quickly transform an article link into a button or to add other visual effects without having to modify HTML code directly.

### Steps to Use the Class Selector

1. From the Home Dashboard, go to the Plugins list and find the TinyMCE plugin.
2. Open the TinyMCE plugin and with the Plugin tab selected scroll down to the bottom.
3. Add classes to the *Link Classes List* For instance, Bootstrap classes to create stylish buttons. You may need to scroll the list left to right or change screen magnification to see see the add, remove and order buttons at the end. 
4. Save & Close.

![Set link classes in tinymce](../../../en/images/articles/article-edit-link-style-tinymce.png)

You can find examples for templates that natively use Bootstrap in the official [Bootstrap Documentation](https://getbootstrap.com/docs/5.3/components/buttons/)

Here are some classes you can use for Bootstrap button variants:

- `btn btn-primary` for a primary button
- `btn btn-secondary` for a secondary button
- `btn btn-success` for a success button
- `btn btn-danger` for a danger button
- `btn btn-warning` for a warning button
- `btn btn-info` for an info button
- `btn btn-light` for a light button
- `btn btn-dark` for a dark button
- `btn btn-link` for a link button

#### Outline Button Alternatives

You can also use the outline button variants:

- `btn btn-outline-primary` for an outlined primary button
- `btn btn-outline-secondary` for an outlined secondary button
- … (etc.)

#### For button sizes, add these classes

- `btn-lg` for a large button
- `btn-sm` for a small button

**Example:** `btn btn-dark btn-lg` (a large dark button)

## Create a link in an article

1. Open an article and select some text, a word or phrase, for link creation. 
2. Select the Link icon that appears when you select some text.
3. Enter the URL for the link.
4. At the bottom of the link creation dialog, select one of the configured classes.
5. Save the Link.
6. Save the Article.
7. Preview the Article

![Apply link style in an article](../../../en/images/articles/article-edit-link-style-apply.png)

And this is an example where the Link Button class was set to `btn btn-sm btn-outline-info` and the linked text is *Bootstrap*:

![Preview of a custom Link Button](../../../en/images/articles/article-edit-link-style-preview.png)

## Advanced Use: Applying Custom Classes

This feature isn’t limited to Bootstrap classes. You can also apply your own custom CSS classes for specific needs. For example, you can add an icon before the link with a hover effect. This makes it easy to style links without needing to modify the article's source code. 