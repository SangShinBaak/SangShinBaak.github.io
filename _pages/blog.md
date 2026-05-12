---
layout: page
title: Blog
permalink: /blog/
description: 물리 개념 정리 · 논문 리뷰 · 공부 일지
nav: true
nav_order: 2
---

{% assign sorted_posts = site.posts | sort: "date" | reverse %}

{% if sorted_posts.size == 0 %}
<p style="color: gray;">아직 작성된 포스트가 없습니다.</p>
{% else %}

<ul style="list-style:none; padding:0;">
{% for post in sorted_posts %}
  <li style="margin-bottom:2rem; padding-bottom:1.5rem; border-bottom:1px solid #eee;">
    <a href="{{ post.url | relative_url }}" style="font-size:1.1rem; font-weight:600; text-decoration:none;">
      {{ post.title }}
    </a>
    <div style="font-size:0.85rem; color:#888; margin:0.3rem 0;">
      {{ post.date | date: "%Y-%m-%d" }}
      {% if post.categories.size > 0 %}
        &nbsp;·&nbsp;
        {% for cat in post.categories %}
          <span style="background:#f0f0f0; padding:1px 7px; border-radius:10px; margin-right:3px;">{{ cat }}</span>
        {% endfor %}
      {% endif %}
      {% if post.tags.size > 0 %}
        &nbsp;
        {% for tag in post.tags %}
          <span style="background:#e8f0fe; padding:1px 7px; border-radius:10px; margin-right:3px;">#{{ tag }}</span>
        {% endfor %}
      {% endif %}
    </div>
    {% if post.description %}
    <p style="margin:0.4rem 0 0 0; font-size:0.9rem; color:#555;">{{ post.description }}</p>
    {% endif %}
  </li>
{% endfor %}
</ul>

{% endif %}
