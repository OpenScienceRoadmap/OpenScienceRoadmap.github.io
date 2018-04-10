---
layout: default
---

# Blog

{% for item in site.posts %}
  ## {{ item.title }}
  {{ item.excerpt }}
  <a href="{{ item.url }}">Read more ></a>
{% endfor %}
