---
layout: page-side
title: "Re:load Pro"
date: 2014-04-14 07:00
comments: true
sharing: true
footer: true
toc: true
section: reload-pro
---
**The Re:load Pro is currently available on Crowd Supply! [Get yours here](https://www.crowdsupply.com/arachnid-labs/re-load-pro)!**

<img src="rlpro-side.jpg" width="500">

The Re:Load Pro is an active load. It acts as a current sink, always drawing the same amount of current regardless of the voltage across it.

Active loads are incredibly useful for all sorts of electronics testing requirements. You can use one to see how a power supply performs under load, check if a battery lives up to its manufacturer's specifications for capacity or current draw, test motor drivers, or a variety of common constant-current tasks, such as testing LEDs, or even doing electroplating. With computer control of the load, you can even do your own IV-curve tracing.

The original Re:load was born out of my frustration at being unable to find a reasonably priced active load for my fairly modest testing needs. Commercial units typically cost several hundred or even thousand dollars and require substantial bench space - far from ideal for a hobbyist.

The Re:load has turned out to be an incredibly useful device for many people, but while its minimalist feature set is well suited to some applications, often you want something with a bit more oomph, better precision, or extra features. That's where the Re:load Pro comes in.

The Re:load Pro takes the robust design of the original Re:load and rebuilds it around a microcontroller. As a result, it offers a USB interface for power and control/monitoring, a good quality backlit display, and accurate voltage and current measurement. And that's just for starters!

<img src="rlpro-action.png" width="500">

The Re:load Pro's features include:

 * Dissipate 25 watts continuously, or more for short periods. Even more with the forthcoming fan kit (see below!)
 * Handle up to 6 amps or 60 volts. Works right down to 0V, too!
 * Easy to use and intuitive user-interface.
 * Current adjustable with milliamp precision over the whole range.
 * Protection against overcurrent, overvoltage, overtemperature, ESD, and reverse polarity.
 * Power supplied over USB from either a computer or a USB charger.
 * Fully isolated USB interface. Your computer is isolated from any direct interaction with dangerous voltages and currents.
 * Fully controllable over USB, with monitoring functionality. You can use your computer to program in a profile!
 * Configurable display, showing voltage, current, power, resistance, and total energy dissipated.
 * Open Source, with a USB bootloader, so you don't need expensive development tools if you want to make your own modifications. Firmware updates will be easy to install, too!

## What's inside the box?

The Re:load Pro's heart is a PSoC 4 microcontroller, from Cypress. The PSoC 4 combines an Arm Cortex M0 processor with configurable digital and analog blocks, making it possible to design incredibly flexible digital and analog solutions. This is ideal for the Re:load Pro, because it both cuts down on external components, which reduces cost and improves reliability, and makes it more flexible since a greater degree of the circuit is under firmware control.

The PSoC 4 in the Re:load Pro includes an integrated Opamp, which the Re:load Pro uses to implement the active load functionality. Sophisticated features like a trim register and configurable compensation make it possible to wring the absolute best performance out of the Opamp.

The other vital component of the Re:load Pro is the pass transistor - a BTS141. This unique component from Infineon acts like a regular FET transistor, but incorporates built in overcurrent, overvoltage, ESD and overtemperature protection. The BTS141 is a large part of what makes the Re:load so robust.

The heatsink and the enclosure are both high quality black anodised Aluminium. The heatsink is a custom extrusion, designed specifically for the Re:load Pro.

Everything from Arachnid Labs is open source. The Re:load Pro is licensed under the Apache Public License, and you can get the current source code and schematics right [here](http://github.com/arachnidlabs/reload-pro/).
