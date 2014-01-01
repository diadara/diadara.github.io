---
layout: post
title: "GSoc:Week 6 update"
location: Pilani
description: ""
category: gsoc
tags: []
---

This week I started work on flask webfonts extension.I use mitsuhiko's
[flask-extension-wizard](https://github.com/mitsuhiko/flask-extension-wizard)
for the scaffolding and added the webfonts module as blueprint. The
css api is working smoothly and and I have started working on the
gallery interface. The interface I made was based on twitter bootstrap
and used some of the javascript components. Also there are a few bugs
and the code is somewhat messy, so I will be rewriting it.

Also the current version of the extension comes with fonts included. I
am trying to make it possible for users to add fonts to the
repository. Currently this requires the user to use a folder inside
the static folder of the main app. There are ways around this to serve
fonts from any folder but these methods have security issues.


The extension also has to handle factory pattern apps. The extension
at it's current state can handle this but advanced features of the app
object does not work. I have run into an issue with relative paths for
specifying the font directory. Next objective will be to add all these
missing features to the extension.

You can follow the development on [github](https://github.com/diadara/flask-webfonts)
