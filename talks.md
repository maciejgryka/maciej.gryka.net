---
layout: page
title: Talks
permalink: /talks/
order: 3
---

{% for collection in site.collections %}
  {% if collection.label == 'talks' %}
  {% assign sorted_items = site[collection.label] | sort:"date" | reverse %}
  {% for item in sorted_items %}
  {% if item.video_url != nil %}
  <h2><a href="{{ item.video_url }}">{{ item.title }}</a></h2>
  {% else %}
  <h2>{{ item.title }} (video coming soon)</h2>
  {% endif %}
  <div style="font-size: 12pt">
  <span>{{ item.date | date: "%Y-%m-%d" }}</span> |
  {% if item.venue_url %}
  <span><a href="{{ item.venue_url }}">{{ item.venue }}</a></span>
  {% else %}
  <span>{{ item.venue }}</span>
  {% endif %}
  </div>
  {% if item.image %}
  <img src="{{ item.image }}" style="width: 100%">
  {% endif %}
  <p>{{ item.description }}</p>
  {% endfor %}
  {% endif %}
{% endfor %}
