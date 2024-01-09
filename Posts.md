---
layout: page
permalink: /posts/
---

<div class="archive">
  <h1 class="archive-category">Hack the Box</h1>
  {% for post in site.posts %}
    {% if post.categories contains 'Hack the Box' %}
      <div class="archive-item">
        <a href="{{ post.url | relative_url }}" class="archive-title fs-4">{{ post.title }}</a>
      </div>
    {% endif %}
  {% endfor %}

  <h1 class="archive-category">HTB Academy</h1>
  {% for post in site.posts %}
    {% if post.categories contains 'HTB Academy' %}
      <div class="archive-item">
        <a href="{{ post.url | relative_url }}" class="archive-title fs-4">{{ post.title }}</a>
      </div>
    {% endif %}
  {% endfor %}

  </div>
