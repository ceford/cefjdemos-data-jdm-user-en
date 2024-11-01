<!-- Filename: J6.x:Workflow_Scenarios_Example_1 / Display title: Workflow Example 1 -->

## Introduction

A workflow consists of *stages* and *transitions* between those stages. For any
article it is the current stage that is recorded in the database and 
used to identify the workflow and the transitions used by that workflow.

A single site may have many workflows. Here, a *Newsletter Workflow* is used
as an example to explain how three individuals with different roles may be 
involved in the production of a newsletter article. The example uses the
Joomla default Author, Editor and Publisher user groups. That has a problem: an
Author can only see Published articles so cannot re-edit Unpublished articles.
A method to avoid that problem is covered in [Example 2](jdocmanual?article=user/workflows/workflow-example-2).

![Workflows list](../../../en/images/workflows/example-1-workflows-list.png)

Notice that the *Basic Workflow* is set as the *Default*. This may have
troublesome consequences covered later in this article! 

## The Users

- *Arthur* is a user assigned to the Joomla **Author Group**. He can create new
  articles and edit his own articles but he cannot edit articles written by
  other users or change the state of articles. So he cannot publish his own
  articles. His job is to draft new articles.
- *Eddie* is a user assigned to the Joomla **Editor Group**. He can edit
  articles created by any other user, including Arthur and himself. He also
  cannot change the state of an article. His job is to review the articles
  submitted by Eddie, check for accuracy, spelling and grammar, quality
  of images and so on.
- *Pru* is a user assigned to the Joomla **Publisher Group**. She can do 
  anything that Eddie and Arthur can do. In addition, she can change the State
  of an article. It his her job to decide whether an article is acceptable for
  publication and to publish it.

## The Stages

There are four stages in this Workflow:

![Workflows list](../../../en/images/workflows/example-1-workflow-stages.png)

- **Draft** is the stage created by Arthur for a new article.
- **Review** is the stage where Eddie takes over to proof read the content.
- **Approve** is the stage where Pru takes over to decide whether the
  article is good enough to publish.
- **Publish** is the stage when the article has been approved and published.

The stage data entry forms need little explanation, just a Name and Description.

## The Transitions

Two transitions are required between each stage: one to revert the stage
if more work is required in the previous stage; and a second to migrate
to the next stage. Extra transitions are required to handle the demise of
an article:

![Workflows list](../../../en/images/workflows/example-1-workflow-transitions.png)

- **Draft/Review** to move the stage form Draft to Review.
- **Review/Draft** to revert the stage from Review to Draft.
- **Review/Approve** to move the stage from Approval to Review.
- **Approve/Review** to revert the stage from Approval to Review.
- **Review/Publish** to move the stage to Published and change the article
  status to *Published*.
- **Publish** To set the article state to *Published* when the transition is
  executed by an Author or Editor.
- **Unpublish** to change the article status to *Unpublished*.
- **Archive** to change the article status to *Archived*.
- **Trash** to change the article status to *Trashed*.

The last three transitions allow Pru to change the status of an article when 
it is no longer needed.

### Edit Transition

The date entry form has four tabs starting with the *Transition* tab:

![Workflows list](../../../en/images/workflows/example-1-edit-transition.png)

- **Name** It is best to use the Current and Target stages in the name.
- **Current Stage** The stage before the transition takes place.
- **Target Stage** The stage after the transition has taken place.
- **Note** Any explanatory notes to help explain the transition.

#### The *Transition Actions* tab:

![Workflows list](../../../en/images/workflows/example-1-edit-transition-actions.png)

- **Featuring State** Define the featured state an item should have after 
  executing this transition. Leave this at *-Non Selected-* if the user likely
  to execute this transition does not have permission to feature articles.
- **Publishing State** Define the published state an item should have after 
  executing this transition. Leave this at *-Non Selected-* if the user likely
  to execute this transition does not have permission to change article state.

#### The *Notifications* tab:

![Workflows list](../../../en/images/workflows/example-1-edit-transition-notification.png)

- **Send Notification** Set this to *Yes* where notifications are necessary, for
  example when Arthur needs to notify Eddie that an article is ready for review.
- **Additional Message Text** This is generic additional text to help the
  recipient.
- **Usergroups** You can choose to send the notification to one or more user
  groups or none and send notification to individuals instead.
- **Users** Select individual users from the list of users.

#### The *Permissions* tab:

Note that *Author* has *Execute Transition* set to Allowed (Inherited). Do not
change these settings for other transitions that an Author should not use as
this will also affect Editors and Publishers.

## The Article Category

Each article is assigned to a workflow on first save. If the article is first
assigned to a Category that has a Workflow selected it is assigned to that
workflow. Otherwise it is assigned to the default workflow. That my be
troublesome because the Workflow component does not provide a method to change
the workflow once allocated. It can be changed by a Super User using the Batch
Action in the Articles list page. 

### Create a Newsletter Category

A new Newsletter category is needed to display the Newsletter as a Category
Blog and to ensure the Newsletter articles are assigned to the Newsletter
Workflow.

![Workflows list](../../../en/images/workflows/example-1-newsletter-category.png)

## The Newsletter Menu Item

For site visitors to see the Newsletter it needs to be the Home page or linked
with a menu item. To follow this example create a new menu item of type
*Category Blog* using the *Newsletter* category. 

Try out the site menu item. It is likely to be a blank page with this message:

<div class="alert alert-info">
There are no articles in this category. If subcategories display on this page, they may have articles.
</div>

## Login as Arthur

Remember Arthur the Author? After login, the Newsletter page should have a
button labelled **New Article**. Select it to compose a new article.

### Compose an Article

Fill out the article edit form as you would for any article. Except, before
the first save look at the *Publishing* tab.

- **Workflow Stage** should be set to **Run Transition** *Draft/Review*.
- **Category** should be set to *Newsletter*.

When you have finished editing the article select *Save* or *Save & Close*.

<div class="alert alert-danger">After closing the article Arthur cannot edit
it again because users in the Author group cannot view Unpublished articles.</div>

## Login as Eddie

Eddie the Editor does have permission to view Unpublished articles so the
Newsletter page does show any Unpublished items for him to edit.

### Review the Article

Select the article drafted by Eddie and make any changes required to make it
better. When satisfied, in the *Publishing Tab*:

- **Workflow Stage** should be set to **Run Transition** *Review/Approve*.

Unlike Arthur who cannot see his article after saving, Eddie can see and edit
the article again. He can also set the transition for the next stage to
Approve/Publish. The transition will work but the article will not be published
as Eddie does not have Publish permission.

## Login as Pru

When the Approve stage was set in the workflow, Pru should have received a
message prompting action. So login as Pru to review the article and set its
Workflow Stage to **Run Transition** *Publish*. *Save & Close* the article
to see the published result. Logout to see the result without the Edit link,

Afterthought: another stage is needed to allow Pru to revert the stage from
Publish to Review if she wants Eddie to fix something.

## Backend Workflow

The Author, Editor and Publisher user groups are intended for frontend use. 
The problem for Arthur is that he cannot access his draft articles from the
frontend because his user group does not hae viewing access for unpublished
articles. 

You can allow backend access for all members of these groups as follows:

- Go to the **Global Configuration** page.
- Select the **Permissions** tab.
- Select *Author* and set **Administrator Login** to *Allowed*.
- **Save**
- Go to the **Articles: Options** page.
- Select its **Permissions** tab.
- Select *Author* and set **Access Administration Interface** to *Allowed*.

This will allow Arthur, Eddie and Pru to login to the backend wih access to
the Content items. A much reduced Home Dashboard:

![Home dashboard for arthur](../../../en/images/workflows/example-1-backend-home.png)

But Arthur has access to his draft articles:

![Article list for Arthur](../../../en/images/workflows/example-1-backend-articles.png)

Notice that Arthur cannot edit the last item in the list because it is not
one of his own articles. The article title is not linked. Similarly, Arthur
cannot edit any of the existing categories because he does not have permission
and they too are not linked. He can create a new Category but it is Unpublished
and he cannot publish it!

## Fix for Wrong Workflow

If you assign an article to the wrong workflow there are two methods available
to fix the problem.

### Super User Method

- Go to the **Articles** list.
- Select the checkbox for the problem article.
- Select the **Actions** button in the Toolbar.
- Select the **Batch** button from the list.
- Select **Change Stage** from the *Batch Process Selected Articles* dialog.
- Select an appropriate target Workflow and Stage.
- Select the **Process** button.

![Article list for Arthur](../../../en/images/workflows/example-1-backend-batch.png)

### Fallback Method

Alternatively, you can edit a database table with phpMyAdmin or similar.

Information required:

- The ID of the article from the last column in the Articles list.
- The ID of a stage in the required workflow from the last column of the
  Stages list of the Workflow you would like to use.

In phpMyAdmin:

- Browse the #__workflow_associations table to find the item_id that contains
  the ID of your article.
- Change the stage_id value to the stage ID that you looked up in the required
  workflow.

Go back to your articles list and check that the problem item is now using 
the correct workflow.
