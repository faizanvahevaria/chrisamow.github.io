---
layout: post
title: "fuzzy finding windows"
category: fzf
tags: [fzf]
comments: true
---
{% include JB/setup %}
[fzf](https://github.com/junegunn/fzf), truly awesome.  
  
  
	#two spaces after the -d backslash, avoiding nested quote hell
	alias winact='wmctrl -i -R $(wmctrl -l | fzf | cut -d\  -f1)'
  
  
  
<img src="/images/screen_fzf_winact.gif" width="1000" >
  
finally, my bad habit of opening new browser windows instead of tabs pays off!
  
