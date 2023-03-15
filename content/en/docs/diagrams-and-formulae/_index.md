---
_schema: index
title: Diagrams and Formulae
linkTitle: Diagrams and Formulae
description: How to use Latex and Katex in DocsyCAnnon
weight: 8
categories:
  - Diagrams
  - Formulae
tags:
  - Diagrams
  - Formulae
  - Scientific Notation
  - Chemistry
  - Mathematics
---
## Latex support with Katex

With Katex support enabled in Docsy, you can include complex mathematical formulae into your web page, either inline or centred on its own line. Since Katex relies on server side rendering, it produces the same output regardless of your browser or your environment. Formulae can be shown either inline or in display mode:

The probability of getting \\(k\\) heads when flipping \\(n\\) coins is:

```math
\tag*{(1)} P(E) = {n \choose k} p^k (1-p)^{n-k}
```

*Precipitation of barium sulfate:* \\(\\ce\{SO4^2- + Ba^2+ -&gt; BaSO4 v\}\\)

* Scientific number notation: \\(\\pu\{1.2e3 kJ\}\\) or \\(\\pu\{1.2E3 kJ\}\\) \\
* Divisions: \\(\\pu\{123 kJ/mol\}\\) or \\(\\pu\{123 kJ//mol\}\\)

$\\ce\{x Na(NH4)HPO4 -&gt;\[\\Delta\] (NaPO3)\_x + x NH3 ^ + x H2O\}$

Make sure to include large formulae in a codeblock, or it may create overflow issues on your page:

$\\ce\{Zn^2+ &lt;=&gt;\[+ 2OH-\]\[+ 2H+\] $\\underset\{\\text\{amphoteres Hydroxid\}\}\{\\ce\{Zn(OH)2 v\}\}$ &lt;=&gt;\[+ 2OH-\]\[+ 2H+\] $\\underset\{\\text\{Hydroxozikat\}\}\{\\ce\{\[Zn(OH)4\]^2-\}\}$\}$

$\\ce\{Hg^2+ -&gt;\[I-\] $\\underset\{\\mathrm\{red\}\}\{\\ce\{HgI2\}\}$ -&gt;\[I-\] $\\underset\{\\mathrm\{red\}\}\{\\ce\{\[Hg^\{II\}I4\]^2-\}\}$\}$

## Activating and configuring Katex support

Katex support will be disabled by default. To enable it uncomment the Katex Support section in the Hugo config.yaml file.

```yaml
#  KaTeX support
  katex:
    enable: true
    mhchem:
      enable: true
    html_dom_element: document.body
    options:
      throwOnError: false
      errorColor: '#CD5C5C'
      delimiters:
        - left: $$
          right: $$
          display: true
        - left: $
          right: $
          display: false
        - left: \(
          right: \)
          display: false
        - left: \[
          right: \]
          display: true
```

Mhchem is a plugin for Katex that enables support for chemical equations and formulae. This can be enabled or disabled as well.