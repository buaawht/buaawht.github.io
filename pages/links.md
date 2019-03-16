---
layout: page
title: Links
description: 记录一下优秀学习资料、优秀项目、优秀博客
keywords: 友情链接
comments: true
menu: 链接
permalink: /links/
---

> God made relatives. Thank God we can choose our friends.

{% for link in site.data.links %}
* [{{ link.name }}]({{ link.url }})
{% endfor %}
