---
layout: page
title: teaching
permalink: /teaching/
description: courses I teach at CIDE, with syllabi and class materials
nav: true
nav_order: 2
display_categories: [fall 2026]
horizontal: false
---

<!-- One course card per row (overrides the 250px grid width and 350px card height from _base.scss on this page only) -->
<style>
  .projects .grid-sizer,
  .projects .grid-item {
    width: 100%;
  }

  .projects .card.course-card {
    height: 117px; /* one third of the theme's 350px project card */
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 8px;
  }

  .projects .card.course-card .course-thumb {
    width: 160px;
    height: 100%;
    object-fit: cover;
    border: 1px solid #000;
    flex-shrink: 0;
  }

  .projects .card.course-card .card-body {
    padding: 0 0 0 16px;
  }

  .projects .card.course-card .card-title {
    font-size: 1.15rem;
    margin-bottom: 0.25rem;
  }

  .projects .card.course-card .card-text {
    margin-bottom: 0.25rem;
  }

  .projects .card.course-card .course-timing {
    font-size: 0.85rem;
    color: var(--global-text-color-light);
  }
</style>

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>

    {%- if category == "fall 2026" %}
    <p style="margin-bottom: 10px;">
      Teaching materials for the Fall 2026 semester at CIDE.
    </p>  
    {%- endif %}

  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include course_card.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include course_card.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
