---
layout: default
permalink: /
---

# The Journal

{% for post in site.posts %}
  - {{ post.title }}
{% endfor %}
