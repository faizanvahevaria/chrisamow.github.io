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
  
	alias winact='xdotool windowactivate $(wmctrl -l | fzf | cut -d\  -f1 )'
  
  
  
<img src="/images/screen_fzf_winact.gif" width="1000" >

