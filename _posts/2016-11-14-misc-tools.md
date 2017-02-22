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
  
  
cling - repl for cpp  
<https://github.com/vgvassilev/cling>  
  
  
byzanz - screencast to animated gif (apt-get)
  
  
mosh - limited mobile high latency ssh-like - apt-get single install for server/client
  
tilda - dropdown console, using it because the version of guake I can get working doesnt support multiple desktops well and building it from github is problematic because of anaconda interactions and the python-vte dependency


chrome: adblockplus, vimium
h264ify (request youtube in h264 instead of webm which doesn't have hw accel)

  
# pip stuff
  
[pytest-pudb](https://pypi.python.org/pypi/pytest-pudb)  
	py.test --pudb
	#or in the code
  
	def test_set_trace_integration():
	    # No --capture=no need
	    import pudb
	    pudb.set_trace()
	    assert 1 == 2

	def test_pudb_b_integration():
	    # No --capture=no need
	    import pudb.b
	    # traceback is set up here
	    assert 1 == 2
	  
[grip](https://github.com/joeyespo/grip) markdown previewer
  
  
click - easy commandline interface with help generation
  
easyargs - very lightweight convenient - decorator, parsing, help gen
  
pipreqs - generate requirements.txt based on imports
  

To save:

pip install --download=/path/to/save -r requirements.txt

And to restore

pip install --no-index --find-links=/path/to/save -r requirements.txt

  

#nas autoconnect utility
gigolo - yeah, that's what I said...

  
#investigate:
  
<https://github.com/miracle2k/webassets> supports Less, Sass, Coffeescript, ...

