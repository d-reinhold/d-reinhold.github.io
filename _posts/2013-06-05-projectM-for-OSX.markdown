---
layout: post
title:  "Project-M for OSX"
date:   2013-06-05 16:23:34
categories: project-M osx
---

With college over, and in between travel plans, I found myself at home in Iowa for a few weeks with very little to do. I hadn't had much time for software development projects this past school year (with thesis, track, social obligations etc), but I had a lot of ideas, so I decided to use this free time to work on a few. Project number one was to find a __good music visualizer for Spotify that ran on OS X__.

This turned out to be a difficult task. The hands-down best general purpose visualizer out there is [project-M](https://sourceforge.net/p/projectm), an open source port of the acclaimed MilkDrop plugin for Winamp. However, the OSX build hadn't been updated since __2007__, and the most highly viewed threads on the discussion boards all related to the woes of Mac users trying to get the source code to compile. The project maintainers hadn't commented about an OSX port since 2009, and a lot of users had seemingly given up hope. 

I want to preface this by saying that __I have next to no experience working in large C++ codebases__. I've only used C++ academically, and the only large codebase I've ever worked on was a Java project at Amazon last summer. In any case, I was probably the least qualified person to attempt to build a working piece of software from the project-M source. What I did have was time, and after __five days of near constant laboring__, I finally have a working build that I'm mostly satisfied with! You can even download it [here](https://dl.dropboxusercontent.com/u/46809629/Code/ProjectM/1.0/projectM-jackOSX.dmg)!

I learned a lot working on project-M. Some of it will probably end up being useful someday. For example, I learned how Cmake works, what the Qt framework is, __how to use install_name_tool to update the load paths of dylibs in an executable__, and the software design tradeoffs involved with static and dynamic linking (at a deeper level than I appreciated them before). While the source code for project-M builds without major issues on Linux (I assume), there were many modification I had to make to get things working on OSX Lion. These were often OSX related quirks, including adding header files (sys/stat.h) to ensure that vital functions were available, adding frameworks (particularly CoreFoundation and OpenGL) for the linker, and installing SDL via [homebrew](http://mxcl.github.io/homebrew/). Oddly enough, some of the biggest hangups I ran into were solved by using absolute paths instead of relative paths (this fixes the disappearing icons!)

Anyway, if any other Mac users out there are looking for a cool visualizer to go with Spotify, iTunes, or anything really, you can [download](https://dl.dropboxusercontent.com/u/46809629/Code/ProjectM/1.0/projectM-jackOSX.dmg) my project-M build and __let me know how it works!__ There are probably lots of bugs still to be ironed out, but I'm satisfied with it as a first shot.





