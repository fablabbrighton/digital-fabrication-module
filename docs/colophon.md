---
layout: page
title: "Colophon"
permalink: "/colophon/"
---


How this site is made

<ul>
  {% for item in site.colophon %}
    <li>
      <a href="{{ item.url }}">{{ item.title }}</a>
      - {{ item.excerpt }}
    </li>
  {% endfor %}
</ul>