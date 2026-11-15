---
layout: landing
title: Home
---

<section class="home-hero">
  <h1 class="home-hero__brand">Jenson Chew</h1>
  <p class="home-hero__lede">AI engineering and agentic systems — governed workflows for development and runtime.</p>
  <ul class="home-hero__actions">
    <li><a class="is-primary" href="{{ '/blog/' | relative_url }}">Read the blog</a></li>
    <li><a href="{{ '/projects/' | relative_url }}">Projects</a></li>
    <li><a href="https://jensonchew.substack.com" rel="noopener noreferrer">Substack</a></li>
  </ul>
</section>

<section class="home-section">
  <h2>Featured project</h2>
  <p class="home-section__intro">Open work you can clone and use.</p>
  {% assign featured = site.data.projects | where: "featured", true %}
  {% for project in featured %}
  <div class="project-feature">
    <h3><a href="{{ project.url | relative_url }}">{{ project.name }}</a></h3>
    <p>{{ project.blurb }}</p>
    <p class="project-feature__meta">
      <a href="{{ project.url | relative_url }}">Project page</a>
      ·
      <a href="{{ project.repo }}">Repository</a>
      ·
      <a href="{{ '/projects/' | relative_url }}">All projects</a>
    </p>
  </div>
  {% endfor %}
</section>

<section class="home-section">
  <h2>Latest writing</h2>
  <p class="home-section__intro">Governance notes and build-in-public essays.</p>
  <ul class="post-list-home">
    {% for post in site.posts limit:5 %}
    <li>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%-d %b %Y" }}</time>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
  <p class="project-feature__meta"><a href="{{ '/blog/' | relative_url }}">All posts</a></p>
</section>
