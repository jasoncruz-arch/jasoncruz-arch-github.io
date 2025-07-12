---
layout: page
title: Writings
permalink: /writings/
---

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-item">
      <a href="{{ post.url | relative_url }}">
        <img class="post-thumbnail" src="{{ post.thumbnail | default: '/assets/images/default-essay-thumb.jpg' }}" alt="{{ post.title | escape }} thumbnail">
      </a>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      <div class="post-meta-row">
        {% if post.tags %}
          <span class="post-tag">{{ post.tags[0] }}</span>
        {% endif %}
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      </div>
      <div class="post-description">
        {{ post.excerpt | strip_html | truncatewords: 30 }}
        <br> <br>
      <a href="{{ post.url | relative_url }}" class="read-more-link">
          Read more <span class="arrow">&rarr;</span>
      </a>
      </div>
    </article>
  {% endfor %}
</div>
