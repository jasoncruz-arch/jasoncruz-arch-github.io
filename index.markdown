---
layout: home
title: Gerald Jason Cruz
---

<header class="site-header">
  <nav class="main-nav">
    {% for item in site.data.navigation %}
    <a href="{{ item.link }}" class="nav-link">{{ item.name }}</a>
    {% endfor %}
  </nav>
</header>

<main class="home-grid">
  {% for project in site.projects limit:4 %}
  <article class="project-thumbnail">
    <a href="{{ project.url }}">
      <img src="{{ project.thumbnail }}" alt="{{ project.title }}">
      <h2>{{ project.title }}</h2>
    </a>
  </article>
  {% endfor %}
</main>

<footer class="site-footer">
  <p>© Gerald Jason Cruz {{ site.time | date: '%Y' }}</p>
  <p>This website is a work in progress</p>
</footer>
