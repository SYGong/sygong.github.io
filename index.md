---
layout: splash
permalink: /
---

# The Journal

{% for post in site.posts %}
  [{{ post.title }}]({{ post.url }})
{% endfor %}
