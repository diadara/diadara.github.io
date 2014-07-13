---
layout: post
title: "GSoC 2014: Lua Scripting support for monkey, Week 8"
date: 2014-07-14 00:01:53 +0530
comments: true
categories: 
---

As mentioned in the last post, the week before the last one I was
trying to understand event driven programming and monkeys use of epoll
to serve large number of connections and had started writing the
response part of the plugin and struggled to complete it.This week was
also spent on the same task except that I think I have a hold of what
am I doing. I have been studying the fast cgi and cgi plugins for
figuring out how to deal with writing response back to the client.

The CGI plugin maintains a list of connections and forks to execute
the script with a `execv` and uses two pipes to communicate with the
parent and uses epoll for getting notification when it has something
to read from the pipe and write back to the client. Similarly fast cgi
has it's own socket for communicating with monkey and uses epoll for
notification. In case of the lua plugin, I had a few options to
implement it. Till now, I have been executing lua code from the monkeys
thread which obviously will prevent the thread from doing anything else.
So the solution is to either fork and execute or spawn a new thread.

Currently, there is no particular advantage of using epoll to get
notification from the lua thread as I can only start writing to the
client socket once the entire lua script finish executing.I am stuck
on putting together this small detail and the plugin should be ready
in a bare metal state.

Next Week, I will sort out the remaining details for IO also taking
into acount chunked encoding and figure out a way to collect some
metrics on the execution.

[github](https://github.com/diadara/monkey_lua)



