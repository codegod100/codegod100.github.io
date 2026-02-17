---
layout: page
title: Roc Zulip Daily Summaries
permalink: /rocsum/
---

This page lists recent daily summaries from the Roc Zulip realm.

{% for post in site.categories.summary %}
  - [{{ post.date | date: "%Y-%m-%d" }}]({{ post.url }})
{% endfor %}

