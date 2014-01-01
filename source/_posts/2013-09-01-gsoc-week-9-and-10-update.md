---
layout: post
title: "GSoC week 9 and 10 update"
location: Pilani
description: ""
category: gsoc
tags: []
---
For the past couple of weeks I have been mainly fixing errors and other issues 
that with the already ported packages caused mainly due to the reorganizing and
renaming of their dependencies. Normalizer module will be used by all the
modules instead of silpa_common normalizer.

Another issue was that the template files had to renamed to reflect the change 
in module names as the framework expects the template to be of the same
name as the package name.This behavior has  to be changed as packages may have
more than one template or another cases where the template name has to be 
different from the package name. A possible solution is adding the template
name in the  code itself But this will require changes in the way modules are
required.

I have also re-organized some of the tests and added the test suite to setup.py
so that tests could be more easily rub with a  `python setup.py test`command.

Apart from this I have partially ported
[indiccallendar](https://github.com/diadara/indiccallendar) (python backend 
working though the module is not fully finished yet ).I was also working on
flask-webfonts.I have implemented the yaml based configuration for setting up
font repositories. I am now rewriting the interface using jquery.webfonts
extension.Jquery webfonts expects data to be  fed in a certain format which is 
slightly different  from the  flask webfonts currently available api.
It was also planned to reduce the number of fields that has to be
set manually in the font configuration using some sort of mechanism to extract
metadata from the fonts files. I am yet to figure  out completely how to
it effectively as a single font can come in multiple formats and may create
conflicts in some cases.


