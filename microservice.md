---
layout: postlist
categories : Microservice_Architecture
---

{% for post in site.categories.Microservice_Architecture %}
  <div class="postlist">
    <p class="postlist__date">{{ post.date | date_to_string }}</p>
    <h2 class="postlist__title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <div class="postlist__excerpt">{{ post.excerpt }}</div>
  </div>
{% endfor %}
