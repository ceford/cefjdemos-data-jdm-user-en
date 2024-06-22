<!-- Filename: jdocmanual?manual=user&heading=seo&filename=seo-basics.md / Display title: SEO Basics -->

## Definition

Search Engine Optimisation is the process of improving a wide range of features
of a website with the intention of improving the position in which it ranks in
search engines.

The process of optimising a website is multi-faceted as there are many factors
which affect where a page might rank in a search engine.

- Ensuring that content has appropriate structure using Semantic HTML
- Improving the quality of the content of individual pages.
- Ensuring that the website can handle requests quickly
- Enabling Search Engine Friendly URLs to make the web address of pages
  'human readable'
- Adding contextual Semantic Markup using Schema data

Resource: Search Engine Optimization (SEO) Starter Guide

## Site Structure and Descriptive URLs

In the early days, websites were structed as individual HTML files in a tree
hierarchy. Some websites are still structured like that. CMSs are different.
Individual pages are assembed from content stored in database tables. The URLs
for the former and latter are different, perhaps like this:
```
https://www.example.com/user/seo/seo-basics.html
https://www.example.com/index.php?option=com_jdocmanual&view=manual&manual=user&heading=seo&filename=seo-basics
```
Clearly the first is easier to remember and easier to type. Search engines
prefer them.

In the Joomla CMS a url of the first form can be set up as follows:

1. Create a Content Category named **User**.
2. Create a Content Category named **SEO** that is a child of *User*.
3. Create an article and assign it to the *SEO* category.
4. Create a **User** menu item of type of **Category List* using the *User* category.
5. Create a menu item **SEO** of type **Category List** using the *SEO* category.
6. Set up the Joomla SEO functionality in *Global Configuration*.

Test it with your SEO URL: navigate via the User and SEO lists to the SEO Basics
page. The Breadcrumbs should show: `You are here: Home / User / SEO / SEO Basics`.
But not if you have created a Single Article menu item type for *SEO Basics*!

## Reduce Duplication

The snag with CMSs is that the same content can be made available with different
URLs. In the example above both URLs will work (but not on this site), as will
`https://example.com/index.php?option=com_content&view=category&id=18&ItemID=17`.
Only one of these should be recognised by search engines and set as the
**canonical** URL. But which one and how?

The **System - SEF** plugin provides some help. It has three settings:

* **Site Domain:** If your site can be accessed through more than one domain
enter the preferred (sometimes referred to as canonical) domain here. **Note:**
`https://example.com` and `https://www.example.com` are different domains.
* **Strict handling of index.php:** This option enables a stricter handling of
'index.php' in URLs when 'Use URL Rewriting' is enabled in Global Configuration.
It will remove 'index.php' if a URL still contains it and redirect incoming
requests with 'index.php' to the version without the 'index.php'.
* **Trailing slash for URLs:** Force Joomla to only use URLs with or without
trailing slash. When set, this will force the right URL with redirects and is
only applied when 'Add suffix to URL' is disabled.

**Canonical Tags** explanation from Daniel Morell:

* How to Create Joomla Canonical Tags
* Plugin and Documentation:

For Joomla 4 and 5, before enabling, the plugin needs `if ($app->isAdmin()) {`
changed to `if ($app->isClient('admin')) {` on lines 72 and 99 of
*plugins /system / customcanonical / customcanonical.php*.

In an article, select the Publishing tab and then the *Canaonical URL* **Auto**
button. This will place a link like the following any page that displays the
single article:
```
	<link href="/jdm3/en/user/seo/seo-basics.html" rel="canonical" />
```
## Content Quality

Make what you write interesting and easy to read. Long paragraphs are often
overwhelming and difficult to read. One-line paragraphs look wrong! Maybe they
should really be bullet points. Aim for paragraphs of three lines or so. Read
what you write and edit out any unnecesary words.

Keep your content up to date and avoid copying information from other sites.
If possible, verify your content.

### Semantic HTML

Content should consist of a hierarchy of headings and paragraphs with other
elements as required (lists, tables and so on). Do not confuse structure with
appearance - so do not use a heading for emboldment or emboldment for a heading.
This is an example of semantic markup of an article:

```html
  <h2>Using headings</h2>
  <p>This is an article about the importance of headings.</p>

  <h2>Why use headings?</h2>
  <p>It is important to use headings so that search engine bots can tell what
  is an <strong>important</strong> part of your article.</p>

  <h3>Types of headings</h3>
  <p>You can use set types of headings, but they should be ordered, and
  structured, within your page.  H1 will be the page title inserted by Joomla,
  with H2 being used for sub-headings of the page.  Any headings within your
  sub-headings should cascade using H3, H4, and H5 as appropriate.</p>

  <h2>Is it hard to implement headings?</h2>
  <p>It is really easy to implement headings, you just use the appropriate
  HTML code.</p>
```
Notice that an article *Title* will become a `<h1>` heading if necessary so do
not use it in an article body.

## Anticipate Search Terms

Choose explicit titles for your pages and headings within pages. For example,
if you don't know what *Semantic HTML* is or want more information on that
topic those would be the words you enter into a search engine. Think of the
people who might be interested in the information you are providing. What will
they search for? But keep Titles and Headings fairly short - some sources say
no more than 60 characters.

## Care with Advertisemants

Nothing will deter site visitors more than advertisments appearing here, there
and everywhere and moving the real information around before your eyes. Adverts
that change every few seconds are also annoying and a drain on end-user
resources. Many will use Ad-blockers!

## Care with Links

Links are both a blessing and a curse! They can affect your site SEO rating for
good or bad depending on whether you have links to reputable or disreputable
sources. And they have to be maintained. You may have links to internal or
external articles that have disappeared, present outdated information or are no
longer relevant. Best advice: link if the target adds real benefit for your
site visitors and use the `nofollow` link attribute if you do not want the
target site associated with your site.

There are plenty of link checker toos available, some free or freemium and
others paid, often as part of a site monitoring service.

## Page Title and Description

In the `<head>` of every page there should be a `<title>` tag and a
`<description>` tag. Joomla makes it very easy to set a different title for
every page. Unfortunately, it also makes it very easy to neglect to set
a suitable Title and Description on every page.

As an example, take the **SEO** category list page mentioned above. The page
source `<title>` says **SEO** and the `<description>` is missing. In the
**Menus: Edit Item** form for this menu item there is a **Page Display** tab
with a **Browser Page Title** field. Insert `SEO - List of Articles` there and
that is what appears in the `<title>` tag and in the browser tab.

In the **Metadata** tab, with the **Meta Description** field set to
`List of articles on Search Engine Optimisation.` that is exactly what appears
in the `<description>` field. The Description is sometimes used to accompany
a page Title in search results so it should pay to make it relevant.

More information:
* Magazine article: Joomla SEO title tags
* Explore the Core: Native SEO Options

## Optimise Images

Needless to say, attractive images can enhance a site enormously. But too many
that are too large attract SEO penalties. Here are some tips:

* Place images next to the text they illustrate.
* Use descriptive **alt** text.
* Use minus sign separated words for the mage names for example
cat-on-hot-tin-roof.jpd.
* Use the right type of image for the job: png for posters, jpg for photographs.
* Use responsive images - the is a Joomla plugin that dynamically creates webp
versions of png and jpg images in several sizes.
