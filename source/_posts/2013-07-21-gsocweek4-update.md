---
layout: post
title: "GSoC:Week4 update"
location: kollam
description: ""
category: gsoc
tags: []
---
I had been away for most of the week as I had to attend a few
functions .I managed to get some work done
nevertheless. I had to rewrite the jinja template for the webfonts
module from scratch and it took more time than expected as I ran into
a few problems as I was not very familiar with the plugins to be used
and documentation wasn't very clear either. The templates ui is still
a little bit messy.

I am still having problems with font-face syntax as fonts are not
getting loaded in chromium and although firefox downloads the fonts,
the glyphs are not displayed properly. Lack of errors also makes the
bug difficult to fix. My current hypothesis is that the issue has
something to do with the mimetypes. It's available on
[github](https://github.com/diadara/silpa-webfonts).



This week has been a struggle for me mainly due to the lack of error
messages. I have been trying to get my version of silpa hosted on
openshift without any luck. So it seems like I to read more documentation..
