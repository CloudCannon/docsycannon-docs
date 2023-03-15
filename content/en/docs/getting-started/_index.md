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
## Use as template

The simplest way to get started is to use DocsyCannon as a template, which gives you a site project that is set up and ready to fill in with your own content. To do this:

1\. Click **Use this template** on <a target="_blank" rel="noopener" href="https://github.com/tomrcc/docsycannon-template">GitHub</a>

2\. Select a name for your new project and click **Create repository from template**.

3\. [Sign up](https://app.cloudcannon.com/register?trial=cc_standard)&nbsp;for CloudCannon using their free trial period.

4\. <a target="_blank" rel="noopener" href="https://cloudcannon.com/community/learn/hugo-cms---get-started-with-cloudcannon">Build your site</a>&nbsp;on CloudCannon.

Once you have a copy of the template live on CloudCannon, navigate to <a target="_blank" rel="noopener" href="https://app.cloudcannon.com/editor">CloudCannon's CMS</a>&nbsp;and edit the contents to suit your needs.

## Existing Docsy users

If you have a site already using Docsy as a theme, and want to migrate over to DocsyCannon to make use of the live editing features in CloudCannon, you will need to use the template and then bring your content over.

Create a new site using the template and replace the provided skeleton `content` folder with your own `content` folder. This should work automatically, however for non-content pages (ie. not docs or blog pages) such as the homepage or an 'about' page, some work may need to be done to convert the content to Bookshop syntax. Consider this classic Docsy homepage content file:

```html
{% raw %}---
title: "Goldydocs"
linkTitle: "Goldydocs"
---

{{&lt; blocks/cover title="Welcome to Goldydocs: A Docsy Example Project!" image_anchor="top" height="full" color="orange" &gt;}}
<div class="mx-auto">
  <a class="btn btn-lg btn-primary mr-3 mb-4" href="{{&lt; relref "/docs" &gt;}}">
    Learn More <i class="fas fa-arrow-alt-circle-right ml-2"></i>
  </a>
  <a class="btn btn-lg btn-secondary mr-3 mb-4" href="https://github.com/google/docsy-example">
    Download <i class="fab fa-github ml-2 "></i>
  </a>
  <p class="lead mt-5">Porridge temperature assessment - in the cloud!</p>
  {{&lt; blocks/link-down color="info" &gt;}}
</div>
{{&lt; /blocks/cover &gt;}}

{{% blocks/lead color="primary" %}}
Goldydocs provides a single web UI providing visibility into porridge temperature, chair size, and bed softness metrics! You can even find out who's been eating **your** porridge.

(Sadly, Goldydocs isn't a real project, but you can use this site as an example to create your own real websites with [Docsy](https://docsy.dev))
{{% /blocks/lead %}}

{{&lt; blocks/section color="dark" &gt;}}
{{% blocks/feature icon="fa-lightbulb" title="New chair metrics!" %}}
The Goldydocs UI now shows chair size metrics by default.

Please follow this space for updates!
{{% /blocks/feature %}}

{{% blocks/feature icon="fab fa-github" title="Contributions welcome!" url="https://github.com/google/docsy-example" %}}
We do a [Pull Request](https://github.com/google/docsy-example/pulls) contributions workflow on **GitHub**. New users are always welcome!
{{% /blocks/feature %}}

{{% blocks/feature icon="fab fa-twitter" title="Follow us on Twitter!" url="https://twitter.com/docsydocs" %}}
For announcement of latest features etc.
{{% /blocks/feature %}}

{{&lt; /blocks/section &gt;}}{% endraw %}
```

Docsy uses a similar concept to Bookshop, in that individual components of the page are broken down into 'blocks'. If you want this content to be editable on CloudCannon, you must add these as Bookshop components in the page's front matter instead, like the example below.

Don't worry if the front matter below looks complicated, CloudCannon will add all of this for you through the CMS, using pre-made components. You will have to manually add the content of those components through the UI. The Bookshop components available to you in CloudCannon use the same names as Docsy's 'blocks', which makes it more obvious how to recreate your page using Bookshop. Once your content is 'Bookshopped' it will be fully editable in the CMS.

```yaml
---
_schema: home
title: DocsyCannon
description: The template for DocsyCannon
content_blocks:
  - _bookshop_name: section/cover
    title: DocsyCannon
    logo_image: ''
    subtitle:
    text: >-
      The Hugo theme Docsy, configured for use in CloudCannon. This theme is
      great for creating documentation websites, without having to touch any
      code!
    col_id: dark
    background_image: /images/placeholder-bg.jpg
    height: auto
    byline:
    link_down:
      _bookshop_name: generic/link_down
      color: dark
      id: home_lead
    button:
      - _bookshop_name: generic/button
        icon: fas fa-arrow-alt-circle-right
        size: lg
        type: primary
        url: /docs
        text: Learn More
      - _bookshop_name: generic/button
        icon: fab fa-github
        size: lg
        type: secondary
        url: https://github.com/tomrcc/docsy-hugo-cloudcannon-template
        text: Download
  - _bookshop_name: section/lead
    color: dark
    height: auto
    text: >-
      This template website is forked from the <a target="_blank" rel="noopener"
      href="(https://github.com/google/docsy-example),">Docsy Example
      Website</a>, and then configured for editing in CloudCannon's CMS. Fork
      your own copy and edit the placeholder information to suit your needs. If
      you also have experience with Hugo you can edit the code and customize
      your site even further, and using CloudCannon's config file and Bookshop
      components you can tailor your page building experience to your needs.
    heading:
    id: home_lead
  - _bookshop_name: section/section
    heading:
    text: ''
    color: info
    height: auto
    type: true
    feature:
      - _bookshop_name: simple/feature
        icon: fab fa-github
        title: GitHub
        text: ''
        link:
          url: https://github.com/
          url_text: Read More
      - _bookshop_name: simple/feature
        icon: fas fa-book
        title: DocsyCannon
        text: ''
        link:
          url: /
          url_text: Documentation
      - _bookshop_name: simple/feature
        icon: fas fa-h
        title: Hugo
        text: ''
        link:
          url: https://github.com/gohugoio/hugo
          url_text: Documentation
---
```