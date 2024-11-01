<!-- Filename: J6.x:Workflow_Scenarios_Example_2 / Display title: Workflow Example 2 -->

## Introduction

This example involves two users, Alice and Bob, who are respectively the
chairperson and secretary of a committee. The workflow involves the preparation
and approval of agendas and minutes of committee meetings. Charlie is a 
committee member who will have access to committee papers when they are
published. The workflow uses the frontend only.

## User Groups

First create new User Groups all children of *Registered*.

- **Committee** A child of *Registered* 
- **Chair** A child of *Committee*
- **Secretary** A child of *Committee*

![Custom user groups](../../../en/images/workflows/example-2-user-groups.png)

## User Access Level

- Create a new level, **Committee** and add *Committee* to User Groups With Viewing Access.
- In the *Special* Access Level add *Committee* to the User Groups With Viewing Access.

![Viewing Access Levels](../../../en/images/workflows/example-2-viewing-access-levels.png)

## Create Users

- **Alice** in the *Chair* group.
- **Bob** in the *Secretary* group.
- **Charlie** in the *Committee* group.

## Create the Workflow

- **Name** *Committee Workflow*
- **Description** *Workflow for preparation of Committee papers.*
- **Permissions**
  - **Committee** All set to *Inherited* Not allowed (inherited).
  - **Chair** All set to *Allowed* except *Delete*. Perhaps...
  - **Secretary** All set to *Allowed* except *Delete* and *Edit State*.

![Workflows list](../../../en/images/workflows/example-2-workflows-list.png)

### Create the Workflow Stages

- **Draft** 
  - **Note** *Papers in preparation.* 
  - **Permissions** All left at *Inherited*.
- **Review**
  - **Note** *Papers awaiting approval.* 
  - **Permissions** All left at *Inherited*.
- **Publish**
  - **Note** *Papers published.* 
  - **Permissions** All left at *Inherited*.

![Workflow stages](../../../en/images/workflows/example-2-stages-committee-workflow.png)

### Create the Workflow Transitions

#### Draft to Review

This is the normal forward transition in the sequence of stages.

- **Name** *Draft/Review*
- **Transition tab**
  - **Current Stage** *Draft*
  - **Target Stage** *Review*
  - **Note** *Transition to next stage.*
- **Transition Actions tab**
  - **Featuring State** *- None Selected -*
  - **Publishing State** *- None Selected -*
- **Notification tab**
  - **Send Notification** *Yes* Recipients need *Receive System Emails* enabled
    to receive email notifications. 
  - **Additional Message Text** Anything specific to this workflow?
  - **User Groups** *Chair*
  - **Users** An alternative to using User Groups.
- **Permissions tab** All set to **Inherited**.

#### Review to Draft

This is the reversion to a previous stage in the sequence invoked when the
Chairperson requires more work by the Secretary. The form fields are similar
to the Draft/Review fields except for the Note and the *Current Stage* and
*Target Stage* being reversed.

#### Review to Publish

This is the transition that changes the state of an item from *Unpublished*
to *Published*. Only the Chair has permission to make that change.

- **Name** *Review/Publish*
- **Transition tab**
  - **Current Stage** *Review*
  - **Target Stage** *Publish*
  - **Note** *The final transition to publication.*
- **Transition Actions tab**
  - **Featuring State** *- None Selected -*
  - **Publishing State** *Published*
- **Notification tab**
  - **Send Notification** *Yes* Recipients need *Receive System Emails* enabled
    to receive email notifications. 
  - **Additional Message Text** *A committee paper has been published and is now available to view.*
  - **User Groups** *Committee*
  - **Users** An alternative to using User Groups.
- **Permissions tab**
  - **Secretary** Set *Execute Transition* to *Denied*.

#### Publish to Review

This is a change from Publish back to Review. Is it really necessary? A 
published article can still be edited by the Secretary or Chair. Perhaps a 
Committee paper with sensitive data has been published by mistake.

If required, create a Transition similar to the *Review to Publish* transition
but with the Stages reversed, the *Transition Actions / Publishing State*
set to *Unpublished* and a generic *Additional Message Text* message.

#### Archive

This is the transition executed when a Committee paper is no longer needed.
In the workflow it remains in the Publish stage but the article State is
changed from Published to Archived.

- **Name** *Archive*
- **Transition tab**
  - **Current Stage** *Publish*
  - **Target Stage** *Publish*
  - **Note** *Change item state from Published to Archived.*
- **Transition Actions tab**
  - **Featuring State** *- None Selected -*
  - **Publishing State** *Archived*
- **Notification tab**
  - **Send Notification** *No* This is not a transition that requires action. 
- **Permissions tab**
  - **Secretary** Set *Execute Transition* to *Denied*.

![Workflow transitions](../../../en/images/workflows/example-2-transitions-committee-workflow.png)

## Create a New Category

<div class="alert alert-warning">This step is really important! New Committee
papers must be created with this category or they will take on the default
workflow that needs a Super User to change.</div>

- **Title** *Committee* 
- **Workflow** Select *Committee Workflow* from the Workflows list.
- **Permissions** 
  - Author, Editor and Publisher: All set to *Not Allowed* or left at 
    *Not Allowed (Inherited)*.
  - Committee: All left at *Inherited*.
  - Chair: All except *Delete* set to *Allowed*.
  - Secretary: All except *Delete* and *Edit State* set to *Allowed*,

## Create a Menu Item

- **Title** *Committee Papers*
- **Menu Item Type** Category List
- **Choose a Category** *Committee*
- **Access** *Committee*

![Committee papers menu item](../../../en/images/workflows/example-2-menu-item.png)

## Check the Site

Login as Alice, Bob, Charlie and a Super User in turn to see what they can see:

Alice, Bob and Charlie can see the Menu item but nobody else can, not even 
a Super User. After selecting the menu item, Alice and Bob can see a table of 
Committee papers including any that have not been published. Charlie can only
see a table of published Committee papers or an explanatory message if none
have been published.

Alice and Bob can also see an Edit link for each article and a **New Article** 
button. This is usually used by Bob to create a Committee paper but Alice can 
do that too.

![Bob's view of the committee papers category list page](../../../en/images/workflows/example-2-committee-papers.png)

### To Create and Publish a Committee Paper

- Login as a Secretary and select the **New Article** button in the 
  *Committee Papers* page.
- Enter the text and *Save*. This can be done over several edit sessions, 
  perhaps over several days or weeks. The article remains Unpublished and in 
  the Draft stage until...
- Select the *Publishing* tab in the edit form and set the *Workflow Stage* to 
  Run Transition **Draft/Review**. 
- Select **Save & Close** to run the transition.
- The work of the Secretary is complete for now and a message has been sent to
  the Committee Chair.
- The Chair logs in, checks the paper ready for Review and uses the 
  **Review/Publish** transition to make the paper *Published*. The work of the
  Chair is complete for now and a message is sent to the Committee members.
- Committee members can login and access the published paper.

QED!
