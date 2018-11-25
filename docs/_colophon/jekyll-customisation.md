---
layout: page
title:  "Jekyll configuration and customisation"
date:   2018-11-17
---

Adapting Jekyll to make it work for this site.

<!--more-->


## Collections

[See this page]({{ site.baseurl }}{% link _colophon/implementing-jekyll-collections.md %}) on how I implemented the site hierarchy using collections


## Overrides

[See here for detail on URL overrides]({{ site.baseurl }}{% link _colophon/publishing-to-multiple-servers.md %}) in `_config.yml`.


So far, my only other customisation is to explicitly state an excerpt separator, so that I can control how posts are displayed on index pages.

```
excerpt_separator: <!--more-->
```

If a post has nothing above this separator, nothing is displayed as an except. However, all posts must have the separator, otherwise an indeterminate amount of text is considered by Jekyll to be the excerpt.

## CSS

I should try SASS, which is what Jekyll uses, but at the moment, I'm just overriding the default CSS for theme I'm using (minima) with CSS declarations in `_includes/head.html`

## A few notes on Markdown (and Jekyll)

Markdown is great, but it has a few quirks worth noting. These can be made more irksome when wrapping your Markdown in Jekyll's 'liquid' syntax.

### Line breaks
In these notes, I’m writing a lot of sentence fragments, so I need to use a lot of line breaks – as opposed to paragraphs. [These have a special syntax](https://daringfireball.net/projects/markdown/syntax#p):

> The implication of the “one or more consecutive lines of text” rule is that Markdown supports “hard-wrapped” text paragraphs. This differs significantly from most other text-to-HTML formatters which translate every line break character in a paragraph into a `<br />` tag.
> When you _do_ want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.

