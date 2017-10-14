---
layout: page
title: PROYECTOS
permalink: /proyectos/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'oficina' or post.categories contains 'proyecto' or post.tags contains 'plan' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
