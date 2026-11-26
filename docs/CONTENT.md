# 内容维护指南

这份文件位于 `docs/`，不会发布到网站。下面的例子仅供复制修改，不要直接当作真实文章发布。

## 新增笔记

在 `_posts/` 创建 `YYYY-MM-DD-english-slug.md`，例如 `2026-11-25-example-slug.md`：

```yaml
---
layout: post
title: "文章标题"
date: 2026-11-25 10:00:00 +0800
permalink: /notes/example-slug/
description: "准确概括文章的一两句话。"
topic: video-codec
type: note
updated: 2026-11-25
featured: false
---

正文从这里开始。
```

`topic` 必须与 `_data/topics.yml` 中的 `slug` 一致：`video-codec`、`aigc`、`computer-graphics`、`cloud-native`。`type` 建议使用 `note`、`tutorial` 或 `case-study`。设 `featured: true` 可进入首页精选（最多显示 3 篇）。首次发布可以不写 `updated`，重要修订时再补。不要更改已发布文章的 permalink。

正文可以使用 Markdown 标题、代码块和图片。图片放入 `assets/images/`，例如 `![图表说明]({{ '/assets/images/example.webp' | relative_url }})`；为图片提供有意义的替代文字。

## 新增课程

在 `courses/` 新增 `my-course.md`。课程由作者指定章节顺序；列表按 `order` 排列：

```yaml
---
layout: course
title: "课程名称"
description: "适用对象与学习内容的一句话介绍。"
permalink: /courses/my-course/
order: 10
topic: video-codec
---

## 适合谁

写明学习者背景和先修知识。

## 课程目录

1. 第一章：链接到课时、视频、讲义或代码
2. 第二章：按授课顺序继续添加
```

资源没有公开时不要留空链接。课程页加入后会自动出现在课程列表和对应专题页。

## 其他页面

- `about.md`：个人经历、项目、兴趣和公开联系信息。
- `index.html`：首页定位、简短介绍及自动聚合区。
- `topics/*.md`：专题介绍；可设置 `start_url` 与 `start_title` 作为“从这里开始”的推荐链接。
- `_data/topics.yml`：四个专题的名称及首页简介。

提交后检查新页面、专题聚合、首页最近更新和 `/feed.xml`。课程页面并非博客文章，不会出现在 RSS 中。
