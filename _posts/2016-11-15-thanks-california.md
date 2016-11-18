---
layout: post
title: "thanks california"
category: devenv
tags: [certificates, devenv, dev]
comments: true
---
{% include JB/setup %}
  
A note to my future self from the past version who wasted time on this for a 2nd time (filtering through the many google solutions before finding the one that worked):
  
This has happened some other time besides trying to install rbenv.  Curl complains
	error setting certificate verify locations
and a BUILD FAILED error ensues.
  
several potential fixes involved linking in various other paths, this is what worked for me:
  
	sudo apt-get install ca-certificates
	sudo mkdir -p /etc/pki/tls/certs
	sudo ln -s /etc/ssl/certs/ca-certificates.crt /etc/pki/tls/certs/ca-bundle.crt
  
  
btw, this also fixes the issue with carina/rackspace setup

