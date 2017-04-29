---
layout: page
title: Automatización
permalink: /automatizacion/
---

<div class="home">

  <ul class="posts">
    {% for post in site.posts %}
    {% if post.categories contains 'electronica' or post.categories contains 'automatización' or post.tags contains 'elec' or post.tags contains 'IoT' or post.tags contains 'auto' %}
      <li>
        <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
        <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
    {% endif %}
    {% endfor %}
  </ul>

  <p class="rss-subscribe">Subscripci&oacute;n <a href="{{ "/feed.xml" | prepend: site.baseurl }}">v&iacute;a RSS</a></p>

</div>
