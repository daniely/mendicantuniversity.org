---
title: Activities
layout: list
header:
  <link rel="alternate" type="application/rss+xml"
  title="Activities RSS feed for Mendicant University"
  href="/activities.xml" />
---

<ul class="posts">
{% for post in site.categories.activities %}
  {% if site.time < post.date %}
    {% include upcoming_post.html %}
  {% else %}
    {% include post.html %}
  {% endif %}
{% endfor %}
</ul>
