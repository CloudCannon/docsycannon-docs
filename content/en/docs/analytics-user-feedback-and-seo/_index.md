---
_schema: index
title: Analytics, User Feedback, and SEO
linkTitle: Analytics, User Feedback, and SEO
weight: 6
description: >-
  Add Google Analytics tracking to your site, collect user feedback and learn
  about the page description meta tag.
categories:
  - Analytics
  - Feedback
  - SEO
tags:
  - Analytics
  - Feedback
  - SEO
  - Google Analytics
---
## Adding Analytics

The DocsyCannon theme builds upon [Hugo’s support for Google Analytics](https://gohugo.io/templates/internal/#google-analytics), which Hugo provides through [internal templates](https://gohugo.io/templates/internal/). Once you set up analytics as described below, usage information for your site (such as page views) is sent to your [Google Analytics](https://analytics.google.com/analytics/web/) account.

### Prerequisites

You will need an **analytics ID** for your website before proceeding (technically it’s called a measurement ID or property ID but we’ll use the term “analytics ID” in this guide). If you don’t have one, see the **How to get started** section of [Introducing Google Analytics 4 (GA4)](https://support.google.com/analytics/answer/1042508).

{{< alert color="info" title="Tip" >}}Your project’s analytics ID is a string that starts with G- (a GA4 measurement ID) or UA- (a universal analytics property ID).{{< /alert >}}

### Setup

Enable Google Analytics by adding your project’s analytics ID to the site configuration file. For details, see [Configure Google Analytics](https://gohugo.io/templates/internal/#configure-google-analytics).

By default, Docsy uses the [gtag.js](https://support.google.com/analytics/answer/10220869) analytics library for both GA4 (which *requires* `gtag.js`) and Universal Analytics (UA) site tags. If you prefer using the older `analytics.js` library for your UA site tag, then set `params.disableGtagForUniversalAnalytics` to `true` in your project’s `config.toml`.

```toml
[params]
disableGtagForUniversalAnalytics = true
```

{{< alert color="warning" title="Warning" >}}You can configure your project’s analytics ID by setting either the top-level googleAnalytics config parameter or services.googleAnalytics.id. Do not define both, otherwise this can result in unexpected behavior. For details, see Is services.googleAnalytics.id an alias for googleAnalytics.{{< /alert >}}

{{< alert color="info" title="Production-only feature!" >}}Analytics are enabled only for production builds (called “environments” in Hugo terminology). For information about Hugo environments and how to set them, see the following [discussion](www.example.com).{{< /alert >}}

## User Feedback

By default Docsy puts a “was this page helpful?” feedback widget at the bottom of every documentation page,

### How is this data useful?

When you have a lot of documentation, and not enough time to update it all, you can use the “was this page helpful?” feedback data to help you decide which pages to prioritize. In general, start with the pages with a lot of pageviews and low ratings. “Low ratings” in this context means the pages where users are clicking **No** — the page wasn’t helpful — more often than **Yes** — the page was helpful. You can also study your highly-rated pages to develop hypotheses around why your users find them helpful.

In general, you can develop more certainty around what patterns your users find helpful or unhelpful if you introduce isolated changes in your documentation whenever possible. For example, suppose that you find a tutorial that no longer matches the product. You update the instructions, check back in a month, and the score has improved. You now have a correlation between up-to-date instructions and higher ratings. Or, suppose you study your highly-rated pages and discover that they all start with code samples. You find 10 other pages with their code samples at the bottom, move the samples to the top, and discover that each page’s score has improved. Since this was the only change you introduced on each page, it’s more reasonable to believe that your users find code samples at the top of pages helpful. The scientific method, applied to technical writing, in other words!

### Setup

1. Open the Feedback section of the Data collection in CloudCannon.
2. Ensure that Google Analytics is enabled, as described above.
3. Set the response text and link that users see after clicking **Yes** or **No**.

### Access the feedback data

This section assumes basic familiarity with Google Analytics. For example, you should know how to check page views over a certain time range and navigate between accounts if you have access to multiple documentation sites.

1. Open Google Analytics.
2. Open **Behavior** &gt; **Events** &gt; **Overview**.
3. In the **Event Category** table click the **Helpful** row. Click **view full report** if you don’t see the **Helpful** row.
4. Click **Event Label**. You now have a page-by-page breakdown of ratings.

Here’s what the 4 columns represent:

* **Total Events** is the total number of times that users clicked *either* **Yes** or **No**.
* **Unique Events** provides a rough indication of how frequently users are rating your pages per session. For example, suppose your **Total Events** is 5000, and **Unique Events** is 2500. This means that you have 2500 users who are rating 2 pages per session.
* **Event Value** isn’t that useful.
* **Avg. Value** is the aggregated rating for that page. The value is always between 0 and 1. When users click **No** a value of 0 is sent to Google Analytics. When users click **Yes** a value of 1 is sent. You can think of it as a percentage. If a page has an **Avg. Value** of 0.67, it means that 67% of users clicked **Yes** and 33% clicked **No**.

The underlying Google Analytics infrastructure that stores the “was this page helpful?” data is called [Events](https://developers.google.com/analytics/devguides/collection/analyticsjs/events). It’s just a `click` event listener that fires the Google Analytics JavaScript function for logging an Event, disables the **Yes** and **No** buttons, and shows the response text.

## Add a contact form with Fabform

You can create a contact form for your site and collect your form submissions at [fabform.io](https://fabform.io/). To use this feature, you first need to sign up for an account with Fabform. The following example shows how to add a simple form that collects the user’s email address to your site source:

<div><pre data-language="html"><code class="language-html"><strong>&lt;</strong><strong>form</strong> action<strong>=</strong>"https://fabform.io/f/{form-id}" method<strong>=</strong>"post"<strong>&gt;</strong>
 <strong>&lt;</strong><strong>label</strong> for<strong>=</strong>"email"<strong>&gt;</strong>Your Email<strong>&lt;/</strong><strong>label</strong><strong>&gt;</strong>
 <strong>&lt;</strong><strong>input</strong> name<strong>=</strong>"email" type<strong>=</strong>"email"<strong>&gt;</strong>
 <strong>&lt;</strong><strong>button</strong> type<strong>=</strong>"submit"<strong>&gt;</strong>Submit<strong>&lt;/</strong><strong>button</strong><strong>&gt;</strong>
<strong>&lt;/</strong><strong>form</strong><strong>&gt;</strong>
</code></pre></div>

For more details, see [Add a Hugo contact form](https://fabform.io/a/hugo-contact-form) in the Fabform documentation.

## Search Engine Optimization meta tags

To learn how to optimize your site for SEO see, [Search Engine Optimization (SEO) Starter Guide](https://developers.google.com/search/docs/beginner/seo-starter-guide).

Google [recommends](https://developers.google.com/search/docs/beginner/seo-starter-guide?hl=en%2F#descriptionmeta) using the `description` meta tag to tell search engines what your page is about. For each generated page, Docsy will set the content of the meta `description` by using the first of the following that is defined:

* The page's `description` field
* For non-index pages, the page [summary](https://gohugo.io/content-management/summaries/), as computed by Hugo
* The site description taken from the [site `params`](https://gohugo.io/variables/site/#the-siteparams-variable)

Add more meta tags as needed to your project’s copy of the `head-end.html` partial.