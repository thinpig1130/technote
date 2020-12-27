---
layout: default
categories : Spring
---

{% for post in site.categories.Spring %}
  <div class="postlist">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt }}</p>
  </div>
{% endfor %}