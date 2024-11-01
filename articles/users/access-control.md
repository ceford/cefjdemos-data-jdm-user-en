<!-- Filename: J4.x:Access_Control / Display title: Access Control -->

## Introduction

Joomla has a sophisticated mechanism for controlling who can see and
manipulate content on a Joomla site. The **who** part is set up in the
Users component options with User Groups and Access Levels. The
**manipulate** part is set up in Action Permissions, either in Global
Configuration settings or in Component settings or in Item settings. For
example, default values set up in Global Permissions can be overridden
in Articles Permissions (all articles) and Articles Permissions can be
overridden in individual Article Permissions.

## User Groups

User Groups are used to divide site users into groups with different
responsibilities. For example, members of the Author user group have
permission to login to the Site, create articles and edit their own
articles. Nothing else! Members of the Super Users group have
responsibility for all aspects of site management and operation. Joomla
provides nine default user groups and you can create more if you need
them.

![Users groups list](../../../en/images/users/access-control-users-groups-list.png)

The default user groups are set up with parent child relationships to
minimise duplication of permissions. Examples of inheritance:

- A member of the Registered group does not have Administrator Login
  permission. Neither do Editor or Publisher.
- A member of the Author group has permission to Create and Edit Own. So
  do Editor and Publisher but they have extra permissions

You can create new user groups for special purposes as required. For
example, you may wish to create a group that has Administrator Login
permission but with access restricted to a single component. There is an
example of such a custom user group towards the end of this tutorial.

## Access Levels

Each time you create an object, such as an article, a module or a menu
item, you will see an Access field, usually in the right column of the
data entry form. It is a drop-down list offering a choice from Public,
Guest, Registered, Special and Super Users. The default is Public. The
default viewing access levels are shown in the following screenshot:

![Users viewing access levels](../../../en/images/users/access-control-users-access-levels.png)

Examples:

- If you create a site module and set Access to Registered it will only
  be seen by users who are logged in to the site.
- If you create a site menu item and set Access to Super Users it will
  only be seen by Super Users who are logged in to the site.

## Permissions

The Global Configuration Permissions are the starting point from which
permission settings in components or individual items may inherit or
override. Screenshot:

![global configuration permissions](../../../en/images/users/access-control-global-configuration-permissions.png)

The screenshot shows that members of the Public group do not have
permission to take any actions. If you select each group in turn you
will see how the permissions change from group to group. Note that
Manager and Administrator are allowed Administrator Login but Author,
Editor and Publisher are not. The latter are effectively Site roles
rather than Administrator roles.

All group permissions inherit from the Public group. It does not have
permission for any actions. However, by default items in the Public
group can be viewed, so assigning Public permission to an item will
allow it to be seen by all site visitors whether logged in or not.

### Articles Permissions

The Articles Permissions actions differ from the Global Configuration
Permissions actions. Not present are items related to login and present
are items related to workflows. This is a fairly typical pattern: a
component will have permissions relevant to the component; a component
item (such as an article) will have permissions relevant to that one
item.

![Content permissions](../../../en/images/users/access-control-global-content-permissions.png)

### Single Article Permissions

The single article permissions has just three items: Delete, Edit and
Edit State:

![single article permissions](../../../en/images/users/access-control-article-permissions.png)

## Access Control Example: Special Purpose User

Suppose you need to create a User Group for users who have only one
responsibility, in this example an Article Administrator. Users in this
group should have Administrator Login permission but should not see
anything other than the Content items. Procedure:

### Create a new User Group

- Select **Users → Groups** from the Administrator menu.
- Select the `New` button in the Toolbar.
- Fill out the Group Title field: Article Administrator
- The Group Parent must be Public - it has no permissions for anything.

![New user group form](../../../en/images/users/access-control-new-group.png)

### Assign to Special

- Select **Users → Access Levels** from the Administrator menu.
- Select the **Special** item.
- Select the Article Administrator checkbox in the **Users: Edit Viewing Access Level** form.
- Save & Close.

![Select access for group](../../../en/images/users/access-control-select-access-for-group.png)

### Global Configuration Permissions

- Select **Home Dashboard → Global Configuration** from the
  Administrator menu.
- Select the **Permissions** tab.
- Select the **Article Administrator** group.
- Set **Adminstrator Login** to Allowed.
- Save & Close

![Select access for group](../../../en/images/users/access-control-article-administrator-global-permissions.png)

### Articles Options Permissions

- Select **Content → Articles** from the Administrator menu.
- Select the `Options` button from the Toolbar.
- Select the **Permissions** tab.
- Select the **Article Administrator** group.
- Set all items except the first two (Configure ACL & Options and
  Configure Options Only) to Allowed.
- Save & Close

![Select access for group](../../../en/images/users/access-control-article-administrator-content-permissions.png)

### Create or Edit User

- Create a new user or edit an existing user who is not assigned to any groups
- Select **Article Administrator** in the **Assigned User Groups** tab
  of the User edit form.
- Save & Close.
- Login as a user in the Article Administrator Group only. The menu
  should show only article-related items:

![Select access for group](../../../en/images/users/access-control-article-administrator-home-dashboard.png)
