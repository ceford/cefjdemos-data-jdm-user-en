<!-- Filename: Enabling_Search_Engine_Friendly_(SEF)_URLs_on_Apache / Display title: SEF URLs on Apache -->

## Verify .htaccess is Enabled

Check that your Apache config file allows .htaccess overrides. You must
make sure overrides are enabled or the .htaccess file in your Joomla!
root directory will be ignored or cause an error. In the section of your
virtual host configuration file or in the main (`httpd.conf`)
configuration file you must have something similar to the example below
enabling overrides:

```bash
<Directory "/home/user/public_html">
  AllowOverride All
</Directory>

<Directory "/path/to/htdocs">
  AllowOverride All Options=[an option],[an option],...
</Directory>
```

There are other ways to test if `.htaccess` is enabled if you do not
have access to your site's configuration files. Please refer to the
<a href="http://httpd.apache.org/docs/current/howto/htaccess.html"
rel="nofollow noreferrer noopener">.htaccess tutorial</a> found on
<a href="http://www.apache.org/"
rel="nofollow noreferrer noopener">The Apache Software Foundation</a>
website for additional information.

## Step by Step

These are step-by-step instructions. Please follow them in the order
they are presented here. If a step fails, **do not** continue until you
have solved the problem.

1.  Rename the file `"htaccess.txt"` in your Joomla!'s base folder to
    `".htaccess"`.
2.  *This step may not be necessary.* Open `.htaccess` in a text editor.
    Uncomment `RewriteBase /` (remove the first character, \#). If
    Joomla is installed in its own folder, the enter the Joomla folder
    name after the forward slash. e.g. `RewriteBase /yourjoomlafolder`.
3.  Log on to your Back-end and open the Global Configuration.
4.  Enable the **Use Apache mod_rewrite/URL rewriting** option and
    *Save*. This option uses the Apache *mod_rewrite* function to
    eliminate the "index.php" portion of the URL.

    Check if your site works correctly. Your URLs should now look like:

        http://www.example.com/the-­news/1­-latest-­news/1-­welcome-­to­-joomla

    If this option causes errors, please see [How to check if mod
    rewrite is enabled on your
    server](https://docs.joomla.org/How_to_check_if_mod_rewrite_is_enabled_on_your_server "Special:MyLanguage/How to check if mod rewrite is enabled on your server").

    - If it is not enabled and you have access to the file
      `apache/conf/httpd.conf`, open that file and check if the line
      `LoadModule rewrite_module modules/mod_rewrite.so` is uncommented.
      If necessary, uncomment the line and restart the Apache web
      server.
    - If *mod_rewrite* cannot be enabled, leave this option off. It does
      not matter if you leave the `.htaccess` file renamed.
5.  *If you think this necessary*, enable **Add suffix to URLs** and
    *Save*. This option adds `.html` to the end of URLs. There are
    different opinions on whether this is necessary or even useful.
    Search engines do not seem to care if your URLs end in `.html` or
    not.
6.  Open the Plugin Manager and enable the **System - SEF plugin**. This
    plugin adds SEF support to links in your Joomla articles. It
    operates directly on the HTML and does not require a special tag.
