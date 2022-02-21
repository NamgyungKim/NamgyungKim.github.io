---
title: "Weekly I Learned"
layout: archive
permalink: categories/wil
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.wil %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}