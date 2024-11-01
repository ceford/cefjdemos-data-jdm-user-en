<!-- Filename: J4.x:User_Profile / Display title: User Profile -->

## Registration Data

User information collected using the default User Registration form is
limited to Name, Username and Email Address. Site owners often require
additional data such as Address and Telephone data. Such data can be
obtained with the User - Profile plugin.

- Select **Home Dashboard → Plugins** from the Administrator menu.
- Find and open the **Plugins: User - Profile** data entry form.
- In the first part of the form, set to Disabled any items you do not
  wish to appear in the User Registration form.
- In the second part of the form, set to Disabled any items that should
  not appear in the User Profile form.
- Save & Close

![user profile plugin](../../../en/images/users/user-profile-plugin.png)

- If self-registration is allowed, open the User Registration form to
  check that any extra User Profile fields are present.
- From the Administrator menu, create a new user or edit an existing
  user. Select the **User Profile** tab and check that any extra User
  Profile fields are present.

## User Profile Data

A user who has logged in to the front end can be provided with an **Edit
Profile** menu item which links to a profile form. This is a convenient
way for the user to change password and enter any missing profile data.

From the Administrator menu:

- Select **Menus → Main Menu → +** or any other suitable menu.
- Enter a suitable title such as **Edit Profile**.
- In the **Menu Item Type** field use the **Select** button.
- In the popup **Menu Item Type** dialog, select **Users **→** Edit User
  Profile**.
- Set the **Access** field to **Registered**. This is IMPORTANT! the
  menu item should only be seen when logged in.
- Save and Close.

![user profile menu item form](../../../en/images/users/user-profile-menu-item-form.png)

- Login to the site and use the link to check the User Profile.

![user profile menu item form](../../../en/images/users/user-profile-summary.png)

- Try the **Edit Profile** button.
