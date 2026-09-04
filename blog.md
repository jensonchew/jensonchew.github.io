---
layout: home
title: Blog
permalink: /blog/
---

# Blog

Notes on agentic engineering, governance, and open source.

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url | relative_url }}) — {{ post.date | date: "%-d %b %Y" }}
{% endfor %}

More on [LinkedIn](https://www.linkedin.com/in/ming-yong-chew/recent-activity/articles/).
