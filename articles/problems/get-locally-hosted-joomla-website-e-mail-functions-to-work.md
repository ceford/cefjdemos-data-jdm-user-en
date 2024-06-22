<!-- Filename: Get_locally_hosted_Joomla!_website_e-mail_functions_to_work / Display title: Local Host Email -->

## Local Hosting

Most ISPs block port 25 so you cannot send email from your own computer's
SMTP server. This is to block spammers. If you don't intend to spam, you can
use your ISP's mail server.

To use the email function from your ISP SMTP server even if you are
hosting your own Joomla site on your own computer, sign in to your Joomla site
as a Super User and navigate to the **Server** tab of the **Global
Configuration** page. In the **Mail** section your data should look
like the following:

    From Email: someone@example.com (usually you)
    From Name: SomeName

    Mailer: SMTP
    SMTP Host: smtp.charter.net (Whatever your ISP tells you to use for their SMTP servers)
    Sendmail Path: /usr/sbin/sendmail
    SMTP Port: 25
    SMTP Security: STARTTLS
    SMTP Auth: Yes (or No)
    SMTP Username: johndoe (username at one of your email accounts at your ISP)
    SMTP Password: trr33459 (password at one of your email accounts at your ISP)
Send a test message to check it is working.

The SMTP Username, Password, and Host are the same fields you enter when adding
an Outlook Express Account, or Eudora, or any client email you may use
on your computer.

You may run into problems with extensions that change the *From* address
in the emails being sent out. For example, the ProjectFork extension
sometimes sends emails as if they are coming from person in control of
the project. This can cause a problem because some ISP SMTP servers will
not allow a "from" address that does not match the user name (e.g.
Rogers in Canada). You will get a message like this:
"PHPMAILER_FROM_FAILEDname@whatever.com." A work around is to make sure
that you always use a valid email address from you ISP for your users.
