---
_schema: index
title: Update DocsyCannon
linkTitle: Update DocsyCannon
weight: 10
description: |
  Keeping the DocsyCannon theme up to date.
categories:
  - Updates
tags:
  - Updates
  - Upstream
  - Hugo Modules
---
DocsyCannon is forked from the Docsy, and tweaked to be used in CloudCannon's CMS. We hope to continue to make improvements to the DocsyCannon along with the community improvements to Docsy. If you have cloned the template (or are otherwise using the theme as a Hugo Module or Git submodule), you can easily update the DocsyCannon theme in your site yourself. If you have cloned the theme itself into your own project you can also update, though you may need to resolve merge conflicts.

Updating DocsyCannon means that your site will build using the latest version of Docsy at&nbsp;`HEAD`&nbsp;and include all the new commits or changes that have been merged since the point in time that you initially added the Docsy submodule, or last updated. Updating won’t affect any modifications that you made in your own project to override the Docsy look and feel, as your overrides don’t modify the theme itself. For details about what has changed in the theme since your last update, see the list of&nbsp;[Docsy commits](https://github.com/google/docsy/commits/main).

If you have been using the theme as a Git submodule, you can also update your site to use&nbsp;[Docsy as a Hugo Module](https://www.docsy.dev/docs/get-started/docsy-as-module/). This is the latest and simplest way to pull in a Hugo theme from its repository. If you’re not ready to migrate to Hugo Modules yet, don’t worry, your site will still work and you can continue to update your submodule as before.

## Manually get updates to DocsyCannon

If you want to manually pull through changes from DocsyCannon to your own repository, you can set DocsyCannon's repository as an upstream remote, pull the upstream changes, and then merge the upstream/main into your own main branch. There may be merge conflicts that will need to be resolved.

1\. Check your remotes. They should show your repository as the `origin` remote.

```console
git remote -v
```

2\. Add DocsyCannon as an `upstream` remote.

```console
git remote add upstream https://github.com/tomrcc/docsycannon-template
```

3\. Check your remotes again. You should see origin and upstream remotes now.

4\. Fetch changes to the upstream remote. This will add them to a branch called `upstream/main`.&nbsp;

```
git fetch upstream
```

5\. Navigate to the branch on your repository you want to merge the changes to and merge the `upstream/main` branch in.

```
git merge upstream/main
```

We recommend using <a target="_blank" rel="noopener" href="https://www.sublimemerge.com/">Sublime Merge</a>&nbsp;or something similar to help with any merge conflicts.