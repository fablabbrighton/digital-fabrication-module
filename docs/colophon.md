---
layout: page
title: "Colophon"
permalink: "/colophon/"
---


_How this site is made._

----


  {% for item in site.colophon %}
<h3><a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a></h3>
<p>{{ item.excerpt }}</p>
    
  {% endfor %}
