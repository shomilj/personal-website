---
title: Tags
permalink: /tags/
layout: page
excerpt: Sorted article by tags.
---

{% for tag in site.tags %} {% capture name %}{{ tag | first }}{% endcapture %}

<h4 class="post-header" id="{{ name | downcase | slugify }}">
  {{ name | upcase }}
</h4>
{% for post in site.tags[name] %}
<article class="posts">
  <!-- <span class="posts-date">{{ post.date | date: "%b %d" }}</span> -->
  <header class="posts-header">
    <h5 class="posts-title">
      <a href="{{ post.url }}">{{ post.title | escape }}</a>
    </h5>
  </header>
</article>
{% endfor %} {% endfor %}