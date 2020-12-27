---
layout: default
categories : jekyll
---

{% for post in site.categories.jekyll %}
  <div class="postlist">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt }}</p>
  </div>
{% endfor %}