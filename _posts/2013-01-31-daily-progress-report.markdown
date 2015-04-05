---
layout: disquspost
title: "Daily progress report"
date: 2013-01-31 21:53
comments: true
categories: loki
---

I spent this evening polishing off the library code for the component to drive the Nokia display, and porting the Game of Life demo to it. Users will now have a nice convenient packaged library for using the display, with no knowledge of its wire protocol required. Data is transferred to the screen using DMA, so you can update the whole screen with no involvement at all from the CPU, making it a very efficient process. I still need to write up some documentation for the library and the Game of Life project. I'd also like to enhance the library component to add at least basic text support, so people don't have to cook up their own solution.

I've also moved the official Loki source repository to the Arachnid Labs github account; you can find it [here](https://github.com/arachnidlabs/loki/). All the schematics for the Loki and the expansion boards, the demo code, dimensional drawings, the bootloader host code, and so forth can be found there. The only component that is not yet in the repository is the bootloader code; it will be added shortly. Everything I can make OSS in this project, I will make - no 'secret sauce' held back!

Finally, I've started working with Firehopper, a denizen of the #sparkfun IRC channel on freenode, to design another Loki expansion plank. This one's a constant current driver plank, capable of driving up to 2A on two separate channels and PWM dimmable, designed for high power LEDs. Keep an eye out for an intro to it soon!