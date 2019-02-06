---
layout: page
title: "Course Notes"
permalink: "/course-notes/"
---


_All the course reference material, and weekly notes._

----


{% assign sorted = site.course-notes | sort: 'title' %}
  {% for item in sorted %}
<h3><a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a></h3>
<p>{{ item.excerpt }}</p>
{% endfor %}
