<!-- Filename: Robots.txt_file / Display title: The robots.txt file -->

## About Robots

Web robots, also known as crawlers, web wanderers or spiders, are
programs that traverse the web automatically. Among many uses, search
engines use them to index the web content.

The robots.txt file implements the 
[Robots Exclusion Protocol](https://en.wikipedia.org/wiki/Robots_exclusion_standard),
which allows a website administrator to define which parts of the site should 
not be inspected by specific robot user agents. For example, access to the 
content of public pages is normally allowed but access to cgi, private and 
temporary directories that should not have pages indexed is often disallowed.

## Where to Place the *robots.txt* File

A standard *robots.txt* file is included in your Joomla root. The
*robots.txt* file must reside in the root of the domain or subdomain and
must be named `robots.txt`.

### Joomla in a Subdirectory

A robots.txt file located in a subdirectory is not valid. Robots only
check for this file in the root of the domain. If the Joomla site is
installed within a subdirectory such as *example.com/joomla/*, the
*robots.txt* file **must** be moved to the site root at
*example.com/robots.txt*.

**Note:** In the robots.txt file, the subdirectory name **must** prefix any
disallowed Joomla paths. For example, the disallow rule for the `/administrator/`
directory **must** be changed to read `Disallow: /joomla/administrator/`.

## Joomla *robots.txt* Contents

This is the contents of a [standard Joomla robots.txt file](https://raw.githubusercontent.com/joomla/joomla-cms/refs/heads/5.2-dev/robots.txt.dist):

```
# If the Joomla site is installed within a folder
# eg www.example.com/joomla/ then the robots.txt file
# MUST be moved to the site root
# eg www.example.com/robots.txt
# AND the joomla folder name MUST be prefixed to all of the
# paths.
# eg the Disallow rule for the /administrator/ folder MUST
# be changed to read
# Disallow: /joomla/administrator/
#
# For more information about the robots.txt standard, see:
# https://www.robotstxt.org/orig.html

User-agent: *
Disallow: /administrator/
Disallow: /api/
Disallow: /bin/
Disallow: /cache/
Disallow: /cli/
Disallow: /components/
Disallow: /includes/
Disallow: /installation/
Disallow: /language/
Disallow: /layouts/
Disallow: /libraries/
Disallow: /logs/
Disallow: /modules/
Disallow: /plugins/
Disallow: /tmp/
```

## Robot Exclusion

You can exclude directories or block robots from your site by adding a
Disallow rule to the *robots.txt* file. For example, to prevent any
robots from visiting the */tmp* directory, add this rule:

    Disallow: /tmp/

See also:

- [Block access to your content](https://support.google.com/webmasters/topic/4598466?hl=en&amp;ref_topic=9427949)
  at Google's Help Center.

## Syntax Checking

For syntax checking you can use a validator for *robots.txt* files. Try
one of these:

- [Test your <em>robots.txt</em> with the robots.txt Tester](https://support.google.com/webmasters/answer/6062598) at Google.
- [<em>robots.txt</em> Checker](http://www.searchenginepromotionhelp.com/m/robots-text-tester/robots-checker.php) by Search Engine Promotion Help.

### General Information

- [The Web Robots Pages](http://www.robotstxt.org/) is the main Website for *robots.txt*.
- [A Standard for Robot Exclusion](http://www.robotstxt.org/orig.html) is the original standard.
- [Robots meta tag, data-nosnippet, and X-Robots-Tag specifications](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag)
