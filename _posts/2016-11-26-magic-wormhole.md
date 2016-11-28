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
  
The major hangup I think I have with it is the rendezvous server.  Even if it never sees unsecure data, it just has a bad feel to it.  I think Brian should have known that target users of this often practice being extra paranoid.  It is great that the server source is right there, it's just that the rendezvous server shouldn't be hardcoded in, or there should at least be a super easy frictionless option to redirect to your alternate.  I don't really want to get into a new habit of using this and then find out that the server support is discontinued and now I have to maintain my own.
  
I will probably give this a try anyway (scp transfer performance is not so great!,) but the other use case that I immediately think about is - I am at someone else's machine and I want to transfer some config files over.  I can just imagine what's going through their head when I do this "magic wormhole" stuff to transfer files lol.  That is a side conversation I will probably not be too excited to have if time pressure is a thing.
  
I don't feel as guilty not being pep8 compliant (or pycodestyle or...) - I like Brian's code, and he's been doing python a lot longer than I have (15 years he said) - and even his has tons of pep8 flags.
  
  
note to myself, investigate this (service_identity, pyOpenSSL, libsodium-dev all installed):
```
➜  work  ★ wormhole send nested.py                                                      [0] 8:32:45
Traceback (most recent call last):
  File "/home/chris/anaconda/bin/wormhole", line 11, in <module>
    sys.exit(wormhole())
  File "/home/chris/anaconda/lib/python2.7/site-packages/click/core.py", line 716, in __call__
    return self.main(*args, **kwargs)
  File "/home/chris/anaconda/lib/python2.7/site-packages/click/core.py", line 696, in main
    rv = self.invoke(ctx)
  File "/home/chris/anaconda/lib/python2.7/site-packages/click/core.py", line 1060, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/home/chris/anaconda/lib/python2.7/site-packages/click/core.py", line 889, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/home/chris/anaconda/lib/python2.7/site-packages/click/core.py", line 534, in invoke
    return callback(*args, **kwargs)
  File "/home/chris/anaconda/lib/python2.7/site-packages/click/decorators.py", line 27, in new_func
    return f(get_current_context().obj, *args, **kwargs)
  File "/home/chris/anaconda/lib/python2.7/site-packages/wormhole/cli/cli.py", line 160, in send
    from . import cmd_send
  File "/home/chris/anaconda/lib/python2.7/site-packages/wormhole/cli/cmd_send.py", line 9, in <module>
    from ..wormhole import wormhole
  File "/home/chris/anaconda/lib/python2.7/site-packages/wormhole/wormhole.py", line 9, in <module>
    from nacl.secret import SecretBox
  File "/home/chris/anaconda/lib/python2.7/site-packages/nacl/secret.py", line 18, in <module>
    import nacl.bindings
  File "/home/chris/anaconda/lib/python2.7/site-packages/nacl/bindings/__init__.py", line 17, in <module>
    from nacl.bindings.crypto_box import (
  File "/home/chris/anaconda/lib/python2.7/site-packages/nacl/bindings/crypto_box.py", line 17, in <module>
    from nacl._sodium import ffi, lib
ImportError: /home/chris/anaconda/lib/python2.7/site-packages/nacl/_sodium.so: undefined symbol: crypto_sign_ed25519_pk_to_curve25519
```

