---
layout: page
title: Projects
permalink: /projects/
---

<div class="projects-grid">
  {% for project in site.projects %}
    <div class="project-item">
      <a href="{{ project.url }}">
        <img src="{{ project.thumbnail }}" alt="{{ project.title }}">
        <h3>{{ project.title }}</h3>
      </a>
    </div>
  {% endfor %}
</div>
