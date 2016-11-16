---
layout: page
title: Chris's 2sense
tagline: really?!
---
{% include JB/setup %}


## Seemed like a good idea at the time...

Just keeping track of notes of software dev interest.  Sometimes it was hard to find on google, sometimes it is so interesting I don't want to lose track or sometimes it's a process or code I know I'll want to refer back to in the future.  Sometimes it's just a time capsule - I want to see if my views change in the future.
  
The fractal yin yang I inverted is by [memloch](http://memloch.deviantart.com/art/Yin-Yang-Fractal-94871319)
  


## musings:

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

