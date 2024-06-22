<!-- Filename: How_do_you_block_direct_hot_linking_to_image_files_using_htaccess%3F / Display title: Image hotlink prevention -->

## Definition

Hotlinking is the practice of linking an image on one website from an article
on another website. It can be a very useful practice. This website uses many
images that are actually located on the docs.joomla.org website. It saves on
the time and effort required to create screenshots and on the bandwidth of
this site. However, there can be copyright issues and you may wish to prevent
your images being used in this way.

The method described here uses an *.htaccess* file, which is an Apache server
feature. Other web servers may provide other methods to prevent hotlinking.

## Directions

Place the following code in the *.htaccess* file of your root directory.
```
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %{HTTP_REFERER} !^$
    RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?yourdomain.com [NC]
    RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?google.com [NC]
    RewriteRule \.(jpg|jpeg|png|gif|webp|svg)$ - [NC,F,L]
</IfModule>
```

### Explanation

* The first RewriteCond allows direct requests using a URL- no referer.
* The second RewriteCond allows requests from your own domain. The *\[NC\]*
    flag means *No Case*, that is, match both upper and lower case characters.
* The third RewriteCond allows allows requests from Google, so your images
    can still appear in search results. You can add similar lines for any
    other sites you wish to allow.
* The RewriteRule blocks requests for image files from all domains not
    previously allowed. The F flag tells the browser to return a Forbidden
    header (403). L stands for Last rule.

### Block Hot Linking from Specific Domains

To stop hotlinking from specific domains only, such as *myspace.com*,
*blogspot.com* and *livejournal.com*, while allowing other websites to
hotlink to your images, use the following code:

```
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?myspace\.com/ [NC,OR]
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?blogspot\.com/ [NC,OR]
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?livejournal\.com/ [NC]
    RewriteRule \.(jpg|jpeg|png|gif|webp|svg)$ - [NC,F,L]
</IfModule>
```
You can add as many different domains as you want. Every *RewriteCond*
line except the last one should end with the *\[NC,OR\]* flags. *NC*
means to ignore case. *OR* means "Or Next", as in, match this line
**or** the next line. The last *RewriteCond* omits the *OR* flag to stop
matching after the last *RewriteCond*.

