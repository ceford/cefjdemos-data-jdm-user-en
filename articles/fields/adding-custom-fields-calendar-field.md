<!-- Filename: J3.x:Adding_custom_fields/Calendar_Field / Display title: Calendar Field -->

## Purpose

The Calendar field provides a text box for entry of a date. An icon next to
the text box invokes a pop-up calendar picker, which can be used to select a
date from a graphical calendar.

## Field Creation

Common field parameters are described in a separate article.

* **Title** You may have several date fields in an article so care is needed
in setting the title to avoid ambiguity in the output.
* **Label** This is what is displayed in the output. If left empty it is set
from the content of the Title field but can be changed.
* **Show Time** If set to *Yes* the time is added to the date field, the
date picker and the output date. **Caution**: Even if you do not specify the
time in the default date, the time is displayed when the option *Show time*
is active.
* **Placeholder** May be set to a date format such as *YYYY-MM-DD* to remind
users of the format required and/or a reminder of what the date is for, such
as *Date of arrival*.

## Data Entry

In use the Calendar field is simple. You can type in the date in the required
format or select a date using the date picker. Care is needed in typing dates.
An error in the date is corrected on save to a new date. For example, a date
of 2024-14-02 is corrected to 2025-02-02.

The following screebshot shows an Acquisition date:

![acquisition date entry](../../../en/images/fields/fields-date-entry.png "Acquisition Date")

Fields only appear in an article if populated in the article data entry form.

## Data Display

The following Site screenshot shows the field displayed in an article. The
option *Automatic display* is responsible for the position of the field and
your template is responsible for the design of the field.

Look for the **Acquisition Date** item.

![Display of all fields](../../../en/images/fields/fields-display.png "Fields display")

The date formats are localized using language strings.
