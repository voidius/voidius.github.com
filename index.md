---
layout: default
title: Blog
---

<ul class="entries">
  {% for post in site.posts %}

  <li>
    <a href="{{ post.url }}">
      <h3>{{ post.title }}</h3>
    </a>
    {% if post.image %}<img src="{{ post.image }}" />{% endif %}
    {{ post.content }}
  </li>

  {% endfor %}
</ul>



