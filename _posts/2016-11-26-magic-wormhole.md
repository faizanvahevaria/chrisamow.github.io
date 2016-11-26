---
layout: post
title: "magic wormhole"
category: tool
tags: [tool, encryption]
comments: true
---
{% include JB/setup %}
  
my yoda split personality ponders... Creature of habit I am.
  
Should I break the scp habit?  [Magic wormhole](https://github.com/warner/magic-wormhole) seems very cool.  A nice easy pip install magic-wormhole
  
<iframe width="560" height="315" src="https://www.youtube.com/embed/oFrTqQw0_3c" frameborder="0" allowfullscreen></iframe>
  
The major hangup I think I have with it is the rendezvous server.  Even if it never sees unsecure data, it just has a bad feel to it.  I think Brian should have known that target users of this often practice being extra paranoid.  It is great that the server source is right there, it's jjust that the rendezvous server shouldn't be hardcoded in, or there should at least be a super easy frictionless option to redirect to your alternate.  I don't really want to get into a new habit of using this and then find out that the server support is discontinued and now I have to maintain my own.
  
I will probably give this a try anyway (scp transfer performance is not so great!,) but the other use case that I immediately think about is - I am at someone else's machine and I want to transfer some config files over.  I can just imagine what's going through their head when I do this "magic wormhole" stuff to transfer files lol.  That is a side conversation I will probably not be too excited to have if time pressure is a thing.
