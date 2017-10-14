---
layout: page
title: INGENIERIA
permalink: /ingenieria/
---
<div class="home">
  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'ingenieria' or post.categories contains 'general' or post.tags contains 'base' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>
</div>
