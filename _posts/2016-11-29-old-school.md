---
layout: post
title: "old school"
category: python
tags: [python]
comments: true
---
{% include JB/setup %}
In this episode of I think I got burned by that before... (and I will probably get burned by again)
  
If you use old style python classes (accidentally even), i.e.
  
```
class C()
```
then setter properties will just silently not get called - hahahahaha!  (so if you were doing some processing on the incoming data, the raw data will get put there instead and when you see it in the debugger you will make faces)
  
So don't forget to do the class C(object) thing... Luckily, old style classes are gone from python3  
  
At least when you forget the annoying semicolon after a class in C++ the compiler will stop you (it will just tell you a million things are wrong with your code other than forgetting a semicolon - thanks obama)
