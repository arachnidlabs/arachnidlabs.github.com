---
layout: post
title: "Constant Current Plank"
date: 2013-02-04 21:25
comments: true
categories: loki
---

As mentioned in a previous progress update post, I've been working with Firehopper, from the #sparkfun channel on freenode, to design a constant current plank, aimed at driving high powered LEDs. It's just about done, with only some minor silkscreen issues to go.

![](https://github.com/arachnidlabs/loki/blob/master/schematics/currentplank/currentplank-layout.png?raw=true)

The board makes use of two [STCS2A](http://www.st.com/internet/com/TECHNICAL_RESOURCES/TECHNICAL_LITERATURE/DATASHEET/CD00185795.pdf) constant current driver ICs from ST Micro, in PowerSO form (an SOIC outline with a thermal pad on the bottom). Each is capable of controlling up to 2A at up to 40V. They support PWM - which is hooked up to Loki GPIO pins, naturally - a fault indicator for when there is no load present, and their maximum current is configurable via a shunt resistor.

The use of a shunt is actually somewhat inconvenient, since it makes adjusting the current limit awkward. There aren't a great number of 0.1 ohm potentiometers that can handle 2A out there. Instead, we've gone with a slightly more complex solution, involving an opamp. A potentiometer in a voltage divider configuration provides a reference voltage; one opamp per channel attempts to make the shunt voltage equal to that, by feedback through the controller's sense pin. This will make it easy to tweak the current limit at runtime with a single potentiometer. PWM still makes it possible to individually dim each channel from the MCU, of course.

The provision of a PWM pin makes this board a perfect fit for the PSoC's built in lighting controller module, the [PrISM](http://www.cypress.com/?rID=48890). Instead of using PWM like regular controllers, PrISM uses a random sequence generator hooked up to a comparator. Each step, the value in the comparator is compared to a generated value, and the output goes high if it's higher, and low otherwise. The result is much like PWM, but with the significant advantage that you can update the compare value at any time without glitches, and the effective illumination will quickly and smoothly adjust to the new value.

I'm quite pleased with the layout on this board, too. I've been trying pay more attention to the attractiveness of PCB layouts recently, after seeing some really nice ones in #hackvana on freenode. A symmetrical and well laid out PCB looks a lot more attractive than one with parts all over the place, and I think I've done a pretty good job here.