---
layout: page
title: ELECTRONICA
permalink: /electronica/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'elec' or post.categories contains 'auto' or post.tags contains 'elec' or post.tags contains 'IoT' or post.tags contains 'auto' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
