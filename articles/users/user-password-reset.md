<!-- Filename: J4.x:User_Password_Reset / Display title: User Password Reset -->

## User Reset

If your users are allowed Site login and a user cannot remember either
Username or Password it is best to require the individual to self-reset
credentials using the links in the Login form:

![site user login module](../../../en/images/users/user-site-login-module.png)

In each case, selecting a link leads to a form for entry of the email
address associated with the account:

![site forgot password reset form](../../../en/images/users/user-forgot-password-reset.png)

All of the process is accomplished by the user with no intervention
required from an Administrator. This is the lost password verification
form:

![site forgot password confirm form](../../../en/images/users/user-forgot-password-confirm.png)

And finally, the user is required to enter a new password:

![site forgot password reset form](../../../en/images/users/user-forgot-password-complete.png)

## Administrator Reset

If there is only Administrator login then a user password reset must be
accomplished by a Super User or Administrator. If it is the only Super
User who does not know the login credentials then see the separate
article on Administrator Password Recovery. Otherwise:

- Select **Users → Manage** from the Administrator menu or select
  *Users* from the Home Dashboard Site panel.
- Find the user who needs a password reset.
- Select the linked **Name** to open the *User: Edit* form.
- Enter a new password in Password and Repeat Password fields.
- Set the **Require Password Reset** field to *Yes*.
- **Save & Close**

![administrators user edit form](../../../en/images/users/users-edit-user-john-doe.png)

You will then need to send an email to the user with the new interim
password in plain text. After login, the user will be able to see the
site Home page but any attempt to navigate to any other page will take
the user to the new password form.
