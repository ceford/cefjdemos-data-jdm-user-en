<!-- Filename: J5.x:Managing_Mail_Template_Layout / Display title: Mail Templates -->

## Introduction

Mail Templates are used to send system email messages in **plain text** or **HTML** or both, selected in the *Mail Templates: Options* form. If only one method is selected the alternative will not be present in the message edit form. 

The following screenshot shows a selection of the 26 standard Mail Templates available. The list is available by selecting **System -> Mail Templates** from the Administrator menu,

![mail templates list](../../../en/images/templates/mail-templates-list.png)

The mail messages can be customised to alter layout, appearance and wording to suit your site’s needs. For example, you might like to use a site logo and colour scheme in those emails sent to customers. Customisation of emails sent to administrators is less important. 

There are two customisation methods: via the *Mail Template: Options* for all mail templates and via *Per Template Mail Settings*.

## Mail Template: Options

Select the **Options** button in the *Mail Templates* list Toolbar to gain access to the overall mail template settings. Select the *Toggle Inline Help* button to see if any of the form fields have extra help.

![mail templates options](../../../en/images/templates/mail-templates-options.png)

### Mail Format

Be aware that a recipient may set a mail client to use simple HTML or Plain Text to avoid download of images. So it may be best to set the *Mail Format* to *Plaintext* or *Both*.

### Per Template Mail Settings

If this is set to **Yes** then individual mail template edit forms have an extra *Options* tab that let you change mail settings for that template and optionally allow you to send a copy (BCC) to a specific email address provided that the **Send Copy** field here is also set to **Enabled**.

## Template Edit Form

In the list of Mail Templates you can select any template to edit. The Title link leads to the edit form for the default English template. Each flag is a link to the same template in that language.

### The Mail tab

![edit mail template form](../../../en/images/templates/mail-template-edit.png)

The contents of the Subject and Body areas are stored in language strings initially. This makes it easy to *Reset To Default Subject* or *Body*. However, once a specific mail template has been edited its Subject and Body fields are stored in the `#__mail_templates` table. 

The items in curly braces are placeholder tags that are replaced by real values when the email is sent. In the example above `{SITENAME}` would be whatever name you chose for your site. `{Method}` would be the selected mail transport method: `PHP Mail`, `Sendmail` or `SMTP`.

The placeholder tags available vary from mail to mail. You could add your own custom placeholder tags but that requires a custom plugin, described in a [Magazine article](https://magazine.joomla.org/all-issues/february-2025/joomla-5-email-templates-how-to-add-variables-via-plugin) from February 2025.

### The Options tab

This tab is only present if the *Per Template Mail Settings* is set to *Yes* in *Mail Templates: Options*. The illustration below shows a screenshot with *Mail Settings* set to *No*. If set to *Yes* more form fields appear that override the Mail options set in the Global Configuration, Server tab.

![edit mail template form](../../../en/images/templates/mail-template-edit-options.png)

If you want to send a blind carbon copy of an outgoing email to a specific email address you can enter it in the *Send Copy To Email* field.

## Mail Template Overrides

To create a mail template override within a custom template:

1. Go to System -> Site Templates -> Open your template (e.g., Cassiopeia).
2. In the Create Overrides tab, select joomla -> mail.
3. Joomla will copy the `mailtemplate.php` file to your template's `/html/layouts/joomla/mail/` directory, where you can modify it as needed.

Once the override is created, you can adjust the layout and styles of your emails without affecting the base template. 

## List of Mail Templates

| Title | Extension | Description |
|-------|-----------|-------------|
| User Actions Log: Notification Mail | User Actions Log | Mail sent to administrators about new entries in the User Actions Log. |
| Global Configuration: Test Mail | Configuration | Sent when you click the "Send Test Mail" button in the Global Configuration. It is sent to the sending mail address that is set in the mail settings. |
| Contacts: Contact Form Mail | Contacts | The "Contact Form" email. |
| Contacts: Contact Form Mail Copy | Contacts | Sent to the submitter of a mail with the contact form if the optional "Send Copy to Submitter" is enabled and selected. |
| Messages: New message | Messaging | Email containing a message created in the messaging component. |
| Privacy: Request Export of Data (Admin) | Privacy | Mail to inform the user that a request to export the data from this website has been created by the administrator |
| Privacy: Request Removal of Data (Admin) | Privacy | Mail to inform the user that a request to remove the data from this website has been created by the administrator |
| Privacy: Request Export of Data | Privacy | Mail to verify that the data of a user should be exported from the website |
| Privacy: Request Removal of Data | Privacy | Mail to verify that the data of a user should be removed from the website |
| Privacy: User Data Export | Privacy | Mail with export of user data |
| Users: Mass Mail Users | Users | The "Mass Mail Users" email. |
| Users: Password Reset | Users | Sent to a user by the "Forgot your password?" link eg in a login form. |
| Users: New account notification to admin | Users | Notification to the admin that a new, activated account has been created. |
| Users: Request to admin to verify new account | Users | Notification to admins to verify a new, verified account. |
| Users: Account activated by admin | Users | Notification sent to the user that the new account has been activated by an administrator. |
| Users: New account with admin activation | Users | Notification about new account to the user, which will now have to be activated by an admin. |
| Users: New account with admin activation (with PW) | Users | Notification about new account to the user, which will now have to be activated by an admin. The cleartext password is included in the mail. |
| Users: New account without activation | Users | Notification about new account to the user. The account is already activated. |
| Users: New account without activation (with PW) | Users | Notification about new account to the user. The account is already activated. The cleartext password is included in the mail. |
| Users: New account with self-activation | Users | Notification about new account to the user, which the user will now have to self-activate. |
| Users: New account with self-activation (with PW) | Users | Notification about new account to the user, which the user will now have to self-activate. The cleartext password is included in the mail. |
| Users: Username Reminder | Users | Sent to a user by the "Forgot your username?" link eg in a login form. |
| Code sent by email | Multi-factor Authentication - Authentication Code by Email | Sent to users from the Multi-factor Authentication page when using the "Authentication Code by Email" option. |
| Task - Privacy Consent: Renew Consent | Task - Privacy Consents | Reminder to renew the privacy consent for this website. |
| Joomla: Update Notification | Task - Joomla! Update Notification | Sent to the site administrators when the "Joomla! Update Notification" task plugin detects an update. |
| Users: New User | User - Joomla! | Sent to a new user when created in the backend. |

