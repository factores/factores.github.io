---
layout: page
title: HUERTO
permalink: /huerto/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'huerto' or post.categories contains 'huerta' or post.tags contains 'huerto' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
