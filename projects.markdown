---
layout: page
title: Projects
permalink: /projects/
---

<div class="projects-grid">
  {% assign sorted_projects = site.projects | sort: "date" | reverse %}
  {% for project in sorted_projects %}
    <div class="project-thumb-link">
      <a href="{{ project.url }}">
        <img class="project-thumb" src="{{ project.thumbnail }}" alt="{{ project.title }}">
        <h3 class="project-title-link">{{ project.title }}</h3>
      </a>
      <div class="project-tags">
        {% if project.type %}
          {% for tag in project.type %}
            <a class="project-tag-link" href="?tag={{ tag | append: "" | uri_escape }}">{{ tag }}</a>
          {% endfor %}
        {% endif %}
        {% if project.location %}
          {% for loc in project.location %}
            <a class="project-tag-link" href="?tag={{ loc | append: "" | uri_escape }}">{{ loc }}</a>
          {% endfor %}
        {% endif %}
        {% if project.date %}
          <a class="project-tag-link" href="?tag={{ project.date | date: "%Y" }}">{{ project.date | date: "%Y" }}</a>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>
