---
layout: page
title: "Colophon"
permalink: "/colophon/"
---


How this site is made

<ul>
  {% for item in site.colophon %}
    <li>
      <a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a>
      - {{ item.excerpt }}
    </li>
  {% endfor %}
</ul>