---
layout: page
title: "Guides"
permalink: "/guides/"
---


_Guides to help with weekly assignments._

----



  {% for item in site.guides %}
<h3><a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a></h3>
<p>{{ item.excerpt }}</p>

  {% endfor %}
