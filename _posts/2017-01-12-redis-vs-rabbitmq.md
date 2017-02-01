---
layout: post
title: "redis vs rabbitmq"
category: devtool
tags: [taskqueue]
comments: true
---
{% include JB/setup %}

Looking to track things that aren't found in main blogs to influence decision (which to use with celery.)
  
So far, there is a claim that redis sometimes will hang and then tasks will queue up until memory exhaustion and this isn't a problem with RabbitMQ.
  
Someone claims experiencing BSODs with RabbitMQ - luckily I'm not counting on windows mwuhahaha!

  
  
some background tips until i reorganize this:
  
<https://library.launchkit.io/three-quick-tips-from-two-years-with-celery-c05ff9d7f9eb#.96pcx3hhv>
  
  
celery stuff:  
https://wiredcraft.com/blog/3-gotchas-for-celery/
https://hairycode.org/2013/07/23/first-steps-with-celery-how-to-not-trip/


