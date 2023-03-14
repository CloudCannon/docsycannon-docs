---
_schema: default
title: Navigation
linkTitle: Navigation
weight: 3
description: |
  Customize site navigation for your DocsyCannon site.
categories:
  - Navigation
tags:
  - Nav
  - Navigation
---
## Top-level menu

The top level menu (the one that appears in the top navigation bar for the entire site) uses your site’s main menu. Any page made in CloudCannon through the Pages collection will appear in this menu.

The menu is ordered from left to right by page&nbsp;`weight`. So, for example, a section index or page with&nbsp;`weight: 30`&nbsp;would appear after the Documentation section in the menu, while one with&nbsp;`weight: 10`&nbsp;would appear before it.

### Adding a version drop-down

If you add some versions in the Versioning section of the Data collection, the DocsyCannon theme adds a version selector drop down to the top-level menu.

You can find out more in the guide to&nbsp;[versioning your docs](https://www.docsy.dev/docs/adding-content/versioning/).

### Adding a language drop-down

If you configure more than one language in&nbsp;`hugo.toml`, the DocsyCannon theme adds a language selector drop down to the top-level menu. Selecting a language takes the user to the translated version of the current page, or the home page for the given language.

You can find out more in&nbsp;[Multi-language support](https://www.docsy.dev/docs/language/).

## Sidebar Menu

The sidebar menu, as shown in the left side of the&nbsp;`documentation`&nbsp;section, is automatically built from the contents of the section.

Like the top-level menu, the sidebar menu is ordered by weight.

### Sidebar menu options

By default, the sidebar menu shows the current docs section fully expanded all the way down. This may make the left nav too long and difficult to scan for bigger sites. Try setting site parameter&nbsp;`sidebar_menu_foldable = true`&nbsp;in the Navbar section of the site Data collection.

The upper limit for how many pages are displayed in the sidebar menu is controlled by `sidebar_menu_truncate.`&nbsp;By default this is set to 50, so no more than 50 pages will show in the sidebar menu.

On large sites (default: &gt; 2000 pages) the sidebar menu is not generated for each page, but cached for the whole section. The HTML classes for marking the active menu item (and menu path) are then set using JS. You can adjust the limit for activating the cached section menu with the optional parameter&nbsp;`sidebar_cache_limit `in the Navbar section of the site Data collection.

## Breadcrumb navigation

Breadcrumb navigation links appear at the top of each page by default. To disable breadcrumb navigation, set&nbsp;`breadcrumb_disable`&nbsp;as true in the User Interface section of the sites Data collection.

Breadcrumb navigation links are also shown for each item on the taxonomy results page (i.e. when you click one of the taxonomy labels, e.g. Tags/Categories). These breadcrumbs can be disabled by setting&nbsp;`taxonomy_breadcrumb_disable`&nbsp;to true in the User Interface section of the sites Data collection.