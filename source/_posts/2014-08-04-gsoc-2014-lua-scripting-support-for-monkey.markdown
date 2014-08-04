---
layout: post
title: "GSoC 2014: Lua Scripting support for monkey, Week 11"
date: 2014-08-04 12:30:55 +0530
comments: true
categories: gsoc
---

I haven't been able to figure out what is causing the looping issue
that had been troubling me from last week. I have created a branch
with the old version of plugin working in blocking mode. The plugin's
current execution model is not efficient as it might block the server
thread and a thread based model is also scalable. Also I am creating a
new lua_state instance per request which could be avoided.

I have identified similar areas for performance improvement and most
important of all will be to use a coroutine based approach for
executing the lua code similar to nginx's lua module.I have started
documenting everything that are working right now.In the coming weeks,
I will complete the documentation and move on to fixing issues that I
have identified.

code: [github](https://github.com/diadara/monkey_lua)



