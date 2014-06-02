---
layout: post
title: "GSoC 2014: Lua Scripting Support for Monkey, Week 1"
date: 2014-05-26 00:28:51 +0530
comments: true
categories: gsoc, monkey, programming
---

I was having my university exams during the last two weeks of
community bonding period and couldn't dedicate as much time as I would
have liked as my schedule became a little tight.I also lost a bit of
time as I was moving and unfortunately lost my glasses. So my exams are
finally over and I am fully focused on the coding work now.

I started of the week by going through the lua programming manual and
few applications of the Lua C api. I made a few sample programs to
better understand the stack based api.I started working on the plugin
and made a basic configuration reader for the plugin which is very
similar to the CGI plugin. The scaffolding of the plugin is in place
and I can get into building a basic version the next week.

Most of my time this week was spend in reading code and identifying
functions and data that should be exposed through the lua scripting
framework. I haven't finalized the api yet and will have to discuss
with Jorge about the same. I have currently decided up on wrapping
certain data structures like the server config structure, the session
request structure and a few others and injecting them as globals.Then
they have to be read back. Another possible implementation could be
using explicit function calls from the lua scripts for communication. 

###Work for next week###
- Complete a basic version of the plugin.
- Draft the api and start the implementation


code: [https://github.com/diadara/monkey/commits/lua-exp](github)


