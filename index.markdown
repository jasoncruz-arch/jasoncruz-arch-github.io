---
layout: home
title: Gerald Jason Cruz
---

# Welcome to My Portfolio

Brief introduction about yourself here.

## Selected Projects

{% for project in site.projects limit:3 %}
<div class="project-thumbnail">
  <a href="{{ project.url }}">
    <img src="{{ project.thumbnail }}" alt="{{ project.title }}">
    <h3>{{ project.title }}</h3>
  </a>
</div>
{% endfor %}

[See all projects](/projects/)
