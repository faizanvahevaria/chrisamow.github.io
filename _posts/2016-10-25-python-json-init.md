---
layout: post
category : python
tagline: ""
tags : [python, json]
---
{% include JB/setup %}


## an interesting and nice way to set up json

https://gist.github.com/hrldcpr/2012250


from collections import defaultdict


Looking at:
```
	from collections import defaultdict
	def tree(): return defaultdict(tree)
	t = tree()
```

It is too fragile to be very generally useful.
As pointed out in the comments, you can't do this (nested assign):
```
	t['a']['b']['c'] = 'hello'
	t['a']['b']['c']['d'] = 'world'
```

You have to do this (but this still seems pretty cool):
```
	t['a']['b']['c']['hello']
	t['a']['b']['c']['d']['world']
```

And to wrap it up:
```
	import json
	print(json.dumps(t))
```


Is it pythonic, or is it so simple it's obsfucated, hmmmm

chris



