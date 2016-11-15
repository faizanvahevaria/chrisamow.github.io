---
layout: post
title: "deterministic gc"
category: python
tags: [python, leaks]
comments: true
---
{% include JB/setup %}
I wish python had something like the [Prompt Collection](https://github.com/qorelanguage/qore/wiki/Prompt-Collection) built in - it would make us C++ guys so happy!  (Instead of having Mr. IDisposable creeping into our beautiful python world.)
  
[PEP 343](https://www.python.org/dev/peps/pep-0343/) and the context managers need to account for larger scopes.  And it should be frictionless, no import contextlib needed.
  
oh well, there is always python4 i guess :)

