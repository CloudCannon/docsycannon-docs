---
_schema: default
title: Versioning
linkTitle: Versioning
weight: 5
description: Customise navigation and banners for multiple versions of your docs.
categories:
  - Versioning
tags:
  - Versions
  - Versioning
---
Depending on your project’s releases and versioning, you may want to let your users access previous versions of your documentation. How you deploy the previous versions is up to you. This page describes the DocsyCannon features that you can use to provide navigation between the various versions of your docs and to display an information banner on the archived sites.

## Adding a version drop-down menu

If you add some&nbsp;`versions`&nbsp;in the Versioning section of the sites Data collection, the DocsyCannon theme adds a version selector drop down to the top-level menu. You specify a URL and a name for each version you would like to add to the menu, as in the following example:

```
  version = "master"
  url = "https://master.kubeflow.org"

  version = "v0.2"
  url = "https://v0-2.kubeflow.org"
```

Remember to add your current version so that users can navigate back!

The default title for the version drop-down menu is&nbsp;**Releases**. To change the title, change the&nbsp;`version_menu`&nbsp;field in Versioning section of the sites Data collection.

<div><div><div> </div></div></div>

If you set the&nbsp;`version_menu_pagelinks`&nbsp;field to&nbsp;`true`, then links in the version drop-down menu point to the current page in the other version, instead of the main page. This can be useful if the document doesn’t change much between the different versions. Note that if the current page doesn’t exist in the other version, the link will be broken.

## Displaying a banner on archived doc sites

If you create archived snapshots for older versions of your docs, you can add a note at the top of every page in the archived docs to let readers know that they’re seeing an unmaintained snapshot and give them a link to the latest version.

To add the banner to your doc site, make the following changes in your sites Versioning section of Data collection:

1. Set the&nbsp;`archived_version`&nbsp;field to true.

2. Make sure that&nbsp;`url_latest_version`&nbsp;contains the URL of the website that you want to point readers to. In most cases, this should be the URL of the latest version of your docs.