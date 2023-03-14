---
_schema: index
title: Print Support
linkTitle: Print Support
weight: 4
description: Making it easier to print entire sections of documentation.
categories:
  - Printing
tags:
  - Printing
---
Individual documentation pages print well from most browsers as the layouts have been styled to omit navigational chrome from the printed output.

On some sites, it can be useful to enable a “print entire section” feature (as seen in this user guide). Selecting this option renders the entire current top-level section (such as Content and Customization for this page) with all of its child pages and sections in a format suited to printing, complete with a table of contents for the section.

This feature is enabled by default. If you want to disable this feature, remove the “print” output format in your site’s&nbsp;

<font face="Inconsolata, monospace, sans-serif"><span style="font-size: 15.3px; white-space: pre-wrap; background-color: rgb(238, 238, 238);">config.toml</span></font>&nbsp;file for the “section” type:

<div><div><div><pre><code class="language-toml"><strong>[</strong>outputs<strong>]</strong>
section <strong>=</strong> <strong>[</strong> "HTML"<strong>,</strong> "RSS"<strong>,</strong> "print" <strong>]</strong></code></pre></div></div></div>

The site should show a “Print entire section” link in the right hand navigation when enabled.