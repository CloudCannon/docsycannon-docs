---
_schema: default
title: Search
linkTitle: Search
weight: 4
description: Customise search for your DocsyCannon site.
categories:
  - Search
tags:
  - Search
  - Algolia
  - GCSE
  - Google Search
---
DocsyCannon offers multiple options that let your readers search your site content, so you can pick one that suits your needs. You can choose from:

* [Google Custom Search Engine](https://programmablesearchengine.google.com/about/)&nbsp;(GCSE), the default option, which uses Google’s index of your public site to generate a search results page. This is an easy to set up option, all you need to do is add a GCSE ID and then set it up on the GCSE dashboard.
* <a target="_blank" rel="noopener" href="https://docsearch.algolia.com/">Algolia DocSearch</a>, which uses Algolia’s indexing and search mechanism, and provides an organized dropdown of search results when your readers use the search box. Algolia DocSearch is free for public documentation sites. This is slightly more complex to add to your site and requires adding to the source code. Enter scripts for Algolia in&nbsp;`layouts/partials/hooks/body-end.html`&nbsp;and style sheets in&nbsp;`layouts/partials/hooks/head-end.html`.

## Disabling the sidebar search box&nbsp;

By default, the search box appears in both the top navigation bar and at the top of the sidebar left navigation pane. If you don’t want the sidebar search box, turn off Algolia DocSearch and remove any GCSE ID in Sidebar Settings section of the sites Data collection.

## Configure search with a Google Custom Search Engine

To enable this feature, you’ll first need to make sure that you have built and deployed a production version of your site, as otherwise your site won’t be crawled and indexed.

### Setting up GCSE search

1. Create a Google Custom Search Engine for your deployed site by clicking&nbsp;**New search engine**&nbsp;on the&nbsp;[Custom Search page](https://cse.google.com/cse/all)&nbsp;and following the instructions. Make a note of the ID for your new search engine.
2. Add any further configuration you want to your search engine using the&nbsp;**Edit search engine**&nbsp;options. In particular you may want to do the following:
   * Select&nbsp;**Look and feel**. Change from the default&nbsp;**Overlay**&nbsp;layout to&nbsp;**Results only**, as this option means your search results are embedded in your search page rather than appearing in a separate box. Click&nbsp;**Save**&nbsp;to save your changes.
   * Edit the default result link behavior so that search results from your site don’t open in a new tab. To do this, select&nbsp;**Search Features**&nbsp;-&nbsp;**Advanced**&nbsp;-&nbsp;**Websearch Settings**. In the&nbsp;**Link Target**&nbsp;field, type “\_parent”. Click&nbsp;**Save**&nbsp;to save your changes.

{{< alert color="info" title="Tip" >}}Your site search results should show up within a couple of days. If it takes longer than that, you can manually request that your site is indexed by submitting a sitemap through the Google Search Console.{{< /alert >}}

## Configure Algolia DocSearch

As an alternative to GCSE, you can use&nbsp;[Algolia DocSearch](https://docsearch.algolia.com/)&nbsp;with this theme. Algolia DocSearch is free for public documentation sites. DocsyCannon supports Algolia DocSearch v3.

### Sign up for Algolia DocSearch

Complete the form at&nbsp;[https://docsearch.algolia.com/apply/](https://docsearch.algolia.com/apply/).

If you are accepted to the program, you will receive the code to add to your documentation site from Algolia by email.

### Adding Algolia DocSearch

1. Enable Algolia DocSearch in the Search section of the sites Data collection.&nbsp; &nbsp;&nbsp;
2. Disable the sidebar search in&nbsp;`hugo.toml`/`hugo.yaml`/`hugo.json`&nbsp;as this is not currently supported for Algolia DocSearch. See&nbsp;[Disabling the sidebar search box](https://www.docsy.dev/docs/adding-content/navigation/#disabling-the-sidebar-search-box).
3. Add the CSS and JS to use Algolia to the head and body of every page in your site.
   * In&nbsp;`head-end.html`&nbsp;add the DocSearch CSS:

     <div><p><code class="language-html"><strong>&lt;</strong><strong>link</strong>&nbsp;rel<strong>=</strong>"stylesheet" href<strong>=</strong>"https://cdn.jsdelivr.net/npm/@docsearch/css@3"&nbsp;<strong>/&gt;</strong></code></p></div>
   * In&nbsp;`body-end.html`&nbsp;add the DocSearch script, replacing the&nbsp;`docsearch`&nbsp;details with the snippet you get from Algolia (the example below is Algolia’s own site index!). You must provide&nbsp;`#docsearch`&nbsp;as your&nbsp;`container`&nbsp;value as that’s the ID of the&nbsp;`div`&nbsp;we provide in Docsy’s layout:

     <div><p><code class="language-html"><strong>&lt;</strong><strong>script</strong>&nbsp;src<strong>=</strong>"https://cdn.jsdelivr.net/npm/@docsearch/js@3"<strong>&gt;&lt;/</strong><strong>script</strong><strong>&gt;</strong><strong>&lt;</strong><strong>script</strong>&nbsp;type<strong>=</strong>"text/javascript"<strong>&gt;</strong>docsearch<strong>({</strong>&nbsp; container<strong>:</strong>&nbsp;'#docsearch'<strong>,</strong>&nbsp; appId<strong>:</strong>&nbsp;'R2IYF7ETH7'<strong>,</strong>&nbsp; apiKey<strong>:</strong>&nbsp;'599cec31baffa4868cae4e79f180729b'<strong>,</strong>&nbsp; indexName<strong>:</strong>&nbsp;'docsearch'<strong>,</strong>&nbsp;&nbsp;<strong>});&lt;/</strong><strong>script</strong><strong>&gt;</strong></code></p></div>

You can find out more about how to configure DocSearch in the Algolia DocSearch V3&nbsp;[Getting started](https://docsearch.algolia.com/docs/DocSearch-v3)&nbsp;guide.

When you’ve completed these steps, Algolia search should be enabled on your site. Search results are displayed as a pop-up, so you don’t need any search results page.