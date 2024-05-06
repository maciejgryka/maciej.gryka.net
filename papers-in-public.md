---
layout: page
title: Papers in Public
permalink: /papers-in-public/
order: 2
---

I read one ML-related paper every weekday and post a 5-minute video summary to my [YouTube channel](https://www.youtube.com/@papersinpublic). This page collects all of those together with short text descriptions.


<div style="margin-top: 24px">
{% for collection in site.collections %}
  {% if collection.label == 'papers' %}
  {% assign sorted_items = site[collection.label] | sort:"date" | reverse %}
  {% for item in sorted_items %}
  <div style="margin-top: 24px;">
  <a id="{{ item.anchor }}" href="#{{ item.anchor}}" style=""><svg style="width: 24px; height: 24px; margin-left: -36px; margin-bottom: -42px;" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M13.19 8.688a4.5 4.5 0 0 1 1.242 7.244l-4.5 4.5a4.5 4.5 0 0 1-6.364-6.364l1.757-1.757m13.35-.622 1.757-1.757a4.5 4.5 0 0 0-6.364-6.364l-4.5 4.5a4.5 4.5 0 0 0 1.242 7.244" /></svg></a>
  <h3>
    #{{ item.order }} {{ item.title }}
    <span style="font-size: 12pt; margin-left: 12px;"><a href="{{ item.paper_url }}">[paper]</a></span>
  </h3>
  <div>
  <iframe width="560" height="315" src="{{ item.video_url }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
  </div>
  {{ item.description }}
  </div>
  {% endfor %}
  {% endif %}
{% endfor %}
</div>
