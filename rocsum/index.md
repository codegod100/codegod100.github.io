---
layout: default
title: Archive
permalink: /rocsum/
---

### Roc Zulip Daily Summaries Archive

Recent activity from the Roc language community on Zulip:

{% for post in site.categories.summary %}
  - [{{ post.date | date: "%Y-%m-%d" }}]({{ post.url }})
{% endfor %}
