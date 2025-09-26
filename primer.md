---
title: Engineering & Mathematics Primer
layout: default
permalink: /primer/
---

# Engineering & Mathematics Primer

<ul>
{% assign items = site.primer | sort: 'title' %}
{% for p in items %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a></li>
{% endfor %}
</ul>
