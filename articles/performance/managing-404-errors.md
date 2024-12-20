<!-- Filename: Managing_404_Errors / Display title: Managing 404 Errors -->

## Why 404 Not Found Matters

The most common problem with websites which are struggling in search
engine rankings is the number of 'not found' errors – commonly referred
to as *404* errors because that is the status code returned if the page
cannot be found.

First, there are legitimate reasons to have 404 errors – if you have a
page for an event which has passed, or a service which you no longer
provide. In these cases, eventually the page will be removed from the
index of search engines and won't be associated with your site any more.

The problem occurs if you have a lot of 404 errors – for example if you
unpublish a category which contained hundreds of articles. From the
search engine's perspective, this is not a great experience for their
visitors, because they land on your site and the information that the
search engine told them was there, isn't. This is why it is not a great
idea to have too many 404 errors on your site.

## Google Search Central

The first step is to find out how many you have – which can be done
using Google's [Search Central](https://developers.google.com/search).
This is a free set of tools which allows you to analyse your website and
pick up on problems, errors and issues quickly. It is recommended that
you have every site you manage registered at Search Central to ensure
you are notified in the event of any problems.

When you visit Search Central there is a section which shows you URL
Errors in the search listing – this will show you a list of the 404
errors that Google has found on your site, and a graph which shows you
how this has changed over time. If the graph starts to go up, look into
why there are pages that were on your site and now can't be found.

If there was a temporary problem on your site, you can mark errors as
being fixed.

![webmaster tools](../../../en/images/performance/404-discovery.png)

## Fixing Problems

Discovery is only one part of the process. Once you have discovered the
problematic URLs, do something about it (if it needs fixing!) by either
redirecting the page to another on the site, re-instating the original
page, or looking into what has caused the 404 error.

If you need to redirect a page you can use the System - Redirect plugin to
collect missing pages and the System / Redirects component to redirect missing
pages to existing pages.

## Monitoring Problems

If you want to monitor your 404 traffic, the best way to do this in
Analytics is to look at what happens when you have a 404 error. In most
cases, the page title changes to 404 – so we can create a custom segment
which will filter traffic with a title of 404 and tell you what the
landing page is. This should allow you to monitor and proactively manage
your 404 errors and ensure that your site visitors do not end up landing
on dead links.

![Analytics alerts 404 traffic](../../../en/images/performance/404-analytics-alerts.png)

![Analytics alerts audience overview](../../../en/images/performance/404-analytics-alerts-2.png)

Google also has the ability, in Analytics, to set up alerts. Alerts
allow you to be emailed when certain events occur. In this case, we can
set up an alert to be notified if there is more than a 5% increase in
the number of 404 errors in a weekly period – which might mean we have a
problem with the website which needs investigating.

This is a great way to keep on top of things even if you haven't logged
in to look at your dashboard!

![Analytics alerts email](../../../en/images/performance/404-analytics-alerts-email.png)

## Monitoring Errors with a Dashboard

There is also a dashboard you can install called the *Data Integrity
Dashboard* which shows you information about 404 errors, along with some
other metrics which might be of interest. Just search the Google
Analytics Gallery for *Data Integrity Dashboard* and select which
profile to install it under.

![Data integrity](../../../en/images/performance/404-data-integrity.png)
