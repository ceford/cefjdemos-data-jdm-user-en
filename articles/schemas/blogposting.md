<!-- Filename: J5.x:Schema_org/Type_Organization_-_Using_Organization_Plugin / Display title: Schema.org - BlogPosting -->

## Purpose

The BlogPosting schema type is for articles created for a blog to help search engines better understand the blog post and display relevant information. See the Schema Org [BlogPosting schema type](https://schema.org/BlogPosting) for more information. There is a separate [Blog schema type](https://schema.org/Blog) for blog websites but that is not yet implemented in Joomla.  

The schema provides search engines with information such as:

- Image: The featured image of the blog post
- Headline: The title of the blog post
- Description: A brief short description of the blog post
- Author
    - Type: Select between Organization or Person
    - Name: The name of the organization or person who authored the blog post
    - URL: The web address of the organization or the person who authored the blog post
    - Email: The email address for the organization or the person who authored the blog post
    - Address
        - Locality: The city, province, locality for the organization or person who authored the blog post
        - Postal Code: The postal code for the organization or person who authored the blog post
        - Street Address: The street address for the organization or person who authored the blog post
- Date Published: The date the blog post was published who authored the blog post
- Date Modified: The date the blog post was modified who authored the blog post
- Generic Field: Used to define custom properties that are not defined in the default form

Open an article edit form and select the Schema tab to select a Schema type and set the data for that type. If a Schema Type is not present in the list its Plugin may be disabled. The values to be entered in each field are mostly self-evident.

The *Generic Field* section allows *Title* and *Value* pairs to be entered in addition to the default fields.

## Example Screenshot

Below is an example of a BlogPosting schema in an Article edit form.

![A blogposting schema edit form](../../../en/images/schemas/edit-schema-blogposting.png)
