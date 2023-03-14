---
_schema: default
title: Logos and Images
linkTitle: Logos and Images
weight: 6
description: Add and customize logos, icons, and images in your project.
categories:
  - Logo
  - Images
tags:
  - Logo
  - Images
---
## Adding images

Either manually add images into the `static/images` folder through the file browser provided in CloudCannon, drag it into the folder via the source code, or upload a new file when prompted.<br><br>Bookshop components that have images will have a field to fill in that will prompt you to use an existing image or upload a new one.&nbsp;<br><br>Content pages such as documentation and blog pages have the option to add images via the image button in the text toolbar, or via the Figure snippet by clicking on the snippets button in the text toolbar. These will prompt you to either upload a new image or use an existing one, the same as above.

## Add your logo

DocsyCannon shows a site logo at the start of the navbar, that is, at the extreme left. Place your project’s SVG logo in&nbsp;`static/icons/logo.svg`. This overrides the default DocsyCannon logo in the theme.

If you don’t want a logo to appear in the navbar, then set&nbsp;`navbar_logo`&nbsp;to&nbsp;`false`&nbsp;in your project’s config.

The 'Cover' bookshop component will display a logo next to the main header if provided a path to the logo image.

## Use icons

Docsy includes the free FontAwesome icons by default, including logos for sites like GitHub and Stack Overflow. You can view all available icons in the&nbsp;[FontAwesome documentation](https://fontawesome.com/icons/), including the FontAwesome version when the icon was added and whether it is available for free tier users.