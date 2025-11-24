---
layout: splash
author_profile: false
header:
  overlay_color: "#aed3fc"
  overlay_filter: "0.3"
excerpt: "AI를 더 쉽고 안전하게, 모두를 위한 AI 서비스 가이드"
---

<style>
/* 헤더 정렬 및 간격 */
.page__hero--overlay {
  text-align: left;
}

.page__hero--overlay .wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2em;
}

.page__hero--overlay .page__title {
  text-align: left;
  margin: 0 0 0.5em 0;
}

.page__hero--overlay .page__lead {
  text-align: left;
  max-width: none;
  margin: 0;
  padding: 0;
  margin-top: 0.8em;
}

.category-intro {
  text-align: left;
  font-size: 1.1em;
  color: #666;
  margin: 2em auto 3em;
  max-width: 1200px;
  padding: 0 2em;
}

.category-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2em;
  margin: 0 auto 4em;
  max-width: 1200px;
  padding: 0 2em;
}

.category-card {
  background: #fff;
  border-radius: 12px;
  padding: 2em;
  text-align: center;
  transition: all 0.3s ease;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  position: relative;
  overflow: hidden;
}

.category-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #3d80cc, #175eb0);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.category-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0,0,0,0.15);
}

.category-card:hover::before {
  transform: scaleX(1);
}

.category-icon {
  font-size: 3em;
  margin-bottom: 0.5em;
}

.category-card h3 {
  color: #333;
  font-size: 1.4em;
  margin: 0.5em 0;
}

.category-card p {
  color: #666;
  font-size: 0.95em;
  margin: 1em 0 1.5em;
}

.category-btn {
  display: inline-block;
  padding: 0.6em 1.5em;
  background: #e8e8e8;
  color: #666 !important;
  text-decoration: none;
  border-radius: 6px;
  transition: all 0.3s ease;
  font-weight: 500;
}

.category-btn:hover {
  background: #d0d0d0;
  transform: scale(1.05);
}

.recent-posts {
  max-width: 1200px;
  margin: 4em auto;
  padding: 0 2em;
}

.recent-posts h2 {
  text-align: left;
  font-size: 2em;
  margin-bottom: 1.5em;
  color: #333;
}

.post-list {
  list-style: none;
  padding: 0;
}

.post-item {
  background: #fff;
  border-radius: 8px;
  padding: 1em 1.5em;
  margin-bottom: 0.8em;
  transition: all 0.3s ease;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.post-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 16px rgba(0,0,0,0.1);
}

.post-item-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}

.post-item-title {
  flex: 1;
  margin: 0;
  font-size: 1.1em;
}

.post-item-title a {
  color: #333;
  text-decoration: none;
}

.post-item-title a:hover {
  color: #3d80cc;
}

.post-item-meta {
  display: flex;
  gap: 1em;
  align-items: center;
}

.post-item-category {
  display: inline-block;
  padding: 0.2em 0.6em;
  background: #e3f2fd;
  color: #1976d2;
  border-radius: 4px;
  font-size: 0.75em;
  font-weight: 500;
}

.post-item-date {
  color: #999;
  font-size: 0.85em;
  white-space: nowrap;
}

@media (max-width: 768px) {
  .category-cards {
    grid-template-columns: 1fr;
  }
  
  .post-item-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .post-item-meta {
    margin-top: 0.5em;
  }
}
</style>

<div class="category-intro">
  최신 AI 서비스와 기술 및 정책을 공유합니다.
</div>

<div class="category-cards">
  <div class="category-card">
    <div class="category-icon">🤖</div>
    <h3>AI Service</h3>
    <p>최신 AI 서비스 소개</p>
    <a href="/ai-service/" class="category-btn">More</a>
  </div>
  
  <div class="category-card">
    <div class="category-icon">🚀</div>
    <h3>AI Tech</h3>
    <p>AI 기술 동향 및 발전 방향</p>
    <a href="/ai-tech/" class="category-btn">More</a>
  </div>
  
  <div class="category-card">
    <div class="category-icon">📋</div>
    <h3>AI Policy</h3>
    <p>국내외 AI 정책 및 규제 동향</p>
    <a href="/ai-policy/" class="category-btn">More</a>
  </div>
</div>

<section class="recent-posts">
  <h2>Recent Posts</h2>
  <ul class="post-list">
    {% for post in site.posts limit:10 %}
    <li class="post-item">
      <div class="post-item-header">
        <h3 class="post-item-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>
        <div class="post-item-meta">
          {% if post.categories.first %}
            {% assign category = post.categories.first %}
            {% if category == "AI-서비스-사례" %}
              <span class="post-item-category">AI Service</span>
            {% elsif category == "AI-기술-트렌드" %}
              <span class="post-item-category">AI Tech</span>
            {% elsif category == "AI-관련-정책" %}
              <span class="post-item-category">AI Policy</span>
            {% else %}
              <span class="post-item-category">{{ category }}</span>
            {% endif %}
          {% endif %}
          <time class="post-item-date" datetime="{{ post.date | date_to_xmlschema }}">
            {{ post.date | date: "%Y.%m.%d" }}
          </time>
        </div>
      </div>
    </li>
    {% endfor %}
  </ul>
</section>