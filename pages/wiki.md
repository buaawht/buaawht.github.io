---
layout: page
title: 随笔
description: 简单写写
keywords: 随笔
comments: false
menu: 随笔
permalink: /wiki/
---

> 随便写点东西

<ul class="listing">
{% for wiki in site.wiki %}
{% if wiki.title != "Wiki Template" %}
<li class="listing-item"><a href="{{ site.url }}{{ wiki.url }}">{{ wiki.title }}</a></li>
{% endif %}
{% endfor %}
</ul>
