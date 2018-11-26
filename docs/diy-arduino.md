---
layout: page
title: "DIY Arduino"
permalink: "/diy-arduino/"
---


_The backstory of making a fab-able Arduino Uno_

----



  {% for item in site.diy-arduino %}
<h3><a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a></h3>
<p>{{ item.excerpt }}</p>

  {% endfor %}
