<!-- Filename: Adding_www_to_a_url / Display title: Adding www to a url -->

## Apache .htaccess Regular Expressions

For a simple solution, add the following to your `.htaccess` file:

```bash
    RewriteEngine On
    RewriteCond %{HTTP_HOST} !^(www\.example\.com)?$ [NC]
    RewriteRule (.*) https://www.example.com/$1 [R=301,L]
```

In this case a URL of the form `https://example.com/index.php?item=1` will be
redirected to `https://www.example.com/index.php?item=1`.

In the example above:

* `RewriteCond` defines a test condition.
* `%{HTTP_HOST}` uses the host variable from the request (example.com).
* `!` means NOT and `^` means START - so, does not start with www.example.com
* `(` and `)` capture whatever is between the brackets for backreference use.
* `\` turns the next character from a control character to an actual character
* `.` usually means any character but preceded by \ it means a full stop.
* `?` makes the match optional
* `$` means END (of the optional match).
* `[NC]` stands for No Case meaning case insensitive.
* `RewriteRule` is valid if the url does not start with www.
* `(.*)` is a pattern, in this case a single character repeated 0 or more
    times, meaning the path part of the URL. It is captured as $1.
* `https://www.example.com/` is the replacement for the host part of the URL.
* `$1` is the captured path.
* `[]` contains flags - instructions on what to do.
* `R=301` is an instruction to send a Moved Permanently header.
* `L` means Last in set - as a match has been found ignore any subsequent rules.

A more complete solution fixing several other canonicalisation issues at
the same time:

    RewriteEngine On
    #
    RewriteCond %{THE_REQUEST} ^[A-Z]{3,9}\ /([^/]+/)*index\.html?\ HTTP/
    RewriteRule ^(([^/]+/)*)index\.html?$ http://www.example.com/$1 [R=301,L]
    #
    RewriteCond %{THE_REQUEST} !^POST
    RewriteCond %{THE_REQUEST} ^[A-Z]{3,9}\ /([^/]+/)*index\.php\ HTTP/
    RewriteCond %{SERVER_PORT}>s ^(443>(s)|[0-9]+>s)$
    RewriteRule ^(([^/]+/)*)index\.php$ http%2://www.example.com/$1 [R=301,L]
    #
    RewriteCond %{HTTP_HOST} !^(www\.example\.com)?$
    RewriteRule (.*) http://www.example.com/$1 [R=301,L]

If you would like to understand what all of this means you could read these
articles:

* Apache mod_rewrite Introduction
* Introduction to .htaccess Redirects