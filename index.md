---
layout: default
title: 首页
---

<h1>{{ site.title }}</h1>

<p>欢迎访问本语料库。请选择首字母以浏览词条：</p>

<ul>
  {% assign letters = site.entries | map: "title" | map: "downcase" | uniq | sort %}
  {% assign first_letters = letters | map: "slice: 0, 1" | uniq %}
  {% for letter in first_letters %}
    <li><a href="/index/{{ letter }}.html">{{ letter | upcase }}</a></li>
  {% endfor %}
</ul>

<a href="/upload.html">上传词条</a>
