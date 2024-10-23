---
layout: page
title: coding
permalink: /coding/
description: current coding projects and associated github repositories
nav: true
nav_order: 3
display_categories: [heterogeneous agent macro, other stuff]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>

    {%- if category == "heterogeneous agent macro" %}
    <p style="margin-bottom: 10px;">
      This is a collection of my coding projects centered around heterogeneous agent macroeconomic models. 
    </p>  

    <p style="margin-bottom: 10px;">
      My work spans both policy and research domains, with a focus on developing models that investigate the implications of policy on income and wealth inequality. 
      At <a href="https://www.impa.american.edu">IMPA</a>, I developed the Julia-lang code base that implements the core model of the institution.
      On the research front, I have a keen interest in the latest solution methods for heterogeneous agent models, and have Julia-based implementations of some of these methodologies. 
    </p>  

    <p style="margin-bottom: 25px;">
      <a href="https://github.com/vasudeva-ram">Pull requests</a> welcome!
    </p>
    {%- endif %}
  
    {%- if category == "other stuff" %}
    <p>
      Some fun projects that make my life easier. More to come (when I finally get around to cleaning those repos up).
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
      {% include projects.html %}
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
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
