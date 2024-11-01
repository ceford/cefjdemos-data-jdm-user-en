<!-- Filename: J4.x:Workflow / Display title: Publishing Workflow -->

## Introduction

In Joomla, a workflow is a sequence of steps in the life of an article from
conception to demise. The steps are usually performed by different individuals
with different responsibilities. For example, in the newspaper world a 
sub-editor takes a story from a reporter and checks for accuracy, grammar,
readability and length, and perhaps more. The sub-editor will then pass the
story to the editor who may accept or reject the story, decide where to place
it in the paper, and so on. 

The Workflow component is used to add **stages** to articles to enhance the 
static states (unpublished, published, trashed and archived) with 
**transitions**. The static states and transitions are recorded separately so 
that Workflows can be enabled or disabled as required without affecting the 
state of content items. Workflows are enabled or disabled in the 
*Articles: Options* page *Integration* tab. 

There is a tutorial page containing steps for the creation an example
workflow: [Workflow Scenarios](jdocmanual?article=user/workflows/workflow-scenarios).

## Terms & Definitions

- *Workflow:* A workflow is a complete sequence of steps. Several different 
  workflows can be created for different purposes. The Workflow component
  contains a *Basic Workflow* and the Blog sample data has a more complex 
  *Blog Workflow*. 
- *Stage:* A stage is a location within a workflow. For example, an unpublished
  article may be at Stage 1: In Preparation or Stage 2: Ready for Review, and
  so on. It is the stage for the item that is recorded in the database.
- *Transition:* A transition is a change from one stage to another, often to the 
  next in the workflow but could be to the previous stage or initial stage.
- *State:* The state of an article can be unpublished, published, trashed
  or archived. A state can be changed by executing a workflow transition 
  provided that the user has permission to change state.
- *Category:* When workflows are in use, a specific Workflow can be selected for
  a category in the *Article: Edit Category* form *Workflow* tab.

## The Workflows List

When workflows are enabled the list of available workflows can be seen by
selection of **Content → Workflows** from the Administrator menu.

![Workflows list](../../../en/images/workflows/workflows-list.png)

- The **Status** of a workflow may be Enabled, Disabled or Trashed.
- The **Name** is a link to the workflow Edit form.
- The **Default** item is used for new items that are not assigned to a
  category that has a defined workflow.
- The **Stages** item is a button showing the number of stages and a link
  to the list of stages for the workflow.
- The **Transitions** item is a button showing the number of transitions and 
  a link to the list of transitions for the workflow.
- The **ID** is a the numerical value of the workflow used internally.

## Stages

The stages are accessed via the *Workflows* list. Select the yellow button
showing the number of stages. 

![Workflow stages list](../../../en/images/workflows/workflow-stages-list.png)

Select the name of a stage to edit it.

![Workflow stage edit form](../../../en/images/workflows/workflow-stage-edit.png)

## Transitions

In workflows, articles transition from one stage to another. The transitions are
managed through the *Transitions* list.

![The transitions list](../../../en/images/workflows/workflow-transitions-list.png)

- The *Current Stage* defines where this transition starts.
- The *Target Stage* defines where this transition ends.

### Transition Stages

The *Current* and *Target* stages are set in the *Edit Transition* form:

![Edit transition form](../../../en/images/workflows/workflow-transition-edit.png)

The *Transition Actions* tab is used to define the *State* the item will be in 
after the transition is complete. 

![Edit transition form actions tab](../../../en/images/workflows/workflow-transition-edit-actions-tab.png)

- **Featuring State** Whether or not the item will be *Feaured*.
- **Publishing State** Select from the list the target state.

The *Transition Notifications* tab is used to define whether a notification is 
sent for that state. For example if an article has been written but needs to 
be proofread, an email could be sent to notify the editor.

![Edit transition form notifications tab](../../../en/images/workflows/workflow-transition-edit-notifications-tab.png)

- **Send Notification** If set to *Yes* extra fields appear.
- **Additional Message Text** Add additional message text or use a language
  string to make the message text translatable.
- **Usergroups** Select who will receive the notification, for example all users
  in the *Editor* user group.
- **Users** Select individual users to receive this notification.

### Permissions

The permissions tab controls access to this transition by selected user groups.
Normally the permissions are inherited form the Permissions in the 
*Articles: Options* permission settings.

### Workflow Transition Plugins

The workflow plugins are used for actions invoked by transitions. Go to 
**System → Plugins** and change the *- Select Type -* filter to *workflow*.
Each of this plugins can be disabled if not required.

![Workflow plugins list](../../../en/images/workflows/workflow-plugins.png)

- **Workflow Featuring** This action implements the change of an article's
  *Featured* status from *Yes* to *No*.
- **Workflow Notification** This action implements notification of a user
  that a change of stage requires attention.
- **Workflow Publishing** This action implements a change of state of an
  article from one to another of *Published*, *Unpublished*, *Trashed* or
  *Archived*. If the user does not have permission to change state it will fail
  with an explanatory message. The transition that requested the change of
  state will still succeed!

## Categories

Articles can be assigned to categories. They correspond to a certain
workflow and can be customized in various ways. You can set a status,
parent category and also restrict the access as well as the permissions.
This option is not within the workflows screen. For this option you need
to go to **Content → Categories**. Once there open any category and you
will see a *Workflows* tab.

![Articles edit category workflow](../../../en/images/workflows/workflow-categories-blog.png)

### Example

Certain articles need to be available only for administrators or users of a 
higher rank.

- Create a category named *Restricted*
- Set all permissions on *Allowed* for administrators or higher. 
- Move the articles concerned to the *Restricted* category.

This saves setting permissions on individual articles,

## Versioning

When the workflow is enabled fields managed by the workflow are excluded
from the versioning (like "state" and "featured") to avoid permission
conflicts.

## Examples

Some specific examples are available to illustrate how to use Workflows for
different user groups:

- [Example 1](jdocmanual?article=user/workflows/workflow-example-1) makes use
  of the default Author, Editor and Publisher user groups to prepare items
  for a Newsletter.
- [Example 2](jdocmanual?article=user/workflows/workflow-example-2) makes use
  of custom user groups to prepare items for committee meetings.
