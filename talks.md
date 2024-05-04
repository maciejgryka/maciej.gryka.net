---
layout: page
title: Talks
permalink: /talks
order: 3
---

{% for collection in site.collections %}
  {% if collection.label == 'talks' %}
  {% assign sorted_items = site[collection.label] | sort:"date" | reverse %}
  {% for item in sorted_items %}
  <a id="{{ item.anchor }}" href="#{{ item.anchor}}"><svg style="width: 24px; height: 24px; margin-left: -48px; margin-bottom: -58px;" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M13.19 8.688a4.5 4.5 0 0 1 1.242 7.244l-4.5 4.5a4.5 4.5 0 0 1-6.364-6.364l1.757-1.757m13.35-.622 1.757-1.757a4.5 4.5 0 0 0-6.364-6.364l-4.5 4.5a4.5 4.5 0 0 0 1.242 7.244" /></svg></a>
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
