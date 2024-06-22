<!-- Filename: Search_Engine_Friendly_URLs / Display title: Search Engine Friendly URLs -->

## Paths and Routes

SEF URLs make sense to both humans and search engines because they explain the
path to the particular page they point to. A **path** is the location of a file
in a directory tree or its simulation in code. Internally, the local part of a
SEF URL (the part after the domain name) is called a **route**. Creating and
processing SEF URLs is therefore referred to as **routing**, and the relevant
code is called a **router**.

Search engine friendly URLs can be activated with the following steps:
* In **Global Configuration**
    - set the **Search Engine Friendly URLs** option to **Yes**.
    - Set the **Use URL Rewriting** option to **Yes**
    - Optional: Set the **Add Suffix to URL** option to **Yes**.
* In the site root, rename htaccess.txt to .htaccess if you are using an
Apache server, or consult the external documentation for NginX or other
servers.

An example of routing can be seen in the incremental effect these changes have
on the URL of the **Articles** Category Blog page in the sample data.

- With SEF URLs turned off in Global Configuration and .htaccess disabled, the
URL is something like `https://www.example.com/index.php?option=com_content&view=category&layout=blog&id=16&Itemid=125` and the breadcrumbs shows:<br>
 *You are here: Home / Sample Layouts / Articles*
- With SEF URLs on but no URL rewriting, it becomes:
  `https://www.example.com/index.php/sample-layouts/articles`
- With both SEF URLs on, URL Rewriting on and .htaccess enabled it becomes
  `https://www.example.com/sample-layouts/articles.html` (Add Suffix to URL
  set to Yes).

## Numbers in non-SEF URLS

In the part of the URL that says `id=16&Itemid=125` the numbers are the
parameters needed to locate the internal URL and show the required page. In
this case, the first numeral is the ID of a Category and the second numeral
is the ID of the Category Blog menu item for that Category.
