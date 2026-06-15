---
layout: home
---

{% assign total_distance = 0.0 %}
{% assign total_elevation = 0 %}
{% assign total_seconds = 0 %}
{% for post in site.posts %}
  {% assign total_distance = total_distance | plus: post.distance %}
  {% assign total_elevation = total_elevation | plus: post.elevation %}
  {% assign total_seconds = total_seconds | plus: post.moving_time_s %}
{% endfor %}

{% assign total_hours = total_seconds | divided_by: 3600 %}
{% assign rem = total_seconds | modulo: 3600 %}
{% assign total_mins = rem | divided_by: 60 %}
{% assign total_secs = rem | modulo: 60 %}
{% assign avg_speed = total_distance | times: 3600.0 | divided_by: total_seconds %}

| Metric | Value |
| --- | --- |
| Raised | €2,000 |
| Days | 18 |
| Distance | {{ total_distance | round: 2 }} km |
| Elevation | {{ total_elevation }} m |
| Average speed | {{ avg_speed | round: 1 }} km/h |
