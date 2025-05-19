---
layout: page
title: Writings
permalink: /writings/
---

<!-- Format of file name is: YEAR-MONTH-DAY-title.md -->

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-item">
      <time class="post-date">{{ post.date | date: "%b %-d, %Y" }}</time>
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt }}</p>
    </article>
  {% endfor %}
</div>
