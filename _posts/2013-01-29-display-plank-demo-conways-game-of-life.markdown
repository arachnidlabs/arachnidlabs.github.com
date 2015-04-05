---
layout: disquspost
title: "Display Plank demo: Conway's Game of Life"
date: 2013-01-29 21:04
comments: true
categories: loki
---

Just a short post today. I've been writing some libraries and demo apps for the Loki, and first up is the Display Plank. Here's a quick demo showing it running Conway's Game of Life:

<iframe width="640" height="360" src="http://www.youtube.com/embed/i93JgOgLXc0" frameborder="0" allowfullscreen></iframe>

That's running at nothing like full speed - I slowed it down a lot so us mere humans could comprehend it.

This was just hacked up in a hurry, but I'm currently working on a library for the display so it'll be really easy to use in your own projects. It'll make use of the PSoC's DMA facilities, so it will be a lot more efficient, too - just pass in a buffer representing the display, and it will write the whole thing out to the display with no involvement from your code or the CPU.

Keep an eye out for more details on the peripheral and the inner workings of the demo soon!