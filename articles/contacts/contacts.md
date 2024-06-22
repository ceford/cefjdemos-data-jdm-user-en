<!-- Filename: contacts.md / Display title: Contacts -->

## Introduction

A contact is a collection of personal information about an individual. You may
wish to make such information available on your website for either public or
private display. For example, you may wish to list key members of your
organisation or community. The Joomla! Contact component is designed for this
purpose. It allows you to list people and their personal information on your
web site, not necessarily registered users. You may also allow anyone, or
just registered users, to send e-mails to those people.

As an example of the use of personal data you could look at the WikiPedia page
on the Parliamentary committees of the United Kingdom. There you will see lists of
committees with popup information in individual chair persons. If you follow a
link to any committee you will see a list of members with selected information
about each individual. To do something like this in Joomla you would set up
categories and subcategries for each committee. Like this:

```
House of Commons
- Business
- Culture
- ...
House of Lords
- Communications
- Constitution
- ...
```
Each committee member has extra information not present in the default
data - political affiliation, such as Conservative, Labour or SNP, and
constituency, the area of the country they represent. Those items can
be collected using Custom Fields.

Care is needed in the collection and display of personal information.
Individuals may be very sensitive to having any information made available
online.

## Contact Data

Contacts are created via the Contacts list page. Select the `New` button in the
Toolbar to add a new entry. There is also a **User - Contact Creator** plugin
that automatically creates a contact when a new user is registered.

In the **Contacts: Edit* form, enter whatever data you have available on the
contact.

![data entry screenshot](../../../en/images/contacts/contact-data-entry.png "Data entry Screenshot")

**Notes:**

In the Screenshot the **Position** was entered as *Chair* which made sense in
the context of a category list of committee members but it does not make sense
in the context of a list of Featured contacts that consists of all the Chairs of
all of the Committees. This needs to be more specific: *Chair of the Culture
Media and Sport Committee*.

The **First...**, **Second..** and **Third Sort Field** fields need words added
for each entry to enable sorting by a user defined order such as a conventional
surname firstname order. This is covered later in this article.

The **Miscellaneous Information** tab contains a text edit field with a short
personal statement.

The **Extra** tab contains the *Party* and *Constituency* custom fields.

The **Form** tab contains settings for the email contact form. If an email
address is not entered this field is not displayed.

## Contact Display

The Contact component provides four menu items to display contact data:

* Single Contact
* Featured Contacts
* List Contacts in a Category
* List All Contacts in a Category Tree

It is a good idea to try each menu type to see what the output looks like.
Some examples:

### List All Categories in a Contacts Category Tree

In this case category tree consists of a parent category and two sub-categories:
```
House of Commons
- Business Committee
- Culture Committee
```
![all categories in a category tree](../../../en/images/contacts/contact-all-committees.png "All Categories in a Contact Category Tree")

The second line of each entry come from the Category Description.

If you select one of the Committe links the Committe page may look like this:

![contacts in a category](../../../en/images/contacts/contact-culture-committee.png "Contacts in a Category")

The layout is not quite as desired. It would have been good to include a
thumbnail image of each individual and a better layout of the details. That
can be done with a template override (later).

### List Contacts in a Category

For the Business Committe there is a List Contacts in a Category menu item.
That causes a different layou to be used:

![contact category list](../../../en/images/contacts/contact-category-list.png "Contact Category List")

Better but still not quite right! A styling override was needed to reduce the
image style. Again it seems a template override could be useful.

### Featured Contacts

For this example the Chairs of all of the committees were marked as featured.

![featured contacts](../../../en/images/contacts/contact-featured.png "Featured Contacts")

## Sort Order

The order in which contacts appear can be set in the Contact component options
or in a menu item. The latter overrides the former if it is set. The settings
available are as follows:
* **Name** The name of the contact. This may not be suitable for alphabet
    ordering.
* **Sort Name** This is the three *Sort Field* fields in the Contact data form
    mentioned previously.
* **Ordering** This is the order in which contacts appear in the Contacts list.
* **Featured Contacts Ordering** Featured contacts appear before other contacts
    but otherwise contacts are displayed in list order.

