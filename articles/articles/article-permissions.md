<!-- Filename:  J6.x:Access_Control / Display title: Article: Edit - Permissions -->

## Introduction

Joomla provides a sophisticated *Access Control* system based on 
*Access Levels* and *User Groups*. It is described in the article on
[Access Control](jdocmanal?article=user/users/access-control) in the *Users*
section of this manual. 

The description here is for the *Permissions* tab of the *Article: Edit* form.
Its settings may appear strange unless you are familiar with the Joomla
Access Control system.

## Screenshot

![The article permissions tab with author selected](../../../en/images/articles/articles-edit-permissions-tab.png)

It may be surprising that an Author does not appear to have permission to Edit
an article!

## Frontend and Backend User Groups

If you are unfamiliar with standard Joomla User Groups it helps to know that
*Author*, *Editor* and *Publisher* are frontend user groups. They cannot login
to the backend. Their work in creating, editing and publishing articles is
accomplished with frontend article edit forms. *Manager* and *Administrator*
are user groups with access to both frontend and backend and can edit articles 
using either backend or frontend edit forms.

## Author Edit Access

Why does the Permissions form appear show *Edit* as **Not Allowed (inherited)**
for the Author goup?

There is a simple explanation. If you close the edit form and go to the
*Articles: Options* page via the *Articles* list *Options* button in the Toolbar, 
the *Permssions* tab there shows that a member of the Author group has 
additional permissions: *Create* and *Edit Own*. These are the permissions that 
allow an author to create articles and edit their own articles.

So the permissions in the *Articles: Edit* form do not allow a member of the
Author group to edit articles created by someone else. 