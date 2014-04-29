---
layout: post
title: "GSoC 2014: Monkey Project"
date: 2014-04-28 23:20:01 +0530
comments: true
categories: gsoc life hack

---


I applied for GSoC this year also and fortunately the folks at
[monkey-project](http://monkey-project.com/) liked my proposal. My
original proposal was to work on a dashboard for Raspberry Pi using
the monkey webserver and the duda i/o framework built over it, however
my mentors asked me whether I would be interested in working with them
on another project. I was more than happy to say yes to them as this
represented a more challenging project which I must admit, a little
intimidating as I haven't had much experience in system programming
apart from making some system calls and the server client programs you
write in your computer networks course.


The project I will be working on involves creating a Lua plugin for
the monkey http server and also a memcached plugin for monkey-project.

Lua is an embeddable scripting language that can be used to add some
scripting capabilities to the monkey server. In addition to the usual
dynamic content creation, the plugin should be also able to do some
administrative tasks with the monkey server and also collect
statistics on the various api calls.The second part of the project
will be to integrate this functionality into duda as a duda package
and design a API for it.

The second project to be completed is developing a memcached plugin
for monkey that can can interface application with the popular
distributed in memory key value store database.
