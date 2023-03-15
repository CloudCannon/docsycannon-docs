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
If you want to manually pull through changes from DocsyCannon to your own repository, you can set [DocsyCannon's repository](https://github.com/CloudCannon/docsycannon-template) as an upstream remote, pull the upstream changes, and then merge the upstream/main into your own main branch. There will be merge conflicts that will need to be resolved.

1\. Check your remotes. They should show your repository as the `origin` remote.

```console
git remote -v
```

2\. Add DocsyCannon as an `upstream` remote.

```console
git remote add upstream https://github.com/CloudCannon/docsycannon-template
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