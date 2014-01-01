---
layout: post
title: "GSoc: Week 7 update"
location: Pilani
description: ""
category: gsoc
tags: []
---

I have been working on restructuring the webfonts flask extension to
make it more user friendly and general purpose. I am rewriting the
routes using method views to make the extension more compact and
extensible. I am sticking with using the main app static folder for
the fonts, and the user will have to pass a dictionary with the
font list and locations of the font files to initialize the extension.

The main objectives completed this week were:

*  rewrite the extension using view classes
* improve the api so that routes and folder structures could be
  customized
* create a bare bones template that can be shipped with the extension

I am having a little trouble organizing everything so that the
extension remains modular.I was making some circular imports which can
break in some cases. I have been going through source code of
some of the larger extensions that provide interfaces like
flask-dashed and flask-admin which uses class bsed views . I hope to
release a working version in a couple of days and move into testing
and documentation.
