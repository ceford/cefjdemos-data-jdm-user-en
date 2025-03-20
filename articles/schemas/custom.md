<!-- Filename: Localhost / Display title: Schema.org - Custom -->

## Purpose

The Custom schema plugin is used to enter custom information in raw JSON-LD format. It is not a Schema Org type.

Open an article edit form and select the Schema tab to select a Schema type and set the data for that type. If a Schema Type is not present in the list its Plugin may be disabled. The values to be entered in each field are mostly self-evident.

This is an example of a hand-crafted rich snippet:

```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "Your Article Title",
  "description": "A brief description of the article.",
  "timeRequired": "PT5M"
}
```

The *timeRequired* property represents the estimated reading time in ISO 8601 duration format. In this case, PT5M means *5 minutes*.

## Example Screenshot

Below is an example of a Custom schema field in an Article edit form.

![A custom schema edit form](../../../en/images/schemas/edit-schema-custom.png)
