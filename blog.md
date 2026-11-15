---
layout: landing
title: Blog
permalink: /blog/
---

<div class="blog-header">
  <h1>Blog</h1>
  <p>Notes on agentic engineering, governance, and open source. Longer versions often live on <a href="https://jensonchew.substack.com" rel="noopener noreferrer">Substack</a>.</p>
</div>

<ul class="blog-list">
  {% for post in site.posts %}
  <li>
    <time class="blog-list__date" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%-d %b %Y" }}</time>
    <a class="blog-list__title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% if post.excerpt %}
    <p class="blog-list__excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
    {% endif %}
  </li>
  {% endfor %}
</ul>
