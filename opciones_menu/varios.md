---
layout: page
title: VARIOS
permalink: /varios/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'varios' or post.tags contains 'miscellaneous' or post.categories contains 'general' or post.tags contains 'general' %}
      <li>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>
