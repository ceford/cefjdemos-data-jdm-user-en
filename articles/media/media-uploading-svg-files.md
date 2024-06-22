<!-- Filename: J4.x:Media:_Uploading_SVG_files / Display title: Uploading SVG files -->

## Introduction

SVG (Scalable Vector Graphics) files are not supported in Joomla by
default. A few steps are necessary to allow the Media component to support
them.

## Media Options

From the Administrator menu:

* Select **Media** from the *Home Dashboard* or from the *Content* menu.
* Select the **Options** button from the Media *Toolbar*.

There are 3 fields to be updated, all are comma separated lists so you just
need to append a comma and the appropriate value:

- In *Allowed Extensions*, add at the end of the already available
  list: `,svg`.
- In *Legal Image Extensions*, add at the end of the already available
  list: `,svg`.
- In *Legal MIME Types*, add at the end of the already available list:
  `,image/svg+xml`.
- **Save & Close**

From now on, you should be able to upload SVG files into the Media
Manager. Unless...

## Why is Joomla still preventing me from uploading SVG files?

SVG is not a raster image format (like PNG files, which contain pixels),
it is written in XML (Extensible Markup Language). It is text-based,
usable directly inside the DOM (Document Object Model), CSS can change
properties and JavaScript can add interactivity.

As such, SVG files are susceptible to all XML related attack patterns:

- Cross-site scripting – or XSS (through its `<script>` tag and events).
- HTML injections (through the `<foreignObject>` element – foreignObject allows
you to include elements from a different XML namespace).
- Denial of service (if the `<xlink:href>` element is misused).

Starting with Joomla 4.1, a sanitizer tool is used to check the content of any
SVG file uploaded through the Media Manager. The rules are strict and ensure
files cannot harm the site. Therefore, some files may need to be **cleaned**
manually (remember, SVG files are text files and can be edited in a text
editor) or through an outside tool before they can be uploaded successfully.

**Tip:** these sites will clean svg files created in *Inkscape*:

* SVG Sanitizer Test
* SVG Cleaner & Optimizer
* SVGminify.com
