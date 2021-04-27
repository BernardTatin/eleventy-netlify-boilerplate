---
title: From NetBSD 8.1 to NetBSD 9.1
metaDescription: An update with somme flaws.
date: 2021-04-27T21:29:20.598Z
author: Bernard Tatin
summary: When I made an update from 8.1 to 8.2, I forgot to run some commands which let the system unstable.
tags:
- NetBSD
- Unix
- update
---

A few years ago I installed _NetBSD 8.1_ on a SSD. I made an upgrade to _NetBSD 8.2_ without reading the associated documentation. The result was sometimes unstable. 

When I upgraded to _9.1_ a few days ago, the result is always unstable but the version of _Firefox_ is very recent, so I can write in that blog and I can access to all settings of my _GitHub_ repositories.

To compile and run some code, I had to remove some libs from `/usr/pkg/lib`:

- `libGL.so.1.2.0` and all it s symbolic links, there is a `/usr/X11R7/lib/libGL.so.3.0`,
- `libGLU.so.1.3.1` and all its symbolic links, there is a `/usr/X11R7/lib/libGLU.so.3.0`. 

These old libs may confused the linker.

The last problems:

- `xdm` does not work: the only key which works is the _Enter_ key,
- some terminals like `xfce4-terminal` does not have a title bar,
- and certainly many more...


