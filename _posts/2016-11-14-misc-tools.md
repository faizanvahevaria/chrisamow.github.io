---
layout: post
title: "misc tools"
category: tools
tags: [devtool, tool]
comments: true
---
{% include JB/setup %}
  
accumulating random tools that are reinstalled just frequently enough so that all knowledge is forgotten
  
  
unbelievably in 2016, exif rotation data is not uniformly followed, so you may need to strip it and transform the image data...  
[exiftool](http://www.sno.phy.queensu.ca/~phil/exiftool/) can be apt installed.  
exiftool -all= some.jpg
  
  
nice static checker <https://github.com/PyCQA/pyflakes>
  
  
ffmpeg, no avconv, no ffmpeg - actual conversion below from camcorder to mp4
ffmpeg -i 00024.MTS -vcodec mpeg4 -b:v 15M -acodec libmp3lame -b:a 192k aelan.mp4

