---
layout: page
title: "Course Notes LM225 2020"
permalink: "/course-notes-lm225-2020/"
---


_All the course reference material, and weekly notes for the LM225 module in 2020._

----


{% assign sorted = site.course-notes-lm225-2020 | sort: 'title' %}
  {% for item in sorted %}
<h3><a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a></h3>
<p>{{ item.excerpt }}</p>
{% endfor %}
