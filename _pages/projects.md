---
layout: default 
title: Projects
permalink: /projects/
nav: true
nav_order: 3
display_categories: [Data Systems on Modern Hardware, Data Systems for Machine Learning, Formal Methods for Data Systems]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endfor %}
</div>
