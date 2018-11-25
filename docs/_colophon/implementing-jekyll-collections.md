---
layout: page
title:  "Implementing Jekyll Collections"
date:   2018-11-25

---

How did I set up the content structure for this site?

<!--more-->


The [Jekyll documentation on collections](https://jekyllrb.com/docs/collections/) is opaque, to say the least. There are plenty of tutorials out there, which I will not attempt to replicate. Instead, I'll document how I set it up for this site, and try to cover any gotchas.

## Setting up collections in _config.yml

I have my site hierarchy set up explicitly in the config file. 

```
collections: 

  course-notes:
    prettylabel: "Course Notes" 
    permalink: /:collection/:name
    output: true  

  colophon:
    prettylabel: "Colophon"
    permalink: /:collection/:name
    output: true
  
  diy-arduino:
    prettylabel: "DIY Arduino"
    permalink: /:collection/:name
    output: true
    
    [and so on ...]
    
```

So each collection is defined with a name (in a URL-friendly format), then underneat that, indented by spaces, not tabs:
* A human-readable label, enclosed in double quotes (Don't forget the double quotes!)
* A permalink format for each item in the collection
* A boolean to tell Jekyll that each object in the collection should be rendered as it's own page


Note that `prettylabel` is an arbitrary data label that I made up.


## Collections directories

Pages in each collection [must be put in a folder named](https://jekyllrb.com/docs/collections/#add-content) after the collection with a preceding underscore.

So for the collections above, I have these directories: 

```
_colophon
_course-notes
_diy-arduino
```

Don't forget the underscores!

## Listing collections and collection contents

This code lists all the collections and within each one, all the pages from that collection.

```ruby{% raw %}
{% for collection in site.collections %}
	{% if collection.label != "posts" %}

		{% assign name = collection.label %}
		{% assign pretty_name = collection.prettylabel %}
		<h2>{{ pretty_name }}</h2>

		{% for item in site[name] %}

			<h3><a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a></h3>
			<p>{{ item.excerpt }}</p>

		{% endfor %}
	{% endif %}
{% endfor %}
{% endraw %}```

One thing that isn't made clear in the docs or tutorials is that the word you use to access things in the collection is arbitrary. I've used `item` here, but it can be anything you like, and you don't have to specify it somewhere else.

The second line: `{% raw %}{% if collection.label != "posts" %}{% endraw %}` and its companion closing `endif` exclude Jekll's built-in `_posts` collection from this kind of listing.

You can also set up index pages for collections with syntax like this:

```ruby{% raw %}
---
layout: page
title: "Colophon"
permalink: "/colophon/"
---

<ul>
  {% for item in site.colophon %}
    <li>
      <a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a>
      - {{ item.excerpt }}
    </li>
  {% endfor %}
</ul>
{% endraw %}```

This page is saved at the root level as `colophon.md`. You have to create an index page like this for every collection.



## Human-readable collection names

Bizarrely, they don't seem to consider that you might want to give your collections names with spaces or capital letter, or other things tha don't work in URL slugs. 

So I created a bit of data for each collection called `prettylabel` that I can access through `collection.prettylabel`, which is a human-readable version of that collection name. It took a bit of fiddling to discover that this data needs to be enclosed in "double quotes".

## Listing collection index pages in the site navigation.

Because each collection index is a page, they can be listed simply by looping through all the pages in the site. This is the code that lists collection index pages in `_includes/header.html`:

```ruby{% raw %}
{% for path in page_paths %}
	{% assign my_page = site.pages | where: "path", path | first %}
	{% if my_page.title %}
		{% if my_page.title != "Tags" %}
			<a class="page-link" href="{{ my_page.url | relative_url }}">
			{{ my_page.title | escape }}
			</a>
		{% endif %}
	{% endif %}
{% endfor %}
{% endraw %}```



## Improvements / <span class="wip">WIP:</span> 

It would be good not to have to list all collections explicitly in the config file.


----


## The old approach

**Stop reading here if you want to implement site hierarchy using collections. For reference, below, I'm including notes I wrote on the old approach I used before, which was to use categories within posts.** 

----

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
	
	<span class="wip">WIP:</span> This is where the category naming breaks down. I need to find a way to associate a properly formated category name with each machine-readable category slug to display on this page.



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


