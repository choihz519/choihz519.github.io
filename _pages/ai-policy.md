---
title: "AI Policy"
layout: single
permalink: /ai-policy/
classes: wide
author_profile: false
sidebar:
  nav: "main"
header:
  overlay_color: "#aed3fc"
  overlay_filter: "0.3"
---

<style>
.post-list {
  list-style: none;
  padding: 0;
  margin-top: 2em;
}

.post-item {
  padding: 1em 0;
  border-bottom: 1px solid #e8e8e8;
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}

.post-item:first-child {
  padding-top: 0;
}

.post-item:last-child {
  border-bottom: none;
}

.post-item-title {
  margin: 0;
  font-size: 1.1em;
  line-height: 1.4;
  flex: 1;
}

.post-item-title a {
  color: #333;
  text-decoration: none;
  transition: color 0.2s;
}

.post-item-title a:hover {
  color: #3d80cc;
}

.post-item-date {
  color: #999;
  font-size: 0.85em;
  white-space: nowrap;
  margin-left: 2em;
}

.pagination {
  display: flex;
  justify-content: center;
  gap: 0.5em;
  margin-top: 3em;
  padding-top: 2em;
  border-top: 1px solid #e8e8e8;
}

.pagination a,
.pagination span {
  padding: 0.5em 1em;
  border: 1px solid #ddd;
  border-radius: 4px;
  text-decoration: none;
  color: #333;
  transition: all 0.2s;
}

.pagination a:hover {
  background: #3d80cc;
  color: white;
  border-color: #3d80cc;
}

.pagination .current {
  background: #3d80cc;
  color: white;
  border-color: #3d80cc;
}

@media (max-width: 768px) {
  .post-item {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .post-item-date {
    margin-left: 0;
    margin-top: 0.3em;
  }
}
</style>

{% assign posts = site.posts | where_exp: "post", "post.categories contains 'AI-관련-정책'" %}
{% assign posts_per_page = 15 %}

<ul class="post-list">
{% for post in posts limit:posts_per_page %}
  <li class="post-item">
    <h2 class="post-item-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
    <time class="post-item-date" datetime="{{ post.date | date_to_xmlschema }}">
      {{ post.date | date: "%Y.%m.%d" }}
    </time>
  </li>
{% endfor %}
</ul>

{% assign total_posts = posts.size %}
{% assign total_pages = total_posts | divided_by: posts_per_page %}
{% assign remainder = total_posts | minus: total_pages | times: posts_per_page %}
{% if remainder > 0 %}
  {% assign total_pages = total_pages | plus: 1 %}
{% endif %}

{% if total_pages > 1 %}
<div class="pagination">
  {% for i in (1..total_pages) %}
    {% if i == 1 %}
      <span class="current">{{ i }}</span>
    {% else %}
      <a href="{{ '/ai-policy/page' | append: i | relative_url }}">{{ i }}</a>
    {% endif %}
  {% endfor %}
</div>
{% endif %}