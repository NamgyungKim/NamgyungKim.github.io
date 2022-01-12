---
title: "project"
layout: archive
permalink: categories/project
author_profile: true
sidebar_main: true
---
---
<br/>
![이미지]({{ site.url }}{{ site.baseurl }}/assets/images/common/translation_talk.png)

기간: 2021-12-29~

{% assign posts = site.categories.project %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}

