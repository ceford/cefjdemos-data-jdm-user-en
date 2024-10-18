<!-- Filename: Content_editors / Display title: Content Editors -->

## Introduction

Joomla has two default editors described in separate articles: 

- [TinyMCE](jdocmanual?article=user/editors/tinymce-plugin) is the default 
  editor.
- [CodeMirror](jdocmanual?article=user/editors/codemirror-plugin) is designed
  for editing raw html and php source code.

## No editor

If *Editor - None* is selected in a User Profile, then all textarea fields
require entry of HTML tags in those fields that need them. This is inconvenient 
for editing Article or Custom Module content but can be useful under some 
circumstances, for example to create a PayPal link. In an article you can use 
the toolbar *Preview* button to see how the HTML will display when rendered.

TinyMCE automatically re-formats and strips some HTML tags when a file is
saved. This can cause complex HTML not to work correctly. If this happens,
you can temporarily change the editor to *Editor - None* to create the
desired content. Note that if you wish to edit this content in the future,
you should be careful to select *Editor - None* again. Otherwise, if you open
and save the content with TinyMCE, you may lose your custom HTML.
