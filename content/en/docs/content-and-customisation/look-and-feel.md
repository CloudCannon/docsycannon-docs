---
_schema: default
title: Look and Feel
linkTitle: Look and Feel
weight: 2
description: Customise colors, fonts and more for your site.
categories:
  - Customisation
  -
tags:
  - Customisation
  - Editing
---
## Colors

Colors for the site can be easily changed in the colors section of the Data collection.<br><br>More color options can be added if you have developer experience by updating `_variables.scss` and&nbsp;`fetch-color.js` in the source code, following the format already there for the existing color options, and rebuilding in CloudCannon, or running&nbsp;`npm start `locally.

## Navbar

For pages beginning with a Cover bookshop component, like most homepages, the navbar is translucent as long as the hero image hasn’t scrolled up past the navbar. This initial translucent setting ensures that the hero image is maximally visible.

After the hero image has scrolled past the navbar, the navbar’s (opaque) background color is set – to the site’s primary color.

The text of navbar entries can be difficult to read with some hero images. In these cases, you can disable navbar translucency by setting the&nbsp;`translucent_over_cover_disable`&nbsp;option to&nbsp;`true`&nbsp;in your site’s Data collection.

By default the navbar does not display your logo in the top left. To enable a logo navigate to the Navbar section of your sites Data file, turn on `Navbar Logo` and ensure the correct path to your logo image is entered.