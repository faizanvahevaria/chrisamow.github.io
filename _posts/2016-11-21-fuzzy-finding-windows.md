---
layout: post
title: "fuzzy finding windows"
category: fzf
tags: [fzf]
comments: true
---
{% include JB/setup %}
[fzf](https://github.com/junegunn/fzf), truly awesome.  Here's what I did to get window selection working when the unruly list on my taskbar is out of control.  Most googling will advise invoking with the search by string feature, but fuzzy searching then using windowId  works so much better (sometimes the search by string doesnt even work when there are special characters involved)  
  
  
	#two spaces after the -d backslash, avoiding nested quote hell
	alias winact='wmctrl -i -R $(wmctrl -l | fzf | cut -d\  -f1)'
  
  
  
<img src="/images/screen_fzf_winact.gif" width="1000" >
  
finally, my bad habit of opening new browser windows instead of tabs pays off!  
it may seem silly, but despite trying to limit myself, I often have a few dozen windows open each on 2 or more browser(s)/instances...
  
(I changed away from using xdotool, to using just wmctrl after I did the screen capture.)
  
