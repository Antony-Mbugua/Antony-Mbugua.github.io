---
title: "Projects"
permalink: /projects/
layout: page
---

## Projects

{% for p in site.projects %}
  <article>
    <h3><a href='{{ p.url }}'>{{ p.title }}</a></h3>
    <p>{{ p.excerpt }}</p>
  </article>
{% endfor %}
