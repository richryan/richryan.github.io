---
layout: default
title: Posts
permalink: /archive/
order: 4
---
<ul class="posts">
  {% for post in site.posts %}
    <br>
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  {% endfor %}
</ul>
