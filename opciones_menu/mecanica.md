---
layout: page
title: MECANICA
permalink: /mecanica/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'mecanica' or post.categories contains 'fabricacion' or post.tags contains 'mec' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
