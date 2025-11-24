---
title: "AI Service"
layout: single
permalink: /ai-service/
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

{% assign posts = site.posts | where_exp: "post", "post.categories contains 'AI-서비스-사례'" %}
{% assign posts_per_page = 15 %}
{% assign page_number = page.path | split: '/' | last | split: '.' | first | plus: 0 %}
{% if page_number == 0 %}{% assign page_number = 1 %}{% endif %}
{% assign offset = page_number | minus: 1 | times: posts_per_page %}

<ul class="post-list">
{% for post in posts limit:posts_per_page offset:offset %}
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

{% assign total_pages = posts.size | divided_by: posts_per_page | plus: 1 %}
{% if total_pages > 1 %}
<div class="pagination">
  {% if page_number > 1 %}
    <a href="{{ '/ai-service/' | relative_url }}">&laquo; First</a>
    <a href="{{ '/ai-service/page' | append: page_number | minus: 1 | relative_url }}">&lsaquo; Prev</a>
  {% endif %}
  
  {% for i in (1..total_pages) %}
    {% if i == page_number %}
      <span class="current">{{ i }}</span>
    {% else %}
      <a href="{% if i == 1 %}{{ '/ai-service/' | relative_url }}{% else %}{{ '/ai-service/page' | append: i | relative_url }}{% endif %}">{{ i }}</a>
    {% endif %}
  {% endfor %}
  
  {% if page_number < total_pages %}
    <a href="{{ '/ai-service/page' | append: page_number | plus: 1 | relative_url }}">Next &rsaquo;</a>
    <a href="{{ '/ai-service/page' | append: total_pages | relative_url }}">Last &raquo;</a>
  {% endif %}
</div>
{% endif %}