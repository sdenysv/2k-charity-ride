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

# Hello! 

I’m Denys, and this is my story “how I spent my summer vacation 2023”.

![Denys on the bike]({{ "/assets/images/cover.jpg" | relative_url }})

I took a vacation from work and rode my bike from Maastricht, Netherlands to Andermatt, Switzerland and back. Why? To raise money for kids in Ukraine, but also to have adventure, see new places, and challenge myself.

I rode 2,000 km in 18 days, and raised €2,000. I met amazing people, had injuries, and every second day I was asking myself “Why am I doing this?”. But I made it, we made it, and I’m proud of us.

It wouldn’t be possible without the support of my family, friends, and all the donors. 

Thank you!

## Stats for nerds

| Metric | Value |
| --- | --- |
| Raised | €2,000 |
| Days | 18 |
| Distance | {{ total_distance | round: 2 }} km |
| Elevation | {{ total_elevation }} m |
| Average speed | {{ avg_speed | round: 1 }} km/h |
