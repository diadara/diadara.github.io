---
layout: post
title: "GSoC 2014: Lua Scripting Support for Monkey, Week 7"
date: 2014-07-07 06:22:55 +0530
comments: true
categories: gsoc, code, monkey
---

This week, I was trying to get a better Idea about event driven
programming especially using epoll in specific so that I can integrate
the plugin with monkey. I found a bunch of great resources for
understanding epoll as well as other strategies and system calls
available in various operating systems to achieve concurrency.


http://kovyrin.net/2006/04/13/epoll-asynchronous-network-programming/

http://www.wangafu.net/~nickm/libevent-book/01_intro.html

I started working on sending the response back to the client by
hooking to the epoll callbacks instead of the blocking way I was using
till now to get things done till now.

Also, I was looking at a way to execute the lua code in a non
blocking way. The popular approach is to use a watchdog timer or
something along the lines mentioned in this thread

http://lua-users.org/wiki/NonBlockingLuaExecution

http://lua.2524044.n2.nabble.com/Nonblocking-script-execution-td7641186.html

I still haven't figured out a working way to make everything work
together and so haven't pushed in my changes as I am running into some
errors. 

I had to move to a new apartment this week and was under some time
constraints and this weeks work required a lot more reading before I
started coding so, that leaves me with no working code till now, I
will try to fix up my code and push it by tonight.
