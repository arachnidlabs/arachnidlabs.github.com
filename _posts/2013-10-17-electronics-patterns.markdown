---
layout: disquspost
title: "Electronics Patterns"
date: 2013-10-17 22:14
comments: true
categories: labs-cards
---

Coming from a software background to electronics, I tend to try and apply tools and techniques I learned in one to the other. Some skills and approaches transfer very well, while others don't. One that seems to transfer very well is the technique of looking at schematics in terms of [design patterns](http://en.wikipedia.org/wiki/Software_design_pattern).

Design patterns are quite common in software, and provide an easy way to break down a system into components that you already understand, rather than trying to understand the system as one large piece. Happily, you can take much the same approach to analyzing, understanding, and composing electronic circuits - and once you start to learn common patterns, understanding an unfamiliar circuit becomes a great deal simpler!

An example ought to make this clearer. Here's the equivalent schematic for a simple operational amplifier, [courtesy of Wikipedia](http://en.wikipedia.org/wiki/File:OpAmpTransistorLevel_Colored_Labeled.svg):

<img src="/images/OpAmpTransistorLevel.svg" width="600">

Complicated, right? But it gets a lot easier to understand when you know how to break it up into its constituent parts, and recognise the repeating patterns:

<img src="/images/OpAmpTransistorLevel_Colored_Labeled.svg" width="600">

In this annotated image, current mirrors are outlined in red, a differential amplifier in blue, voltage level shifter in green, and an output stage in cyan. Each of these are components that can be understood independent of each other, and you'll see them repeated again and again in different designs. Some of them can be broken down further into sub-patterns, too!

Or, how about a simpler example. Here's an excerpt from the Arduino Uno schematic, the part that controls switching between USB and DC plugpack power:

<img src="/images/uno-voltage-selector.svg" width="400">

And here it is, annotated to show the patterns, simple though they are:

<img src="/images/uno-voltage-selector-colored-labeled.svg" width="400">

Here, the blue box depicts a voltage divider, the green a comparator, and the red a FET switch.

This doesn't just apply to analog circuits, either - you'll find common patterns in digital, in power electronics, in fact pretty much everywhere there's human designers at work. Most people learn to recognize them implicitly, and certainly there are a number of them that get taught as such. Everyone knows what a resistor divider does, for instance, or learns it pretty quickly.

I think there's a lot of value in using patterns as a teaching tool directly, though, and once I sat down with the explicit goal of identifying and describing patterns, it wasn't hard to find a lot of them. I thought it would be very neat to print them off on cards; I could publish the source online, and include one in each Arachnid Labs package I sent out.

It didn't take long to pick out 32 patterns, ranging from the extremely common and well known, to the more advanced or esoteric - a collection I hope will have something in it for everyone. I got a few printed by [Moo](http://www.moo.com/), and took them with me to my first Mini Maker Faire, at Elephant and Castle.

Here's a few example cards. The ubiquitous resistor divider, of course:

<img src="/images/resistor_divider_card.png" width="400">

Or how about a capacitative voltage doubler, from power electronics:

<img src="/images/voltage_doubler_card.png" width="400">

If digital's more your style, there's the SR latch:

<img src="/images/sr_latch_card.png" width="400">

As you can see, each card is color coded by type, and has a schematic and a short description of its functionality, along with relevant equations and other information.

At the Maker Faire, they were popular beyond my wildest imagination. People weren't content with just one - they wanted whole decks! I wasn't really prepared for this, but after the faire, I sought out a small run printing service and got my own decks with tuckboxes made. Now they're even being [resold by Adafruit!](http://www.adafruit.com/products/1474).

As with everything else produced by Arachnid Labs, the full source is [available on GitHub](https://github.com/arachnidlabs/labs-cards/). The source files are all HTML, rendered using [wkpdf](http://plessl.github.io/wkpdf/) - apologies to anyone using Linux or Windows, though I'm certain alternatives will work with a little tweaking. The schematics are all exported from Eagle using a script that's part of the makefile.

Of course, if you'd just like a set for yourself without all the hassle, they're [available on Tindie](https://www.tindie.com/products/arachnidlabs/circuit-patterns-trading-cards-full-deck/), too.

Do you have a favorite electronics pattern that you'd like to see explained better? I'm pondering expansion decks focused on specific fields such as digital, power and analog, and I'd love to hear what patterns you think warrant going in one. Leave a note in the comments!