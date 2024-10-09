<!-- Filename: J4.x:Logging_in_to_Joomla / Display title: Logging in to Joomla -->

## Introduction

One of the great things about Joomla! is that it offers the flexibility
to carry out tasks through the Administrator Dashboard (often referred
to as the backend) and, if enabled, to carry out tasks directly from the
frontend (the public facing) part of the website.

Frontend access is an easy and efficient way to allow content writers to
quickly add or edit articles without the need to go to the Administrator
Dashboard.

Joomla login is configured to control what users can see and do (or
can't) using Joomla's User component and powerful Access Control Levels
(ACL). This means that a Joomla website may have users that only use the
backend, some that only use the frontend and others that use both.

The following covers logging in and out from both the backend and
frontend of a Joomla website.

**Note:** A Joomla Administrator may have disabled frontend access,
requiring all tasks to be carried out using the backend Administrator
Dashboard.

### Administrator Login

Navigate to the Administrator Login page. This is the web address for
the website appended with /administrator, for example,
my-joomla-website.com/administrator which invokes the Joomla Administrator 
login page:

![Administrator login form](../../../en/images/getting-started/logging-in-to-joomla-administrator-login-form.png)

1.  Add your **Username**
2.  Add your **Password**

Select the **Log in** button to be taken to the Joomla! Home Dashboard.

**Note:**

1.  Joomla provides an option to set up and use Web Authentication. 
    This is not within the scope of this tutorial.
2.  If a website has several languages installed you will be able to
    select a language to use from a dropdown list before logging in.

### Administrator Logout

To log out select the **User Menu** then **Log out**.

![Administrator logout link](../../../en/images/getting-started/logging-in-to-joomla-logout-link.png)

### Site Login

If frontend access is enabled, a login form will have been added to the
website. Joomla allows a number of ways to do this. A standard
installation includes a login form in the sidebar of the website but you
may find a link has been added to the website menu, or perhaps in the
footer. In some cases a *Create Page* link may exist. The design of the
website will dictate where you access the login form.

This example uses a login form located in the right sidebar.

![Site login form module](../../../en/images/getting-started/logging-in-to-joomla-site-login-form.png)

In the **Login Form**

1.  Add your **Username**
2.  Add your **Password**

Select the **Log in** button.

When logging in from the frontend of the website, you may be kept on
the same page that you logged in from or you may be taken to your Profile page. 
You will notice the login form will also contain a **Log out** button.

### Site Logout

![Site logout form module](../../../en/images/getting-started/logging-in-to-joomla-site-logout-form.png)

To logout go to the login form and select the **Log out** button.

## Tips

- Some Joomla website administrators install extensions that hide or
  restrict access to the backend Administrator Dashboard. You may have
  to take additional steps or visit an alternative login URL.
- If you are making edits using the frontend login, save time by logging
  in on the page you wish to edit.
