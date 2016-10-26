---
layout: page
title: Chris's 2sense
tagline: really?!
---
{% include JB/setup %}


## greetings!

This blog to help me keep notes of software dev interest.  Sometimes it was hard to find on google, sometimes it is so interesting I don't want to lose track...



## musings:

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

