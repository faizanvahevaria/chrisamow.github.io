---
layout: post
title: "t2.nano stress test"
description: ""
category: 
tags: []
comments: true
---
{% include JB/setup %}
I'm looking at the ever changing options for startup server hosting.  
  
I like his methodology:  
  
<https://www.concurrencylabs.com/blog/handle-thousands-of-users-with-a-t2-nano/>
  
I need to look at the cost curve of his recommendation:  

	I don’t recommend using a t2.nano to power a critical, high-traffic WordPress site. In such a case, I recommend using a combination of large instance types, ELB, Autoscaling and RDS with read replicas.

