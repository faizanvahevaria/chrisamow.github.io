---
layout: page
title: Chris' 2sense
tagline: sometimes you do get less than you pay for
---
{% include JB/setup %}


## Welcome!

This blog to help me keep notes of software dev interest





## Some musings:

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

