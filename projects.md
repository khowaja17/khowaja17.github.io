---
title: Projects
layout: default
permalink: /projects/
---

# Projects

<div class="grid cards">
  {% assign items = site.projects | sort: 'title' %}
  {% for p in items %}
    <div class="card">
      {% if p.thumb %}<img src="{{ p.thumb | relative_url }}" alt="" style="width:100%;border-radius:12px;margin-bottom:8px">{% endif %}
      <h3><a href="{{ p.url | relative_url }}">{{ p.title }}</a></h3>
      {% if p.role or p.when %}
        <p><small>{% if p.role %}{{ p.role }}{% endif %}{% if p.role and p.when %} • {% endif %}{% if p.when %}{{ p.when }}{% endif %}</small></p>
      {% endif %}
      {% if p.summary %}<p>{{ p.summary }}</p>{% endif %}
      {% if p.tags %}<p class="badges">{% for t in p.tags %}<span>{{ t }}</span>{% endfor %}</p>{% endif %}
    </div>
  {% endfor %}
</div>
