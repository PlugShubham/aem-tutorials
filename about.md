---
layout: page
title: Home
permalink: /home/
---

<ul>
  {% for post in site.posts reversed %}
    <li>
      <a href="{{ post.permalink }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
