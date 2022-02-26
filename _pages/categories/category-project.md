---
title: "project"
layout: archive
permalink: categories/project
author_profile: true
sidebar_main: true
---

---

## - 번역톡

{% assign posts = site.categories.TranslationTalk %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}

## - 원티드 프리온보딩 코스

{% assign posts = site.categories.pre_onboarding %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
