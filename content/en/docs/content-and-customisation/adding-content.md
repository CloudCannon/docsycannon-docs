---
_schema: default
title: Adding Content
linkTitle: Adding Content
weight: 1
description: Add different types of content to your DocsyCannon site
categories:
  - Content
  - Customisation
tags:
  - Content
  - Customisation
  - Editing
---
## Content sections

* Documentation is for pages in your site’s Documentation section.
* Blog is for pages in your site’s Blog.

These two sections are meant for the main content of your site. They come with pre-made navigation to their various subpages.&nbsp;<br><br>Other pages on the site are more flexible and are built using components available in CloudCannon [Bookshop](https://github.com/CloudCannon/bookshop/blob/main/guides/hugo.adoc). The template comes with pre-made components for you to edit and create pages, but also the ability to create new components and tailor your page building experience even further.

## Creating new pages
{{% pageinfo color="primary" %}}You cannot create more than one blog section or documentation section.{{% /pageinfo %}}

### Normal pages

Create new normal (as opposed to documentation or blog pages) by navigating to the pages collection with CloudCannon's sidebar, and then add pages using the Add button in the top right corner of the page. These pages will appear in the main navigation in the header.

### Documentation pages

Create new documentation pages by navigating to the Docs collection using the sidebar in CloudCannon and then adding either a docs section or a docs page using the Add button in the top right corner of the page.<br><br>A docs section is meant for any new documentation page that doesn't already belong to a 'docs section'. A docs section can have subpages which are created using the&nbsp; 'docs page' add option. A docs page will be greyed out and indented in the sidebar underneath its docs section.&nbsp;<br><br>Each docs page has an index of all of the sections and pages that are direct children nested inside it.

### Blog pages

Create new blog pages by navigating to the Blog collection using the sidebar in CloudCannon and then adding either a blog index or a blog page using the Add button in the top right corner of the page.

A 'blog index' is meant to be a list of related blog pages. A 'blog page' is used for a new blog post, and is listed on the main Blog page. If a blog page is nested in a 'blog index' it will also be listed on that 'blog index' page.<br><br>Blog post lists are ordered so that the most recent posts are at the top of the list.