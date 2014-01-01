---
layout: post
title: "GSoC:Week 1 Update"
location: Kollam
description: ""
category: gsoc 
tags: []
---

Coding period started on 17th and today is 25th and that calls for an update.
I have discussed with my Mentor to reorganize the work differently from my 
proposal. Earlier I was planning to write the tests together with the 
modules (TDD). I thought it would be better if I do most of the testing and 
documentation to the last month of the programme as I want to spend moretime 
on porting tasks. 

##So progress till now:


###Separation of templates

I used jinja2's choice loader and package loader methods to look for
templates in the templates folder of each of the individual packages and
load them if there is no corresponding template in the templates folder of the
main app. There is very good [blog post](http://reliablybroken.com/b/2012/05/custom-template-folders-with-flask/) 
about how to do this. And flask is one of most well documented projects around 
and people at #pocoo were very helpful and I got  this implemented without 
much trouble.

####Packaging

This has been a very informative task for me as I got to read a lot of 
kntresting stuff like [this](http://www.clemesha.org/blog/modern-python-hacker-tools-virtualenv-fabric-pip/)
and [this](http://www.b-list.org/weblog/2008/dec/14/packaging/). It seems 
python community is still confused about what to use for packaging as the
options are plentiful. Distribute, distutils, setuptools and a lot of forking
and merging. Silpa has been using setuptools with the neat setuptools-git 
extension which packages all the git tracked files into your package.

####Fixing broken packages and PEP8

I also fixing some of the broken packages and doing some code cleaning to make
them PEP8 compaliant.

###New packages

I have ported syllabalizer and ngrams packages from silpa into their individual
packages. You can find them here: [syllabalizer](https://github.com/diadara/syllabalizer) ,
[ngrams](https://github.com/diadara/n-gram) (templates included).

###What's next ?
* port remaining modules starting with guesslanguage
* fix broken hyphenation module
