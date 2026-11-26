---
layout: default
title: 专题
description: 围绕四个技术方向整理的笔记与课程。
permalink: /topics/
section: topics
---
<div class="page-heading narrow">
  <p class="eyebrow">Explore</p>
  <h1>技术专题</h1>
  <p class="lead">从领域出发，找到相关笔记与课程。每个专题会随内容持续更新。</p>
</div>
<div class="topic-grid topic-grid-page">
  {% for topic in site.data.topics %}
    <a class="topic-item" href="{{ topic.slug | prepend: '/topics/' | append: '/' | relative_url }}">
      <span class="topic-number">0{{ forloop.index }}</span>
      <h2>{{ topic.title }}</h2>
      <p>{{ topic.description }}</p>
      <span class="topic-arrow" aria-hidden="true">↗</span>
    </a>
  {% endfor %}
</div>
