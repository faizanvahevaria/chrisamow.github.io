---
category : blog
tagline: ""
tags : [blog disqus]
---
{% include JB/setup %}


## disqus embedding mysteriously not working?

Make sure you copied the up-to-date universal embedding code directly from disqus!
The important part being the "//" prefix to the shortname (instead of the full "http://"
Otherwise, you'll get a quiet mixed content error and the comments section won't display.  
  
A lot of examples out there will have embedding code you might copy, and many of them were done before github pages supported https (summer of this year.)  I saw some people out there with unresolved questions asking why there disqus wasn't working, this could be one reason.  
  
-chris
