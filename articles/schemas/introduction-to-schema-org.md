<!-- Filename: J5.x:Schema_org / Display title: Introduction to Schemas -->

## Rich Snippets

Rich snippets (also known as *rich results*) are normal Google search results with additional data displayed. This extra data is usually compiled from structured data found in a page's HTML. Common rich snippet types include reviews, recipes, and events. Rich snippets can help websites stand out in search results, attract more clicks, and provide users with a better understanding of the content before they click through.

Joomla implements Rich Snippets using JSON-LD. This is a JavaScript notation embedded in a `<script>` tag in the `<head>` element of an HTML page. The markup is not interleaved with the user-visible text. The content of the snippets are entered in form fields implemented with plugins.

## Schema.org

>Schema.org is a collaborative, community activity with a mission to create, maintain, and promote schemas for structured data on the Internet, on web pages, in email messages, and beyond.

Structured data is a standardised format for organising and representing information on the web. It provides a way to describe the content and meaning of data in a structured manner, making it easier for search engines and other applications to understand and process the information. There is more detailed information on the [Schema.org website](https://schema.org/).

## Joomla Implementation

In Joomla, Rich Snippets are generated using structured data markup based on the Schema.org schemas. Each schema type is implemented as a separate plugin. This allows for a more modular and extensible architecture. Each plugin is responsible for generating the schema markup for a specific type of content, which allows for more flexibility and customisation options. This makes it easier for third-party developers to contribute to the development of Joomla's structured data capabilities.

To get started, go to **System -> Plugins** and enable the *System - Schema.org* plugin. If this plugin is not enabled there will be no Schema tab in an article edit form even if all of the individual plugins are enabled.

![List of schema plugins](../../../en/images/schemas/schema-plugins-list.png)

### Edit System - Schema.org Plugin

- **Base Type** Choose whether your website represents an organization or a single person.
- **Name** Enter the name of the organization or person the website represents.
- **Image** Add your company or personal image
- **Social Media Accounts** Add your company or personal social media accounts. Select the Green button plus sign to add rows to the form.
- Select **Save & Close**.

![edit system schema org plugin](../../../en/images/schemas/edit-system-schema-org-plugin.png)

### Edit an Article

Go to any of your articles and fill in the Schema form fields. If the *Schema Type* is set to *None*, the default, there are no fields to complete. Select any Schema to see a list of fields appropriate for that schema. The following screenshot shows an article with the Article schema selected:

![edit article scheme form](../../../en/images/schemas/schema-form-in-an-article.png)

### Output

You will not see anything related to the schema in the web page. However, if you look at the page source you will see a script entry, as in the following example:

```json
	<script type="application/ld+json">{
    "@context": "https://schema.org",
    "@graph": [
        {
            "@type": "Organization",
            "@id": "http://localhost/jcms-testing/#/schema/Organization/base",
            "name": "Joomla Documentation Team",
            "url": "http://localhost/jcms-testing/"
        },
        {
            "@type": "WebSite",
            "@id": "http://localhost/jcms-testing/#/schema/WebSite/base",
            "url": "http://localhost/jcms-testing/",
            "name": "JCMS Testing",
            "publisher": {
                "@id": "http://localhost/jcms-testing/#/schema/Organization/base"
            }
        },
        {
            "@type": "WebPage",
            "@id": "http://localhost/jcms-testing/#/schema/WebPage/base",
            "url": "http://localhost/jcms-testing/index.php/en/article-en-gb",
            "name": "Article (en-gb)",
            "isPartOf": {
                "@id": "http://localhost/jcms-testing/#/schema/WebSite/base"
            },
            "about": {
                "@id": "http://localhost/jcms-testing/#/schema/Organization/base"
            },
            "inLanguage": "en-GB",
            "breadcrumb": {
                "@id": "http://localhost/jcms-testing/#/schema/BreadcrumbList/139"
            }
        },
        {
            "@type": "Article",
            "headline": "Article Schema Test",
            "description": "Latin text used to simulate layouts.",
            "author": {
                "@type": "person",
                "name": "Superman"
            },
            "@id": "http://localhost/jcms-testing/#/schema/com_content/article/1",
            "isPartOf": {
                "@id": "http://localhost/jcms-testing/#/schema/WebPage/base"
            }
        }
    ]
}</script>
```
You can test your structured data via the Google [Test your structured data page](https://developers.google.com/search/docs/appearance/structured-data).

## Available plugins

| Plugin | Description |
|--------|-------------|
| Article Plugin | The starting point for using schema.org |
| Blogposting Plugin | For Blog Post content |
| Book Plugin | For Book content |
| Custom Plugin | For direct entry of JSON-LD code |
| Event Plugin | For Event content |
| JobPosting Plugin | For Job Posting content |
| Organization Plugin | For Company and Organization content |
| Person Plugin | For Person content |
| Recipe Plugin | For Recipe content |
