---
layout: page
title: Projects
permalink: /projects/
---

# Projects

Open-source and public work.

{% for project in site.data.projects %}
## [{{ project.name }}]({{ project.url }})

{{ project.blurb }}

{% if project.tags %}*Tags: {{ project.tags | join: ", " }}*{% endif %}

[Project page]({{ project.url }}) · [GitHub]({{ project.repo }})

{% endfor %}
