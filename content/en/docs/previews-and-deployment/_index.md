---
_schema: index
title: Previews and Deployment
linkTitle: Previews and Deployment
weight: 10
description: Deploying your DocsyCannon site.
categories:
  - Deployment
  - Development
tags:
  - Deployment
  - Development
  - Localhost
  - CloudCannon
  - Hosting
  - CMS
---
## Serving your site locally

Depending on your deployment choice you may want to serve your site locally during development to preview content changes. To serve your site locally:

1. Ensure you have an up to date local copy of your site files cloned from your repo.
2. Ensure you have the tools described in&nbsp;[Prerequisites and installation](https://www.docsy.dev/docs/get-started/docsy-as-module/installation-prerequisites)&nbsp;installed on your local machine, including&nbsp;`postcss-cli`&nbsp;(you’ll need it to generate the site resources the first time you run the server).
3. Run the&nbsp;`hugo server`&nbsp;command in your site root. By default your site will be available at&nbsp;[http://localhost:1313](http://localhost:1313/).

Now that you’re serving your site locally, Hugo will watch for changes to the content and automatically refresh your site. If you have more than one local git branch, when you switch between git branches the local website reflects the files in the current branch.

## Build environments and indexing

By default, Hugo sites built with&nbsp;`hugo`&nbsp;(rather than served locally with&nbsp;`hugo server`) have the Hugo build environment&nbsp;`production`. Deployed Docsy sites with&nbsp;`production`&nbsp;builds can be indexed by search engines, including Google Custom Search Engines. Production builds also have optimized JavaScript and CSS for live deployment (for example, minified JS rather than the more legible original source).

If you do not want your deployed site to be indexed by search engines (for example if you are still developing your live site), or if you want to build a development version of your site for offline analysis, you can set your Hugo build environment to something else such as&nbsp;`development`&nbsp;(the default for local deploys with&nbsp;`hugo server`),&nbsp;`test`, or another environment name of your choice.

The simplest way to set this is by using the&nbsp;`-e`&nbsp;flag when specifying or running your&nbsp;`hugo`&nbsp;command, as in the following example:

```
hugo -e development
```

## Deployment with CloudCannon

DocsyCannon is a forked version of Docsy, with configuration meant for use in CloudCannon's CMS.&nbsp;

{{< iframe src="https://cloudcannon.com/documentation/guides/hugo-starter-guide/" width="100%" tryautoheight=false style="min-height:98vh; border:none;" sandbox=false name="CloudCannon Setup" sub="Your browser cannot display embedded frames. You can access the embedded page via the following link:" >}}