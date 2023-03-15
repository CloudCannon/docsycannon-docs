---
_schema: index
title: Getting Started
linkTitle: Getting Started
weight: 2
description: What does your user need to know to try your project?
categories:
  - Getting Started
tags:
  - Install
  - Start
  - Getting Started
  - Template
  - Build
---
Learn how to get started with DocsyCannon, including the available options for installing and using the DocsyCannon theme. DocsyCannon is a&nbsp;[Hugo](https://gohugo.io/)&nbsp;theme, which means that if you want to use DocsyCannon, you need to set up your website source so that the Hugo static site generator can find and use the DocsyCannon theme files when building your site. The simplest way to do this is to copy and edit our example site, though we also provide instructions for adding the DocsyCannon theme manually to new or existing sites.

If you want to build and test your site locally you also need to be able to run Hugo itself, either by installing it and any other required dependencies, or by using our provided Docker container.

This page describes DocsyCannons installation options and helps you choose the appropriate setup guide to get started.

## Installation options

Hugo offers multiple options for using themes, all of which are supported by DocsyCannon.

### Use as template

The simplest way to get started is to use our [example site](https://github.com/CloudCannon/docsycannon-example) as a template, which gives you a site project that is set up and ready to use. To do this:

1\. Click **Use this template** on <a target="_blank" rel="noopener" href="https://github.com/tomrcc/docsycannon-template">GitHub</a>

2\. Select a name for your new project and click **Create repository from template**.

3\. [Sign up](https://app.cloudcannon.com/register?trial=cc_standard)&nbsp;for CloudCannon using their free trial period.

4\. <a target="_blank" rel="noopener" href="https://cloudcannon.com/community/learn/hugo-cms---get-started-with-cloudcannon">Build your site</a>.

Once you have a copy of the template live on CloudCannon, navigate to <a target="_blank" rel="noopener" href="https://app.cloudcannon.com/editor">CloudCannon's CMS</a>&nbsp;and edit the contents to suit your needs.

### **Adding the theme as a Hugo Module**

<a target="_blank" rel="noopener" href="https://gohugo.io/hugo-modules/">Hugo Modules</a>&nbsp;are the another easy way to use Hugo themes. Hugo uses the modules mechanism to pull in the theme files from the main DocsyCannon repo at your chosen revision, which pulls through theme files from Docsy which makes it easy to keep the theme up to date in your site. Our&nbsp;<a target="_blank" rel="noopener" href="https://github.com/cloudcannon/docsycannon-example">example site</a>&nbsp;uses DocsyCannon as a Hugo Module.

### **Adding the theme as a Git submodule**

Adding the theme as a&nbsp;[Git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules)&nbsp;also lets Hugo use the theme files from their own repo, though is more complicated to maintain than the Hugo modules approach. This is the approach used in older versions of the Docsy example site and is still supported.