---
layout: post
title: "gsoc: week 5 update"
location: Kollam
description: ""
category: gsoc
tags: []
---

Past week I had been trying to get the webfont module working properly
and had some difficulty setting things up. There was an issue with the
app returning different mime-types from localhost and openshift
servers. Well it turn's out that I was setting the mime-type with
<code>response.headers['content-type']</code> , now the response object
has a built in mimetype method to set the mimetype .I spent an awful
lot of time to figure out this reinventing the wheel by manually
setting the headers.

Rest of the week I worked on cleaning up the ui. The bootstrap
[slider](http://www.eyecon.ro/bootstrap-slider/) used for the slider
looks brilliant but the controls were broken, seems like the author is
not  very active and found the component to be a bit buggy and needed
a few hacks to get it working. I found a fork of the project with some
of the bugs fixed. I am considering migrating to this version of the
plugin.

I also spend some time getting familiar with the testing using
unittest module as I have to add tests to the packages. I am not
very familiar with all the functions of the ported packages so I will
focus on creating very simple tests and later on expand the test
coverage with the help of people more familiar with the respective
languages and functions of all the modules.

I had a discussion with my mentors on how this module should be added
to silpa as this module does a very specialized operation, that is
serving fonts using silpa-flask. Since it is not reusable, there's no
point in keeping it as a standalone python package. Another option was
to add the module to silpa-flask repository itself. Again this defeats
the purpose of separation of silpa modules in silpa-flask. Copyninja
suggested that this can be made into a generic flask extension which
can be used in any flask application to add webfont support. So I
spent some reading stuff on flask extensions.

The extension will have to keep some high level of code
[quality](http://flask.pocoo.org/docs/extensiondev/#approved-extensions)
to be accepted as an
[official approved extension](http://flask.pocoo.org/extensions/). I
believe this will be a very useful extension and can come in handy in
a variety of situations. So I made an initial evaluation for this and
it looks like I will have to write the extension from scratch however
the template developed can be reused. I have started working on the
flask extension and hopefully I can finish it this week itself.
