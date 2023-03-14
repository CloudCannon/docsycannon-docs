---
_schema: index
title: Repository Links
linkTitle: Repository Links
weight: 7
description: Help your users interact with your source repository.
categories:
  - Repository Links
  - GitHub
tags:
  - Repository Links
  - Repository
  - GitHub
  - Issues
  - Contribute
---
The DocsyCannon docs and blog layouts include links for readers to edit the page or create issues for your docs or project via your site’s source repository. The current generated links for each docs or blog page are:

* **View page source**\: Brings the user to the page source in your docs repo.
* **Edit this page**\: Brings the user to an editable version of the page content in their fork (if available) of your docs repo. If the user doesn’t have a current fork of your docs repo, they are invited to create one before making their edit. The user can then create a pull request for your docs.
* **Create child page**\: Brings the user to a create new file form in their fork of your docs repo. The new file will be located as a child of the page they clicked the link on. The form will be pre-populated with a template the user can edit to create their page. You can change this by adding&nbsp;`assets/stubs/new-page-template.md`&nbsp;to your own project.
* **Create documentation issue**\: Brings the user to a new issue form in your docs repo with the name of the current page as the issue’s title.
* **Create project issue**&nbsp;(optional): Brings the user to a new issue form in your project repo. This can be useful if you have separate project and docs repos and your users want to file issues against the project feature being discussed rather than your docs.

This page shows you how to configure these links.

Currently, DocsyCannon supports only GitHub repository links “out of the box”. Since GitLab can handle the same link scheme, it should work as well. If you are using another repository such as Bitbucket and would like generated repository links, feel free to&nbsp;[add a feature request or update our theme](https://www.docsy.dev/docs/contribution-guidelines/).

## Link configuration

There are four variables you can configure in&nbsp;`hugo.toml`/`hugo.yaml`/`hugo.json`&nbsp;to set up links, as well as one in your page metadata.

## GitHub repository

The URL for your site’s source repository. This is used to generate the&nbsp;**Edit this page**,&nbsp;**Create child page**, and&nbsp;**Create documentation issue**&nbsp;links.​​​​​

## GitHub subdirectory

Specify a value here if your content directory is not in your repo’s root directory. For example, this site if your site is in the&nbsp;`userguide`&nbsp;subdirectory (folder) of its repo. Setting this value means that your edit links will go to the right page.

## GitHub project repository

Specify a value here if you have a separate project repo and you’d like your users to be able to create issues against your project from the relevant docs. The&nbsp;**Create project issue**&nbsp;link appears only if this is set.

## GitHub branch

Specify a value here if you have would like to reference a different branch for the other GitHub settings like&nbsp;**Edit this page**&nbsp;or&nbsp;**Create project issue**.

## Path base for GitHub subdirectory

Suppose that the source files for all of the pages under&nbsp;`content/some-section`&nbsp;come from another repo, such as a&nbsp;[git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules). Add settings like these to the&nbsp;**section’s index page**&nbsp;so that the repository links for all pages in that section refer to the originating repo:

```yaml
---<u>
</u>**title****:**<u> </u>Some super section<u>
</u>**cascade****:**<u>
</u><u>  </u>**github_repo****:**<u> </u>https://github.com/some-username/another-repo/<u>
</u><u>  </u>**github_subdir****:**<u> </u>docs<u>
</u><u>  </u>**path_base_for_github_subdir****:**<u> </u>content/some-section<u>
</u>…<u>
</u>---
```

As an example, consider a page at the path&nbsp;`content/some-section/subpath/some-page.md`&nbsp;with&nbsp;`github_branch`&nbsp;globally set to&nbsp;`main`. The index page settings above will generate the following edit link for&nbsp;`some-page.md`\:

```nocode
https://github.com/some-username/another-repo/edit/main/docs/subpath/some-page.md
```

If you only have a single page originating from another repo, then omit the&nbsp;`cascade`&nbsp;key and write, at the top-level, the same settings as illustrated above.

If you’d like users to create project issues in the originating repo as well, then also set&nbsp;`github_project_repo`, something like this:

```yaml
---<u>
</u>...<u>
</u>**cascade****:**<u>
</u><u>  </u>**github_repo****:**<u> </u>*&repo*<u> </u>https://github.com/some-username/another-repo/<u>
</u><u>  </u>**github_project_repo****:**<u> </u>**repo*<u>
</u>...<u>
</u>---
```

<div><div><div> </div></div></div>

<div><p>{{< alert color="info" title="Tip" >}}Please note that the YAML code fragment makes use of Yaml anchor. Use of Yaml anchors is optional, but it helps keep the settings DRY.{{< /alert >}}</p></div>

The&nbsp;`path_base_for_github_subdir`&nbsp;setting is a regular expression, so you can use it even if you have a site with&nbsp;[multiple languages](https://www.docsy.dev/docs/language/)&nbsp;for example:

```yaml
---<u>
</u>…<u>
</u>**path_base_for_github_subdir****:**<u> </u>content/\w+/some-section<u>
</u>…<u>
</u>---
```

<div><div><div>In situations where a page originates from a file under a different name, you can specify&nbsp;<code>from</code>&nbsp;and&nbsp;<code>to</code>&nbsp;path-rename settings. Here’s an example where an index file is named&nbsp;<code>README.md</code>&nbsp;in the originating repo:</div><div> </div></div></div>

<div><div><div><div><div><pre data-language="yaml"><code class="language-yaml">---<u>
</u>…<u>
</u><strong>github_repo</strong><strong>:</strong><u> </u>https://github.com/some-username/another-repo/<u>
</u><strong>github_subdir</strong><strong>:</strong><u> </u>docs<u>
</u><strong>path_base_for_github_subdir</strong><strong>:</strong><u>
</u><u>  </u><strong>from</strong><strong>:</strong><u> </u>content/some-section/(.*?)/_index.md<u>
</u><u>  </u><strong>to</strong><strong>:</strong><u> </u>$1/README.md<u>
</u>…<u>
</u>---</code></pre></div></div></div></div></div>