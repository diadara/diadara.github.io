---
layout: post
title: "GSoC 2014: Lua scripting support for monkey, Week 4"
date: 2014-06-16 03:32:05 +0530
comments: true
categories: gsoc, monkey, programming
---

This week I had been working on the completing the environment
preparation for lua script execution. All basic tables `request`,
`response` and `config` have been implemented as of now. I had been
working on implementing some features that would make using the lua
scripting support easier like better query string and post data
parsing and also to provide a stack trace for easier error detection.I
have updated the example script from last time to show, how the new
features work.


A few things tripped me up like monkeys lack of query string parsing
and the fact that the query strings were not escaped caused some
problems which have been taken care of.

Next thing on my list is to write back the actual response from the
plugin and before that I have to check the code with valgrind.

code:
[github](https://github.com/diadara/monkey_lua)

