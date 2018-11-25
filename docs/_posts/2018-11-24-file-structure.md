---
layout: post
title:  "File structure"
date:   2018-11-24
categories: colophon
---
How are the files in this project organised?

<!--more-->


### Git repo

Everything is inside a Git repository on my local computer. It syncs with a remote repo on GitHub, here:
<https://github.com/andrewsleigh/digital-fabrication-module>

*Root*
`Digital Fabrication Module/`
Lives at https://github.com/andrewsleigh/digital-fabrication-module on GitHub

*Docs* 
`Digital Fabrication Module/docs`
Generate the static site to this folder using Jekyll and push to GitHub with other files, so they can be seen there too. This folder will be a mirror of https://andrewsleigh.com/learning/digital-fabrication-module

*Posts or Pages?*
e.g. my DIY Arduino notes. Should these be published as /posts/ in a blog format, e.g. 
`docs/_posts/2018-11-17-diyardiuno.md`
Or as root level /[pages](https://jekyllrb.com/docs/pages/)/ within the docs folder, e.g. 
`docs/diyardiuno.md`

From https://jekyllrb.com/docs/pages/
> If you have a lot of pages, you can organize them into subfolders. The same subfolders that are used to group your pages in our project’s source will exist in the `_site` folder when your site builds.



*Project or assignment resources, e.g*
`Digital Fabrication Module/DIYArduino`
Code or assets for specific assignments or projects

Or should these live inside `docs`?


## Trying Jekyll
### Setup

Go to folder
`cd /Users/Andrew/Dropbox/Work/Digital\ Fabrication\ Methods/Website` 

Create new Jekyll site, assuming it will live within a docs folder (This can be mirrored within a git repo):
`jekyll new docs`

Go into that new folder:
`cd docs/`

Run the Jekyll `serve` command:
`bundle exec jekyll serve`

Go to the dev site:
http://127.0.0.1:4000/

Try adding some sample content as pages inside folders

Think I need to add hierarchy using /collections/: https://jekyllrb.com/docs/collections/

Add this to _config.yml
```
collections:
 - diy-arduino
```

Add my sample posts to the `diy-arduino/` folder
Rerun the serve command

Can’t get this to work, so also tried using a category setup, which also didn’t work (possibly because its set up for posts, not pages)


2 options:
1. Follow these instructions for collections: https://ben.balter.com/2015/02/20/jekyll-collections/
2. Or these (Which I think I did for my podcast posts): https://kylewbanks.com/blog/creating-category-pages-in-jekyll-without-plugins 

Think 1 is the most logical way to go…

Nope - can’t get that to work. Alternative method:

Change permalinks for posts to remove dates:
Add this line to config.yml:

`permalink: /:categories/:title:output_ext`

This removes dates from the default format, which is:
`permalink: /:categories/:year/:month/:day/:title:output_ext`

Then implement category pages as per https://kylewbanks.com/blog/creating-category-pages-in-jekyll-without-plugins 


---

OK, so final setup 

Write all docs as dated posts, and store in the root level _posts/ folder  
Use the permalinks setting to remove dates from post URLs
Assign categories to posts, so they can be grouped, as per the standard [Jekyll docs for categories](https://jekyllrb.com/docs/posts/#categories-and-tags)
Add a category.html page in _layouts/ which will be the template for listing all posts within a category – an index template for a category
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


Add a similar home.html page in _layouts/ which will override the default homepage template to list all posts by category:

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



Add a simple page for each category inside the category/ folder. These all have the same format:
```
---
layout: category
title: DIY Arduino
category: diy-arduino
---
```


Don’t use collections, or pages, or store pages in special folders. Remove these from the site or any special commands from the config.yml file





## A few notes on Markdown (and Jekyll)

Markdown is great, but it has a few quirks worth noting. These can be made more irksome when wrapping your Markdown in Jekyll's 'liquid' syntax.

### Line breaks
In these notes, I’m writing a lot of sentence fragments, so I need to use a lot of line break – as opposed to paragraphs. [These have a special syntax](https://daringfireball.net/projects/markdown/syntax#p):

> The implication of the “one or more consecutive lines of text” rule is that Markdown supports “hard-wrapped” text paragraphs. This differs significantly from most other text-to-HTML formatters which translate every line break character in a paragraph into a `<br />` tag.
> When you _do_ want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.


### Spaces in category names
If you want categories that have more than one word, you need to encapsulate them with [square brackets], like this:

```
categories: [DIY Arduino]
```
