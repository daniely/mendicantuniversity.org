---
title: Activities
layout: list
header:
  <link rel="alternate" type="application/rss+xml"
  title="Activities RSS feed for Mendicant University"
  href="/activities.xml" />
---

<ul class="posts">
{% assign past_header_shown = false %}
{% for post in site.categories.activities %}
  {% unless post.next %}
    {% if site.time < post.date %}
      <h2>upcoming</h2>
    {% else %}
      <h2>past</h2>
      {% assign past_header_shown = true %}
    {% endif %}
  {% else %}
    {% if site.time >= post.date and past_header_shown == false %}
      <h2>past</h2>
      {% assign past_header_shown = true %}
    {% endif %}
  {% endunless %}

  {% include post.html %}
{% endfor %}
</ul>
