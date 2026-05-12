---
layout: page
title: Blog
permalink: /blog/
description: 물리 개념 정리 · 논문 리뷰 · 공부 일지
nav: true
nav_order: 2
---

<style>
  .post-list { list-style: none; padding: 0; }
  .post-item {
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .post-title {
    font-size: 1.1rem;
    font-weight: 600;
    text-decoration: none;
    color: var(--global-text-color);
  }
  .post-title:hover { color: var(--global-theme-color); }
  .post-meta {
    font-size: 0.85rem;
    color: var(--global-text-color-light);
    margin: 0.3rem 0;
  }
  .post-category {
    display: inline-block;
    background: var(--global-code-bg-color);
    color: var(--global-text-color);
    padding: 1px 8px;
    border-radius: 10px;
    margin-right: 3px;
    font-size: 0.8rem;
  }
  .post-tag {
    display: inline-block;
    background: var(--global-theme-color);
    color: #fff;
    padding: 1px 8px;
    border-radius: 10px;
    margin-right: 3px;
    font-size: 0.8rem;
    opacity: 0.85;
  }
  .post-description {
    margin: 0.4rem 0 0 0;
    font-size: 0.9rem;
    color: var(--global-text-color-light);
  }
</style>

{% assign sorted_posts = site.posts | sort: "date" | reverse %}

{% if sorted_posts.size == 0 %}
<p style="color: var(--global-text-color-light);">아직 작성된 포스트가 없습니다.</p>
{% else %}

<ul class="post-list">
{% for post in sorted_posts %}
  <li class="post-item">
    <a href="{{ post.url | relative_url }}" class="post-title">{{ post.title }}</a>
    <div class="post-meta">
      {{ post.date | date: "%Y-%m-%d" }}
      {% if post.categories.size > 0 %}
        &nbsp;·&nbsp;
        {% for cat in post.categories %}
          <span class="post-category">{{ cat }}</span>
        {% endfor %}
      {% endif %}
      {% if post.tags.size > 0 %}
        &nbsp;
        {% for tag in post.tags %}
          <span class="post-tag">#{{ tag }}</span>
        {% endfor %}
      {% endif %}
    </div>
    {% if post.description %}
    <p class="post-description">{{ post.description }}</p>
    {% endif %}
  </li>
{% endfor %}
</ul>

{% endif %}
