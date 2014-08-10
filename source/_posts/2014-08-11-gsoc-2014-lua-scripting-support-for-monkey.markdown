---
layout: post
title: "GsoC 2014: Lua Scripting support for Monkey, Week 12"
date: 2014-08-11 01:12:58 +0530
comments: true
categories: 
---

In order to implement a nonblocking way to excecute the lua code for
the plugin I have been reading ngnix's
[http://wiki.nginx.org/HttpLuaModule](HttpLuaModule). The module is
implemented with one LUA VM per worker and each lua call/request is
run with it's own coroutine. This seems to be a better approach than
the one I am currently using as this removes the latency involved in
creating a Lua state per request as coroutines are much more
lightweight compared to lua_state, I am currently rewriting some of
the code to work in this way as it might offer much more flexibility
and performance.

from the
[https://github.com/openresty/lua-nginx-module/wiki/Introduction](lua
ngnix module wiki)
>Lua-nginx-module integrated Lua into NginX, and providing
>high-concurrent & non-blocking request processing ability without
>forcing developers explicitly dividing business logics into state
>machine. Developers can write their programs in plain-old sequential
>ways, and lua-nginx-module will automatically interrupt the program
>logic at blockable I/O operations, save the context and delegate these
>I/O ops to NginX’s event mechanism. When I/O ops are done,
>lua-nginx-module will restore the context and restore the normal
>running of the program logic. User program itself will feel everything
>as usual as never being interrupted.
>
>Lua-nginx-module uses one-coroutine-per-request
>request handling model, i.e. for each incoming request,
>lua-nginx-module creates a coroutine to run user code to process the
>request, and the coroutine will be destroyed when the request handling
>process is done. Every coroutine has its own independent global
>environment, which inherits shared read-only common data. So any
>global values injected by the user code won’t affect other request’s
>processing, and will be freed when request handling is done. You can
>imagine that user code is running in a ‘sandbox’, which shares the
>same lifecycle with the request itself. By this way, lua-nginx-module
>can prevent memory-leak caused by abusing uses of global values in
>user code, hence improve robustness.

The non blocking behaviour of the module is achieved by using
coroutines with blocking calls that yields to the event loop. This is
done using something called `cosockets` which makes writing sequential
code that works in non blocking way. In order to implement similar
functionality in monkey, this co sockets api has to rewritten to
integrate with monkeys event loop. Although this would require in
effect writing a socket library for lua that specifically works with
monkey, this will make adding more libraries easier in the future as
well as make it possible to use many of the existing libraries for
openresty to monkey lua without much effort other than that required
for dealing with lua 5.1 vs lua 5.2 issues.

This week I completed a for the api documentation. I have
a version of the plugin that is functional in the testing branch of
the repo. Making the plugin non blocking by using co sockets requires
some effort and I will try to finish this before the pencils down date.
