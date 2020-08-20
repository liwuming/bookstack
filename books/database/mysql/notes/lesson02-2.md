# Markdown Extensions

## Header Anchors

Headers automatically get anchor links applied. Rendering of anchors can be configured using the [`markdown.anchor`](../config/README.md#markdown-anchor) option.

## Links

### Internal Links

Internal links are converted to `<router-link>` for SPA navigation. Also, every `README.md` or `index.md` contained in each sub-directory will automatically be converted to `index.html`, with corresponding URL `/`.

For example, given the following directory structure:

```
.
├─ README.md
├─ foo
│  ├─ README.md
│  ├─ one.md
│  └─ two.md
└─ bar
   ├─ README.md
   ├─ three.md
   └─ four.md
```

And providing you are in `foo/one.md`:

```md
[Home](/) <!-- Sends the user to the root README.md -->
[foo](/foo/) <!-- Sends the user to index.html of directory foo -->
[foo heading](./#heading) <!-- Anchors user to a heading in the foo README file -->
[bar - three](../bar/three.md) <!-- You can append .md (recommended) -->
[bar - four](../bar/four.html) <!-- Or you can append .html -->
```

### Redirection for URLs

VuePress supports redirecting to clean links. If a link `/foo` is not found, VuePress will look for a existing `/foo/` or `/foo.html`. Conversely, when one of `/foo/` or `/foo.html` is not found, VuePress will try the other. With this feature, we can customize your website’s URLs with the official plugin [vuepress-plugin-clean-urls](https://vuepress.github.io/plugins/clean-urls/).

::: tip
Regardless of whether the permalink and clean-urls plugins are used, your relative path should be defined by the current file structure. In the above example, even though you set the path of `/foo/one.md` to `/foo/one/`, you should still access `/foo/two.md` via `./two.md`.
:::

### External Links

Outbound links automatically get `target="_blank" rel="noopener noreferrer"`:

- [vuejs.org](https://vuejs.org)
- [VuePress on GitHub](https://github.com/vuejs/vuepress)

You can customize the attributes added to external links by setting [config.markdown.externalLinks](../config/README.md#markdown-externallinks).

## Frontmatter

[YAML frontmatter](https://jekyllrb.com/docs/frontmatter/) is supported out of the box:

``` yaml
---
title: Blogging Like a Hacker
lang: en-US
---
```

This data will be available to the rest of the page, along with all custom and theming components.

For more details, see [Frontmatter](./frontmatter.md).

## GitHub-Style Tables

**Input**

```
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

**Output**

| Tables        |      Are      |  Cool |
| ------------- | :-----------: | ----: |
| col 3 is      | right-aligned | $1600 |
| col 2 is      |   centered    |   $12 |
| zebra stripes |   are neat    |    $1 |

## Emoji :tada:

**Input**

```
:tada: :100:
```

**Output**

:tada: :100:

A [list of all emojis](https://github.com/markdown-it/markdown-it-emoji/blob/master/lib/data/full.json) is available.

## Table of Contents

**Input**

```
[[toc]]
```

**Output**

<!--lint disable no-shortcut-reference-link no-undefined-references-->

[[toc]]

<!--lint enable no-shortcut-reference-link no-undefined-references-->

Rendering of the TOC can be configured using the [`markdown.toc`](../config/README.md#markdown-toc) option.

## Custom Containers <Badge text="default theme"/>

Custom containers can be defined by their types, titles, and contents.

### Default Title
**Input**

```md
::: tip
This is a tip
:::

::: warning
This is a warning
:::

::: danger
This is a dangerous warning
:::

::: details
This is a details block, which does not work in IE / Edge
:::
```

**Output**

::: tip
This is a tip
:::

::: warning
This is a warning
:::

::: danger
This is a dangerous warning
:::

::: details
This is a details block, which does not work in That is / Edge
:::

### Custom Title
**Input**

````md
::: danger STOP
Danger zone, do not proceed
:::

::: details Click me to view the code
​```js
console.log('Hello, VuePress!')
```
:::
````

**Output**

::: danger STOP
Danger zone, do not proceed
:::

::: details Click me to view the code
​```js
console.log('Hello, VuePress!')
```
:::
