---
layout: post
title: "GSoc 2014: Lua scripting support for Monkey"
date: 2014-06-22 23:17:22 +0530
comments: true
categories: gsoc, monkey, code
---


This week I have been working on finishing up the request parsing
functionality for the plugin. The plugin can now handle
`application/x-www-form-urlencoded` as well as `multipart/form-data`
encoded form data and thus should be able to handle file uploads as
well although I haven't wired up the file-uploading part of the api yet.

I also implemented a configuration option for turning debugging on
or off which will decide whether a trace back of error will be send
back as response. To easily test all these, I went ahead and made a
blocking version for sending back the response. Everything seems to be
working fine.

###Next:

- There is no cookie handling in the api yet although headers are
    accessible, this has to be implemented.
- re-factor the code and remove errors that may have been introduced
- make the plugin work in a non-blocking way.
- decide upon how the duda package for the plugin should function


###code:
[github](https://github.com/diadara/monkey_lua)
