---
layout: post
title:  "Jekyll configuration and customisation"
date:   2018-11-17
categories: colophon

---

Adapting Jekyll to make it work for this site.

<!--more-->


## Content structure

I tried a few ways to build a hierarchy of content within Jekyll, since this site doesn't really follow a (reverse-chronological) blog format. Specifically, writing all content as pages instead of posts, and using the Jekyll's concept of "[collections](https://jekyllrb.com/docs/collections/)". Neither of these worked, so I've ended up with the following approach.

1. Write all content as posts. i.e. use the standard `date-name.md` file naming format, and store them in the `/_posts/` directory.

2. Give all posts [categories](https://jekyllrb.com/docs/posts/#categories-and-tags), by including this in the frontmatter at the top of each post, like so:

	```
	---
	layout: post
	title:  "Jekyll configuration and customisation"
	date:   2018-11-17
	categories: colophon
	---
	```
	
	Or:
	```
	categories: [colophon, course]
	```

	<span class="wip">WIP:</span> Note that categories must be URL-friendly (lowercase, one-word, or hyphenated), as they are used in post slugs. This causes problems later on when you want to list category names in templates.

3. Override the default permalink settings to use categories as part of the URL slug, instead of dates (this makes the whole site a lot less _bloggy_.)

	Add this line to `_config.yml`: 
	```
	permalink: /:categories/:title:output_ext
	```

	This removes dates from the default format, which is:
	```
	permalink: /:categories/:year/:month/:day/:title:output_ext
	```


4. Create index pages for categories by adding a `category.html` page to `/_layouts/`. 

	```ruby
	{% raw %}---
	layout: page
	---
	<h3>{{ category[0] }}</h3>

	{% for page in site.categories[page.category]  %}
		<h3><a href="{{ page.url | relative_url }}">
		  {{ page.title }}
		</a></h3>
		 <p>{{ page.excerpt }} </p>
	{% endfor %}
	</ul>
	{% endraw %}```

5. [Override the default homepage template](https://jekyllrb.com/docs/themes/#overriding-theme-defaults) by creating a similar `home.html` template in `/_layouts/` to list all posts by category. 

	```ruby{% raw %}
	---
	layout: page
	---
	{% for category in site.categories %}
	  <h3>{{ category[0] }}</h3>
	  <ul>
		{% for post in category[1] %}
		  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
		{% endfor %}
	  </ul>
	{% endfor %}
	{% endraw %}```
	
	<span class="wip">WIP:</span> This is where the category naming breaks down. I need to find a way to associate a properly formated category name with each machine-readable category lug to display on this page.



6. Add a simple template for each category inside the `/category/` folder. These all have the same format:
	```
	---
	layout: category
	title: Course notes
	category: course
	---
	```
	
	This step is derived from [a similar approach detailed here](https://kylewbanks.com/blog/creating-category-pages-in-jekyll-without-plugins).

This way, all posts appear listed by category on the homepage, and in the site nav, all categories are listed, linked through to their respective index pages



## Overrides

URL-based overrides are [detailed elsewhere]({{ site.baseurl }}{% post_url 2018-11-24-publishing-to-multiple-servers %})

I've already talked about permalink settings.

So far, my only other customisation is to explicitly state an excerpt separator, so that I can control how posts are displayed on index pages.

```
excerpt_separator: <!--more-->
```

If a post has nothing above this separator, nothing is displayed as an except. However, all posts must have the separator, otherwise an indeterminate amount of text is considered by Jekyll to be the excerpt.

### Permalinks


## CSS

I should try SASS!





## A few notes on Markdown (and Jekyll)

Markdown is great, but it has a few quirks worth noting. These can be made more irksome when wrapping your Markdown in Jekyll's 'liquid' syntax.

### Line breaks
In these notes, I’m writing a lot of sentence fragments, so I need to use a lot of line breaks – as opposed to paragraphs. [These have a special syntax](https://daringfireball.net/projects/markdown/syntax#p):

> The implication of the “one or more consecutive lines of text” rule is that Markdown supports “hard-wrapped” text paragraphs. This differs significantly from most other text-to-HTML formatters which translate every line break character in a paragraph into a `<br />` tag.
> When you _do_ want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.


### Spaces in category names
If you want categories that have more than one word, you need to encapsulate them with [square brackets], like this:

```
categories: [DIY Arduino]
```
