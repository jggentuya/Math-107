---
layout: default
title: Math 107 - Exercises
---

# Math 107 Exercises

## Cardinalities of Sets (Section 11)

{% assign sec11 = site.cha | where_exp: "item", "item.path contains 'Sec_11'" | sort: "path" %}
{% for exercise in sec11 %}
- [{{ exercise.path | split: '/' | last | replace: '.md', '' }}]({{ exercise.url }})
{% endfor %}
