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
  <h3>
    #{{ item.order }} {{ item.title }}
    <span style="font-size: 12pt; margin-left: 12px;"><a href="{{ item.paper_url }}">[paper]</a></span>
  </h3>
  <div>
  <iframe width="560" height="315" src="{{ item.video_url }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
  </div>
  </div>
  {% endfor %}
  {% endif %}
{% endfor %}
</div>
