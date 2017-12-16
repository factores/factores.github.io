---
layout: page
title: LABORATORIO
permalink: /laboratorio/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'fablab' or post.categories contains 'laboratorio' or post.tags contains 'fablab' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
