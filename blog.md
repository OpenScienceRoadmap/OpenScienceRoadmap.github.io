---
layout: default
title: Blog
---

# Blog

{% for item in site.posts %}
  <h2>{{ item.title }}</h2>
  <em>{{ item.date | date: "%b %-d, %Y" }}</em>
  {{ item.excerpt }}
  <a href="{{ item.url }}">Read more ></a>
{% endfor %}
