---
layout: home
title: Home
---

# Jenson Chew

AI engineering and agentic systems — building governed workflows for development and runtime.

## Links

- [GitHub](https://github.com/jensonchew)
- [LinkedIn](https://www.linkedin.com/in/jensonchew/)
- [Substack](https://jensonchew.substack.com)

## Featured projects

{% assign featured = site.data.projects | where: "featured", true %}
{% for project in featured %}
### [{{ project.name }}]({{ project.url | relative_url }})
{{ project.blurb }}

[View project]({{ project.url | relative_url }}) · [Repository]({{ project.repo }})
{% endfor %}

See all [projects]({{ '/projects' | relative_url }}).

## Blog

Latest on the [blog]({{ '/blog' | relative_url }}): open-sourcing the agentic dev governance template and cross-links to longer reads on Substack.
