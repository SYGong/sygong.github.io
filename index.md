# The Journal

{% for post in site.posts %}
  {{ post.date | date_to_string }}
{% endfor %}
