<!-- Filename: Content_editors / Display title: Content Editors -->

## TinyMCE

**TinyMCE** is the default editor for both Frontend and Backend users.
TinyMCE is a **WYSIWYG** (what you see is what you get) editor that
allows users a familiar word-processing interface to use when editing
Articles and other content.

TinyMCE can be configured with 3 different sets of toolbar buttons

- **Set 2** is assigned to the 'Public' group.
- **Set 1** is assigned to the 'Manager' and 'Registered' groups.
- **Set 0** is the most extended toolbar and is by default assigned to
  the 'Administrator', 'Editor' and 'Super Users' groups.

<img
src="https://docs.joomla.org/images/thumb/f/fb/Help30-editor-tinymce-advanced-en.png/600px-Help30-editor-tinymce-advanced-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/f/fb/Help30-editor-tinymce-advanced-en.png 1.5x"
data-file-width="669" data-file-height="114" width="600" height="102"
alt="screenshot of tinymce advanced tools" />

## CodeMirror

The CodeMirror editor is designed to make it easy to enter HTML code in
an article or description. CodeMirror supports syntax highlighting and
auto-completion, as shown in this screenshot.

<img
src="https://docs.joomla.org/images/thumb/e/e2/Help25-screenshot-editor-codemirror-example-en.png/320px-Help25-screenshot-editor-codemirror-example-en.png"
decoding="async"
srcset="https://docs.joomla.org/images/e/e2/Help25-screenshot-editor-codemirror-example-en.png 1.5x"
data-file-width="326" data-file-height="165" width="320" height="162"
alt="screenshot of codemirror syntax highlight" />

CodeMirror offers some of the same advantages of using No Editor, but
makes it somewhat easier to work with raw HTML code and PHP code in template
overides.

## No editor

If *Editor - None* is selected in a User Profile, then all textarea fields
require you to enter HTML tags yourself. This is inconvenient for editing
Article or Custom Module content but can be useful under some circumstances,
for example to create a PayPal link. In an article you can use the toolbar
*Preview* button to see how the HTML will display when rendered.

TinyMCE automatically re-formats and strips some HTML tags when a file is
saved. This can cause complex HTML not to work correctly. If this happens,
you can temporarily change the editor to *Editor - None* to create the
desired content. Note that if you wish to edit this content in the future,
you should be careful to select *Editor - None* again. Otherwise, if you open
and save the content with TinyMCE, you may lose your custom HTML.
