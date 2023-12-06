---
layout: post
title: History
---

<div id="title-banner" class="written">
  <h1>{{ page.title }}</h1>  
</div>
<div class="written">
{% for post in site.posts %}
  <hr>
  <a href="{{ post.url | prepend:site.baseurl }}"
     style="margin: 1rem 0; width: 100%; display: block; color: inherit; text-decoration: none; border-bottom: transparent;"
  >
    <h2 id="{{post.title}}">{{ post.title }}</h2>
    <span>
      {{ post.date | date: "%Y年%-m月%-d日" }} | {% for key in post.keywords %}.{{ key }} {% endfor %}
    </span>
    <p>{{ post.excerpt | strip_html | truncatewords: 80 }}</p>
  </a>
{% endfor %}
</div>
