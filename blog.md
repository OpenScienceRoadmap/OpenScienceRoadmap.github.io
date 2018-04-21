---
layout: default
---

# Blog
JROST blog posts will be listed here.

{% for item in site.posts %}
  ## {{ item.title }}
  {{ item.excerpt }}
  <a href="{{ item.url }}">Read more ></a>
{% endfor %}
