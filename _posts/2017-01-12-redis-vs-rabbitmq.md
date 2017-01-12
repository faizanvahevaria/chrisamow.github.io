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

