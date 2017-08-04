---
layout: page
title: MISCELANEO
permalink: /miscelaneo/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'oficina' or post.tags contains 'oficina' or post.categories contains 'miscelaneo' or post.tags contains 'miscelaneo' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
