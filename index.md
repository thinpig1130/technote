---
layout: default
title: HOME
---
<div class="body__banner">
    블로그 작성자가 <br>
    궁금하십니까?
    <input type="button" value="만나러가기">
</div>
<div class="body">
    <div class="body__container">
        <div class="content">
            {% for post in site.posts %}
            <div class="postlist">
                <p class="postlist__date">{{ post.date | date_to_string }}</p>
                <h2 class="postlist__title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
                <div class="postlist__excerpt">{{ post.excerpt }}</div>
            </div>
            {% endfor %}
        </div>
        <div class="sidebar">
            <div class="sidebar__title">
                categories
            </div>
            <ul class="sidebar__nav"> 
                {% for item in site.data.navigation %}
                <li><a href="{{ item.link | relative_url }}" {% if page.url == item.link %}style="color: red;"{% endif %}>
                    {{ item.name }}
                </a></li>
                {% endfor %}
            </ul>
        </div>
    </div>
</div>