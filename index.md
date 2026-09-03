---
layout: home
title: Home
---

# Jenson Chew

AI engineering and agentic systems — building governed workflows for development and runtime.

## Links

- [GitHub](https://github.com/jensonchew)
- [LinkedIn](https://www.linkedin.com/in/ming-yong-chew/)

## Featured projects

{% assign featured = site.data.projects | where: "featured", true %}
{% for project in featured %}
### [{{ project.name }}]({{ project.url }})
{{ project.blurb }}

[View project]({{ project.url }}) · [Repository]({{ project.repo }})
{% endfor %}

See all [projects]({{ '/projects' | relative_url }}).

## Blog

Posts coming soon. See the [blog]({{ '/blog' | relative_url }}) page for updates.
