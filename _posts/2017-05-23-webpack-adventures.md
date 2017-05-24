---
layout: post
title: "webpack adventures"
category: node
tags: [webpack]
comments: true
---
{% include JB/setup %}
  
After spending tons of time trying to get webpack code splitting to work just the way I wanted, I changed tack and got just what I wanted.  To get the benefit of building and packing js libs (some of them don't have cdn versions) and not force a js rebuild while serving the web app from a python framework, I wanted to separate my js code from the libs.
  
Here's what I did:  
- base it on the vue-cli webpack-simple (don't forget vue-cli global install needs sudo) 
- add a devbuild option to package.json  
- in main.js, export functionality we'll be calling from our js (e.g. Vue, App, etc.)  
	(comment out the app instance)  
- webpack.config.json, put library entry in output field  
	libraryTarget defaults to 'var' which is fine  
- html, make sure to have an entry for the .js file created by webpack  
	assign handy alias variables to the exports  
	fix up the paths (remove leading slashes) so the static files are found without npm dev  
	instantiate the app here or external js file  
- npm run devbuild  
  
nicccceeeeee  
