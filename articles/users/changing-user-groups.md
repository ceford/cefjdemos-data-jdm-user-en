<!-- Filename: Changing_user_groups / Display title: Changing User's Groups -->

## Group Inheritance

Group lists use an inheritance pattern. For example, a user in the Author group
inherits all of the privileges of the Registered group and gains some extra
privileges. Likewise, a user in the Editor group inherits all of the privilages
of the Author group and gains some more extra privileges. The backend groups
inherit the highest privilege level in the frontend.

For this reason you only need to select one group for an individual user -
the group with most privileges.

## Steps

You can change a user's group by following these steps. You must log in
as an Administrator or a Super User to be able to change a user's
groups. Also, an Administrator cannot make himself or others a Super
User.

1.  From the *Home Dashboard* select the **Users** item. Or...
2.  From the *User* menu item select **Users** and then **Manage**.
3.  Find the required user in the list of users. You can search on name,
    username, email or id: prefix.
4.  Select the name of the user to edit.
5.  Select the *Assigned User Groups* tab.
6.  Select whichever group a user needs to belong to.
7.  Select *Save*.

## Access Control List (ACL) for Joomla

The following lists the  Access Control
List
(ACL) for Joomla. The user group is listed, and the bullets below
describe the permissions associated with that group.

### Frontend Groups

#### Guest

- View public site and public articles

#### Registered

- Guest Group privileges
- View registered articles
- No access to items restricted to Guest Group

#### Author

- Registered Group privileges
- Create new articles
- Edit articles they own
- View special content

#### Editor

- Author Group privileges
- Edit all articles, including unpublished ones

#### Publisher

- Editor Group privileges
- Publish articles

### Backend Groups

These groups allow you to log into the Administrator via the
*/administrator* URL.

#### Manager

- Publisher Group privileges
- Access Administrator Backend

#### Administrator

- Manager Group privileges
- Create new users
- Install extensions

#### Super User

- Administrator privileges
- Change site template
- Change global configuration
