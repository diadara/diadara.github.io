---
layout: post
title: "GSoC 2014: Lua Scripting Support for Monkey"
date: 2014-07-01 00:38:16 +0530
comments: true
categories: gsoc, monkey, code
---

Last week, I started to  re-factor the code I had already written for
the plugin. During the course of the project, I have been reading
source code from  ngnix and apache respective lua modules to
understand good coding patterns for lua and to understand good ways
for getting things done. I am using LUA's lightuserdata that allows to
access C datastructures from LUA code and also wrote a bunch of
functions to help building on top of it easier. Also I have tried to
make the code more modular.

I was also working on adding cookie support to the lua environment,
which took more time than I had expected. You
can get a table of all the set cookies from `mk.cookies.get_cookies()`
function call and set a cookie by this syntax
`mk.cookie.set_cookie{name=[name], value=[value], secure=true,
expires= os.time()+ 60*60*12}`

####Next Week:

- Make the response in a non blocking way
- Start work on the duda plugin

###code:
[github](https://github.com/diadara/monkey_lua/commits)
