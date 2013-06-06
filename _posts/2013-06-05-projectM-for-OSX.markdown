---
layout: post
title:  "ProjectM for OSX"
date:   2013-06-05 16:23:34
categories: project-M osx
---

With college over, and in between travel plans, I found myself at home in Iowa for a few weeks with very little to do. I didn't have much time for personal programming projects during senior year (with thesis, track, social obligations etc), but I had a lot of ideas, so I decided to use this newfound free time to work on a few of them. Project number one was to find a __good music visualizer for Spotify that ran on Mac OS X__.

This turned out to be a difficult task. The hands-down best general purpose visualizer out there is [projectM](https://sourceforge.net/p/projectm), an open source port of the acclaimed MilkDrop plugin for Winamp. However, the OSX build hadn't been updated since __2007__, and the most highly viewed threads on the discussion boards all related to the woes of Mac users trying to get the source code to compile. The project maintainers hadn't commented about an OSX port since 2009, and a lot of users had seemingly given up hope. 

I should probably mention here that __I have next to no experience working in large C++ codebases__. I've just used C++ academically, and the only large codebase I've ever worked on was a Java project at Amazon last summer. In any case, I was probably the least qualified person to attempt to build a working piece of software from the projectM source. What I did have, though, was time, and after __five days of constant tinkering__, I finally have a working build that I'm mostly satisfied with! You can even download it [here](https://dl.dropboxusercontent.com/u/46809629/Code/ProjectM/1.0/projectM-jackOSX.dmg)!

I learned a lot working on projectM, and some of it will probably end up being useful someday. For example, I learned how [CMake](http://www.cmake.org/) works, what the [Qt](http://qt-project.org/) framework is, and why anyone would use these tools. I learned __how to use install_name_tool to update the load paths of dynamic libraries in an executable__, and gained a deeper appreciation of the software design tradeoffs involved with static and dynamic linking. While the source code for projectM builds without major issues on Linux (I assume), there were many modifications I had to make to get things working on OS X Lion. These were often OS X related quirks, like adding header files (sys/stat.h) to ensure that vital functions were available, adding frameworks (particularly CoreFoundation and OpenGL) for the linker, and installing SDL via [homebrew](http://mxcl.github.io/homebrew/) to obtain the sdl-config tool. Oddly enough, some of the biggest roadblocks I ran into were solved by simply using absolute paths instead of relative paths (this fixed the disappearing icons!)

Anyway, if any other Mac users out there are looking for a cool visualizer to go with Spotify, iTunes, or any other audio application, you can [download](https://dl.dropboxusercontent.com/u/46809629/Code/ProjectM/1.0/projectM-jackOSX.dmg) my project-M build and __let me know how it works!__ There are probably lots of bugs still to be ironed out, but I'm satisfied with it as a first attempt. If you already have JackOSX installed on your computer, just download [this](https://www.dropbox.com/s/vkvsvw7hzx64zew/projectM.dmg)!





