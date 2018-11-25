---
layout: page
title: "Course Notes"
permalink: "/course-notes/"
---


All the course notes

<ul>
  {% for item in site.course-notes %}
    <li>
      <a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a>
      - {{ item.excerpt }}
    </li>
  {% endfor %}
</ul>