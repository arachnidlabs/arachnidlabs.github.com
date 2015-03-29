---
layout: post
title: "Announcing Re:load v2"
date: 2013-05-30 17:00
comments: true
categories: reload
---

Re:load 2 is now available for preorder! See <a href="http://www.arachnidlabs.com/blog/2013/06/09/re-load-2-now-available-for-preorder/">this post</a> for details.

<a href="https://www.tindie.com/products/arachnidlabs/reload-the-simple-robust-affordable-dummy-load/">Re:load</a>, Arachnid Labs' DC dummy load project, has been hugely - and somewhat unexpectedly - popular. When I first listed it, I expected to get 10, maybe even 20 preorders; instead there were over 100. Since then, it's continued to sell well, and we're now nearly out of kits - the regular Re:load just sold out, and stock for Epic Re:loads is almost as scarce.

Clearly the time for a new run has arrived, and what better time to make some improvements? The basic premise and design of the Re:load has proven to be fundamentally sound, but there's always a few improvements that can be made. I've taken the best suggestions and ideas from the community along with a few of my own, and put them together when designing version 2.

<img src="https://github.com/arachnidlabs/reload/raw/master/reload-layout.png" width="400">

<!-- more -->

First of all, the whole design has been converted to surface mount. Re:load made a great and straightforward thru-hole kit, but it only barely fit into its chosen form factor. Switching to surface mount allowed me to improve the design without giving up Re:load's compact size. It also made available a much wider range of kits.

Switching to surface mount also made it possible to add mounting holes, as you can see. People have come up with a number of clever ways of mounting Re:load, and with proper mounting holes, I hope to see a lot more. Also in the form factor department, solder jumpers are provided to allow you to reverse the direction the potentiometer operates, so you can mount it on the bottom of the board without affecting the potentiometer's operation, and an alternate footprint for the FET is provided right at the edge of the PCB, in case you'd like to mount it to a larger heatsink, or a heatsink case.

Next up in the form factor changes, the spring terminals are gone. All Re:load v2 units will ship with binding posts that screw straight into the PCB, for the best of both worlds.

The test terminals have also changed. They're now 0.1" spaced, so you can attach a standard header, and a VIN pin has joined the sense pins. You can use this to sense the voltage across the Re:load.

Also new is a solder jumper for self-power. It's bridged by default, meaning Re:load v2 is powered by the device under test just like Re:load v1. But if you'd like, you can remove the jumper, and power Re:load from the Vin pin, allowing you to use it over a wider range, from 0 to 60 volts!

I've saved the best for last. The Re:load's previous LDO regulator, used to power the opamp and related circuitry, has been replaced with the [LM2936](http://www.ti.com/lit/ds/symlink/lm2936.pdf). This regulator has some fantastic features that really enhance the Re:load. It's got built in protection against being reverse biased, so we can drop the schottky diode that was required to protect the regulator. In turn, this means you can now use Re:load at full power with voltages barely over 3 volts with full reverse bias protection, where Re:load v1 only went down to 4 volts before the current limit started decreasing. At the other end of the scale, the LM2936 tolerates input voltages up to 40 volts, up from 30.

So in short:

 - Mounting holes and improved options for mounting the components on the Re:load for your custom case
 - Increased voltage range, from 3.1 volts to 40 volts, with full reverse bias protection
 - Option to power the Re:load from an external supply to support voltages from 0 to 60 volts

I'm also getting this batch of Re:loads professionally assembled by [Smart Prototyping](http://smart-prototyping.com/). This is the first time I've farmed out assembly services, so it'll be interesting to see how it goes - you can be certain I'll be writing up my experience with the process here on the blog.
