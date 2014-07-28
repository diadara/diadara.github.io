---
layout: post
title: "GSoC 2014: Lua Scripting support for monkey, Week 10"
date: 2014-07-28 03:40:32 +0530
comments: true
categories: 
---
I seem to have hit a roadblock as I am facing some issues with
integrating the plugin with monkey. Last week I had a working
implementation for the plugin, however on further testing, I noticed
that the plugin will fail while using some features which make use of
the monkey api as the lua execution happens in a new thread. I have
been trying to figure out ways to circumvent the issues without any
luck as I had limited time due to school work.

A temporary solution was to execute the lua code in the plugin context
itself, blocking the thread. I also found a few more issues with the
current implementation which  I am having a little  trouble in fixing.

My project is lagging behind the initial plan I had in mind, I will
try my level best from now on to make up for the lost time and
complete the project in time.

