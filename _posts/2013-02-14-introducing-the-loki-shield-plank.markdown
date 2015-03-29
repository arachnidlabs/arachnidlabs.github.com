---
layout: post
title: "Introducing the Loki Shield Plank"
date: 2013-02-14 20:13
comments: true
categories: loki
---

Time to introduce another Loki plank! This one's a direct result of a suggestion from a (future) user: the Shield Plank.

![](https://github.com/arachnidlabs/loki/blob/master/schematics/shieldplank/shieldplank-layout.png?raw=true)

The Shield Plank, as its name implies, provides an interface from the Loki expansion system to the Arduino one. On the bottom are standard Loki connectors; on the top are Arduino compatible stacking headers. Conveniently, the Arduino and Loki headers differ enough in their header spacing that it's possible to use thru-hole headers for both sets.

The board itself is, naturally, pretty straightforward. 20 of the Loki's 32 pins are broken out and routed to Arduino's D0-D13 and A0-A5. The remaining 12 pins are routed to headers adjacent to a prototyping area for added convenience. Of course, some or all of those pins may be unavailable due to other planks below it, but it's worthwhile to break them out anyway.

The Arduino R3's I2C headers are connected to the Loki's configuration I2C bus. The relevant power lines are connected between the Arduino and the Loki too, naturally. The only pin not connected is the AREF pin; fortunately this is infrequently used on Arduino shields.

Naturally, this plank will only work with 3.3 volt compatible Arduino shields. Fortunately, with the release of the Arduino Due, and other 3.3 volt Arduino variants, these are growing more and more common. I'm optimistic that this will open up the Loki system to a wide variety of existing expansion boards designed for the Arduino system.
