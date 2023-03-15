---
_schema: index
title: Multi-Language Support
linkTitle: Multi-Language Support
weight: 9
description: Support multiple languages in your site.
categories:
  - Languages
  - Translations
tags:
  - Languages
  - Translations
---
If you’d like to provide site content in multiple languages, the DocsyCannon theme and Hugo make it easy to both add your translated content and for your users to navigate between language versions. You will need to modify the Hugo config.yaml to enable multiple languages, and modify your collections configuration in cloudcannon.config.yaml to tell CloudCannon what to display in the sidebar and how to add new files. Some experience with .yaml is recommended.

## Content and configuration

To add content in multiple languages, you first need to define the available languages in a&nbsp;`languages`&nbsp;section in your site configuration. Each language can have its own language-specific configuration. For example, the Docsy Example Site Hugo config.yaml specifies that it provides content in English, Norwegian and Farsi, and that the language version visitors will see by default is English:

```yaml
# Language settings
contentDir: content/en
defaultContentLanguage: en
defaultContentLanguageInSubdir: false
# Useful when translating.
enableMissingTranslationPlaceholders: true
enableRobotsTXT: true

# Language configuration
languages:
  en:
    title: DocsyCannon
    description: A technical documentation site
    languageName: English
    weight: 1
  'no':
    title: Goldydocs
    description: Docsy er operativsystem for skyen
    languageName: Norsk
    contentDir: content/no
    time_format_default: 02.01.2006
    time_format_blog: 02.01.2006
  fa:
    title: اسناد گلدی
    description: یک نمونه برای پوسته داکسی
    languageName: فارسی
    contentDir: content/fa
    time_format_default: 2006.01.02
    time_format_blog: 2006.01.02
```

Any setting not defined in a&nbsp;`[languages]`&nbsp;block will fall back to the global value for that setting: so, for example, the content directory used for the site above will be&nbsp;`content/en`&nbsp;unless the user selects the Norwegian language option.

Once you’ve updated your site config, you create a content root directory for each language version in your source repo, such as&nbsp;`content/en`&nbsp;for English text, and add your&nbsp;[content](https://www.docsy.dev/docs/adding-content/content/)&nbsp;as usual. See the&nbsp;[Hugo Docs](https://gohugo.io/content-management/multilingual)&nbsp;on multi-language support for more information.

{{< alert color="danger" title="Attention (only when using docsy as a Hugo module)" >}}If you have a multi language installation, please make sure that the section [languages] inside your configuration file is declared before the section [module] with the module imports. Otherwise you will run into trouble!{{< /alert >}}

{{< alert color="info" title="Tip" >}}If there’s any possibility your site might be translated into other languages, consider creating your site with your content in a language-specific subdirectory, as it means you don’t need to move it if you add another language.{{< /alert >}}

For adding multiple language versions of other site elements such as button text, see the internationalization bundles (i18n) section below.

## Configuring CloudCannon to handle multiple languages

Once you have enabled languages in your Hugo config.yaml and added content in other languages, you need to tell CloudCannon how to reach your content and define how to add different types of pages/sections for each collection. Each section of each language will be a collection - so `en/docs` will be a collection and `no/docs` will be another collection. You should follow the format already defined in `cloudcannon.config.yaml`. Just copy and paste the equivalent english collection, change the `path` to where your content lives and change the `add_options`&nbsp;name to whatever is appropriate for your language. Here is an example from the&nbsp;[DocsyCannon Example](https://github.com/CloudCannon/docsycannon-example)&nbsp;`cloudcannon.config.yaml`&nbsp;file:

```yaml
pages:
    output: true
    path: content/en
    icon: home
    _enabled_editors:
      - visual
      - content
    text_key: title
    subtext_key: linkTitle
    description: Collection of pages.
    disable_add_folder: true
    add_options:
      - name: Page
        base_path: /
        schema: default
    schemas:
      default:
        path: schemas/page.md
        create:
          path: '{title|slugify}/_index.md'
  norsk_pages:
    output: true
    path: content/no
    icon: home
    _enabled_editors:
      - visual
      - content
    text_key: title
    subtext_key: linkTitle
    description: Collection of pages.
    disable_add_folder: true
    add_options:
      - name: Norsk Page
        base_path: /
        schema: default
    schemas:
      default:
        path: schemas/page.md
        create:
          path: '{title|slugify}/_index.md'
  farsi_pages:
    output: true
    path: content/fa
    icon: home
    _enabled_editors:
      - visual
      - content
    text_key: title
    subtext_key: linkTitle
    description: Collection of pages.
    disable_add_folder: true
    add_options:
      - name: Farsi Page
        base_path: /
        schema: default
    schemas:
      default:
        path: schemas/page.md
        create:
          path: '{title|slugify}/_index.md'
  blog:
    path: content/en/blog
    output: true
    icon: auto_stories
    text_key: title
    subtext_key: date
    description: Collection of blog posts.
    disable_add_folder: true
    schemas:
      default:
        path: schemas/blog/post.md
        name: Blog Post
      post_list:
        path: schemas/blog/post_list.md
        name: Post Index Page
        create:
          path: '[relative_base_path]/{title|slugify}/_index.md'
    _enabled_editors:
      - content
      - visual
  farsi_blog:
    path: content/fa/blog
    output: true
    icon: auto_stories
    text_key: title
    subtext_key: date
    description: Collection of blog posts.
    disable_add_folder: true
    schemas:
      default:
        path: schemas/blog/post.md
        name: "Blog Post (fa)"
      post_list:
        path: schemas/blog/post_list.md
        name: "Post Index Page (fa)"
        create:
          path: '[relative_base_path]/{title|slugify}/_index.md'
    _enabled_editors:
      - content
      - visual
```

Collection groups are how you define how collections are displayed in the CloudCannon sidebar. Here we have grouped the collections we have defined above into languages, however here we could also have decided to group all the different languages docs in a section together, or any groupings that suit your use case.&nbsp;

```
# Control which collections are displayed in the CloudCannon site navigation,
# and how those collections are grouped.
collection_groups:
  - heading: English
    collections:
      - pages
      - blog
      - docs
  - heading: Norsk
    collections:
      - norsk_pages
      - norsk_docs
  - heading: Farsi
    collections:
      - farsi_pages
      - farsi_docs
      - farsi_blog
  - heading: Site Data
    collections:
      - data
```

## Selecting a language

If you configure more than one language in your&nbsp;[configuration file](https://gohugo.io/getting-started/configuration/#configuration-file), the DocsyCannon theme adds a language selector drop down to the top-level menu. Selecting a language takes the user to the translated version of the current page, or the home page for the given language.

## Internationalization bundles

Coming soon. If you are interested in this feature, please let us know by [creating an issue](https://github.com/CloudCannon/docsycannon-template/issues/new) on DocsyCannon requesting it.