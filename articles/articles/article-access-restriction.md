<!-- Filename: J6.x:Article_Access_Restriction / Display title: Article: Access Restriction -->

## Introduction

There are several reasons for restricting access to articles on a web site.
Some content may be private to specific users, such as members of a committee.
Or the site may contain pay-to-view commercial content. Joomla provides a 
powerful Access Control List (ACL) system for restricting access. It is 
described in a separate article on [Access Control](jdocmanual?article=user/users/access-control)
in the User section of this manual. 

This article describes the implementation of access restriction  in the 
*Article: Edit* form. 

## Restriction by Access Level

Joomla provides the Access Levels seen in the following screenshot:

![User access levels](../../../en/images/articles/article-access-user-groups.png)

The access levels appear in the *Content* tab of the *Article: Edit* form.

- **Public** Can be viewed by everyone - both users who are logged and users
  who are not logged in.
- **Guest** This access level restricts access to users who are **NOT**
  logged in.
- **Registered** This level restricts access to users who are logged in.
  An article with *Access* set to *Registered* will require a front end login 
  before the article can be viewed.
- **Special** This level restricts access to users who are logged in and
  are in a specific user group other than Registered. In addition, it is
  possible to differentiate content that some logged in users can access
  but others can't. Typically this might be a website where subscriptions
  are required to access additional content.
- **Super Users** Setting this level means only a Super User can access
  the article. This might be used for articles on site management.

Note that this list is about **Viewing** or having permission to view content.
You can create additional Access levels and User Groups to customise who can
see what.

## Partial Restriction to Read More

Sometimes you might wish to restrict access to an article but allow unrestricted
access to a taster for the article. This is a common way to implement paid
for access to commercial content. Procedure:

- Find the article to be partially restricted in the *Articles* list and open
  it for editing.
- Insert a *Page Break* after the first paragraph. The Page Break tool is near
  the bottom of the *CMS Content* list in the TinyMCE article edit form.
- Set the article *Access* level to *Registered*.
- Select **Save & Close** in the Toolbar.

### Restricting access to Articles individually

Open the *Category Blog* or *Featured Articles* menu item where the article will
appear.

- In the **Options** tab, set **Unauthorized Links** to **Yes**. It is at the
  bottom of the list of Options.
- Select **Save & Close** in the Toolbar.

### Restricting access to Articles Globally

* Set the relevant Categories to view level *Public*, otherwise menu items
  will not be visible to users who are not logged in.
* Set the articles in the relevant Categories to view level Registered. This
  can be done by selecting the articles and using the *Batch* button.
* Go to **Content → Articles → Options**
* Set **Unauthorised Links** to **Yes** in the Articles tab. If set to Yes, 
  links to registered content will be shown even if you are not logged-in. 
  You will need to log in to access the full item.

**Note:** Text in an Article without a *Read More* break is treated as all Intro
text. If you have an Article that is supposed to be restricted to Registered
users only but does not have a Read More then the whole article will be visible
to all users. So add a Read More to the article!
