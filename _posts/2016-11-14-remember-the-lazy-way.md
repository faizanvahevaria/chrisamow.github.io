---
layout: post
title: "remember the lazy way"
category: python
tags: [python]
comments: true
---
{% include JB/setup %}

easy to forget until it matters... increasingly better
  
```
#that list comprehension that just pops into your head
[x for x in xrange(1, 1000) ]

#lazy - some would say unpythonic
map(lambda x: x*2, xrange(1,1000))

#lazy (generators, yeah!)
(x*2 for x in xrange(1, 1000) )

```

where is that hidden wall floating around...
  
e.g.  
<http://stackoverflow.com/questions/855191/how-big-can-a-python-array-get/855455#855455>
	Therefore the maximum size of a python list on a 32 bit system is 536,870,912 elements
