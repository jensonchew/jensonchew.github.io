---
layout: landing
title: Projects
permalink: /projects/
---

<div class="blog-header">
  <h1>Projects</h1>
  <p>Open-source and public work on agentic development and governance.</p>
</div>

{% for project in site.data.projects %}
<div class="project-feature" style="border-top: 1px solid var(--rule); padding-top: 1.25rem; margin-top: 0.5rem;">
  <h3><a href="{{ project.url | relative_url }}">{{ project.name }}</a></h3>
  <p>{{ project.blurb }}</p>
  {% if project.tags %}
  <p class="home-section__intro">{{ project.tags | join: " · " }}</p>
  {% endif %}
  <p class="project-feature__meta">
    <a href="{{ project.url | relative_url }}">Project page</a>
    ·
    <a href="{{ project.repo }}">GitHub</a>
  </p>
</div>
{% endfor %}
