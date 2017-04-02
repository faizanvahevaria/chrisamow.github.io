---
layout: post
category : ssl
tagline: ""
tags : [letsencrypt, ssl]
---
{% include JB/setup %}


## let's encrypt!

Here's a quick start if you want to get a free ssl certificate working on a shared linux host like Arvixe.

Arvixe has no API to set up the certificates, and installing them is a paid service of theirs so their incentive to provide that is low.

Someone stepped up and made the letsencrypt accessible to everone (without root priviledges) - great job [gethttpsforfree](https://gethttpsforfree.com)   Although I thought it was interesting and useful to go through the process once, it can take a while and may be error prone.  One of the problems is that [letsencrypt](https://letsencrypt.org/) certificates only last 3 months, so you want something as simple as possible.

The next awesome guy automated much of it via their API - [dehydrated](https://github.com/lukas2511/dehydrated)

Git clone that and then scp it to your limited ssh access on arvixe.

This project has a dependency on mktemp.  You probably will not be able to apt-get it.  I found a ruby version of it that seems to work - [ruby-toolbox-mktemp](https://www.ruby-toolbox.com/projects/mktemp)
You can do a "gem install mktemp"

I set a config directory and the wellknown directory all in my home directory.
	/home/joeuser/dehydrated_config/

Make the 2 changes to the "config" file and you are good to go:

	WELLKNOWN="/home/joeuser/www/.well-known/acme-challenge"

	CONTACT_EMAIL=joe@user.com

The commandline options I found in other peoples' posts did NOT work for me, I ended up doing this:

	 ./dehydrated --cron -f /home/joeuser/dehydrated_config/config


Then the directory will look like:

	   |-accounts
	   |---aHR0cHM6Ly9h1lLXYwMS5hcubGV0c2Vu3J5cHQub3JnL2RpcmVjdG9yeQo
	   |-certs
	   |---joedomain.com

And the joedomain.com/ will have the two things you need for the arvixe cpanel gui in:
security:ssl/tls:Manage SSL sites:(Install an SSL Website section, select domain from dropdown)
  
	cert-1477216360.csr  cert.pem              fullchain-1477216360.pem  privkey.pem
	cert-1477216360.pem  chain-1477216360.pem  fullchain.pem
	cert.csr             chain.pem             privkey-1477216360.pem


First, set up the certificate.
Just fill in the top box with the cert.pem, the middle box with the privkey.pem (these are both symlinks so some of those files are redundant)  And they will have filled out the last box automatically.

Then you can install it and test your web site with the https: instead of the http:

nice!
-chris


2016-11-30 [even stronger secureness](https://gist.github.com/mapmeld/a9bcac46d1f486f81664814a799e5897)

2017-04-01 nice tool to check status <https://www.sslshopper.com/ssl-checker.html>

