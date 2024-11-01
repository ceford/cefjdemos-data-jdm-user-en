<!-- Filename: J4.x:Module_Positions / Display title: Module Positions -->

## Introduction

Template module positions are defined in a templateDetails.xml file and
used in a template index.php file. Several modules may be assigned to a
single position so there is rarely any need to create more positions. If
you do want more positions you will need create your own template and
that is not covered here.

## Preview Module Positions

There is a template option that allows you to see module locations in
Site and Administrator templates, including positions which have no
assigned modules. To enable this feature:

- Select **System **→** Site Templates** from the Administrator menu.
- Select the `Options` button from the Toolbar.
- In the Template: Options form set **Preview Module Positions** to
  **Enabled**.
- Save and Close

To view module positions you need to append either ?tp=1 or &tp=1 to the
url.

- If the url does not contain a question mark then append ?tp=1.
- If the url already contains a question mark then append &tp=1.

### Atum Administrator Template Positions

![templates atum template positions](../../../en/images/modules/template-positions-templates-page.png)

### Cassiopeia Site Template Positions


![templates cassiopeia template positions](../../../en/images/modules/template-positions-site-page.png)

You may also find this module position diagram helpful:

![cassiopeia template position diagram](../../../en/images/modules/cassiopeia-template-positions.png)

## Production Sites

Remember to change the **Preview Module Positions** to **Disabled** on
productions sites.
