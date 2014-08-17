---
layout: post
title: "GSoC 2014: Lua Scripting Support for Monkey"
date: 2014-08-18 00:36:55 +0530
comments: true
categories: gsoc 
---

This week, I managed to figure out what was causing the issue with my
previous version of the plugin. As I discussed in my previous blog
post, I changed the code execution model for the plugin. Now the code
for the script is loaded as a lua co-routine and executed. Currently
the plugin will block the thread if you make a blocking call from lua.
This can be fixed by yielding to the event loop.

Two approaches are possible to make the plugin 100% non blocking. One
is to write custom lua modules for making network calls that will
integrate with the plugins event loop. Another possible approach as I
discussed earlier was to wrap the sockets api. Currently, the plugin
is functional although I have to check for memory leaks and other
issues.

I started out the project planning to accomplish a lot more, however I
had a few roadblocks that really slowed down the progress. I had
struggled a lot but I have learned a lot about things like event
loops, networking, the HTTP specification, lua,  coroutines, and a
bunch of other interesting stuff. I want to that Eduardo and Jorge for
all the guidance they have given throughout the program. The plugin
can be improved in a lot of ways and I plan to work on it after the
GSoC, the socket library wrapper is on my list first. This will allow
porting openresty  libraries to monkey thus providing an alternative
to duda for writing web applications with minimum hassle with lua.c
