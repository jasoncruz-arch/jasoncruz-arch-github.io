---
layout: page
title: Writings
permalink: /writings/
---

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-item">
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      {{ post.excerpt }}
    </article>
  {% endfor %}
</div>
