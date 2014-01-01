---
layout: post
title:  "GSoC, flask, python, SMC and SILPA"
location: Kollam
date:   2013-06-11 07:53:31
categories: gsoc
---
![Google Summer of Code 2013][logo]

One more attempt at blogging and I will probably continue with this at least 
for this summer. My proposal for this years Google Summer of Code  got through
and I will be writing code for [Swathanthra Malayalam Computing][SMC] this
summer. [SMC][SMC] is community of open source enthusiasts interested in 
creating software for people to use in their language of choice. They maintain
font repositories and take part in [i18n][i18n] of popular software as well as 
maintain a few projects such as [SILPA][SILPA], Dhwani TTS and also provide an
indic webfonts service. For a full list of their activities do visit their 
[site][SMC].

My proposal was to complete the porting of [SILPA][SILPA], the language 
processing package into a more modular structure using the [flask][flask] micro
web framework written in python. Jishnu Mohan  is my alloted mentor for the
project with Vasudev Kammath (aka copyninja) and Santhosh Thotingal acting
as a secondary mentor.They are the current maintainers of the project which aims
to bring  language processing tools for indic languages.

The community bonding period started on 28th May
and I am supposed to read the documentation and go through the source code and interact
with the community members till the coding period kicks off at 21st of June.For
the last two weeks I have been idling on #pocoo on freenode (these guys made flask,
 jinja2 and a lot of other cool python projects) and the people there
seemed to be really cool and are helpful to n00bs.I have been looking at some 
python packaging tools, unittesting frameworks and PEP recommendations for 
packaging.SILPA is currently using setup tools, with the setup-tools-git
extension which adds all the git tracked files into the python package without 
the need of any fiddling around in the MANIFEST.in file.I will be using pythons
built in unittest framework, unittest to write tests for this project.I had taken
[edX's](http://edx.org) SaaS class last semester,(which is a very good course,
very challenging if you don't know ruby, like me when I took the course)
where I heard a lot about Test Driven Development and hope to
follow some good coding practices for this project.

I have made some prototypes for the proposed template separation and hope to hit
the road running when the coding period starts.Till then  more
code reading to get familiar  with all the modules of silpa. Since I have a little time 
on my hands now, I have some spring cleaning to do(or rather summer cleaning or formatting my
archlinux system, a new .vimrc and a new playlist).I have learnt a lot as a 
developper during the gsoc application period and I am sure I will learn even
more.That's it for now, the talk is done, next time there will be some code
to show.
>Talk is cheap. Show me the code.
>Torvalds, Linus (2000-08-25). Message to linux-kernel mailing list. Retrieved on 2006-08-28.


[SMC]: http://smc.org.in/
[SILPA]: http://silpa.org.in/
[SILPA-Flask]: https://flasksilpa-indic.rhcloud.com
[flask]: http://flask.pocoo.org/
[i18n]: https://en.wikipedia.org/wiki/Internationalization_and_localization
[logo]: /images/soc-logo-bw2.jpg
