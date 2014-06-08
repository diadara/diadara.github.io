---
layout: post
title: "GSoC 2014: Lua scripting support for Monkey, Week 3"
date: 2014-06-08 22:55:47 +0530
comments: true
categories: gsoc, monkey, programming
---

I started out populating the the lua environment where the scripts
will be executed using the lua C api. I am pushing a global lua table
`mk` for the time being which would contain all the variables and
functions that I am currently implementing.I have a function mk.print
that will buffer everything and print to a static file. Currently we
will have 3 tables under monkey, `config`, `request` and `response`.
The `request` table will all the request headers in native lua types
and the `response` table will have the defaults, which when modified
read back to set response headers.

 `request` and `config` table have been implemented, `response` is yet
 to be implemented and and the already implemented tables could use
 some polish.

 I have also added an [example lua script](https://github.com/diadara/monkey_lua/blob/master/example/test.lua) which shows how the current
 api looks like. 

###Next Week
- Finish up the environment preparation
- Start Working on thread safe lua execution


CODE:
I moved the plugin code to a new repo
[github](https://github.com/diadara/monkey_lua)
