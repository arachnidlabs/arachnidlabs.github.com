---
layout: disquspost
title: "Plug and Play configuration with Loki"
date: 2013-01-28 19:05
comments: true
categories: loki
---
[Previously](/blog/2013/01/24/how-loki-avoids-pin-conflicts/), I wrote about how Loki avoids pin conflicts by remapping IO pins with surface mount headers on each expansion plank. I mentioned at the time that this can lead to some confusion figuring out which plank pins correspond to which microcontroller pins, and hinted at a solution. Today, we'll take a closer look at how that solution works.

The problem, if you recall, is that the Loki is set up such that each plank takes the first available pins; this means that the microcontroller pins your plank is connected to depend on what other planks are in the stack below it. Rearrange the planks, and the pin assignments change. This isn't a problem from a hardware point of view - any Loki pin can perform any function - but it can be hard to keep track of.

Loki solves this with a configuration system. Much like the Beaglebone, each expansion plank has an onboard EEPROM that contains configuration data. This data includes its name URL, optional serial number, flags, and most importantly, a description of which GPIO pins it uses. Each pin that's used is given a name determined by the plank. Likewise, the Loki has an onboard EEPROM storing the pin names of the Loki itself.

With EEPROMs on each plank, we can identify planks at runtime, and with the pin names on the Loki and the pin names on the expansion boards, we can build up a nice convenient table, allowing users to see at a glance which pin is mapped to which plank. This still ignores the sticky issue of addressing, however. Supposing we use I2C EEPROMs - how do we ensure each plank's EEPROM has a unique (and predictable) address? We could use jumpers, like BeagleBone capes do, but this seems rather manual. The consequences of setting the jumpers wrong are a lot worse for the Loki than they would be on the Beaglebone, too - the pin mappings would be inaccurate. How can we give each EEPROM a unique address, without manual intervention and undue complexity?

The answer comes to us from computer science, in the form of the [Linear Feedback Shift Register](http://en.wikipedia.org/wiki/LFSR) or LFSR. An LFSR is a way to generate a sequence of numbers that goes as long as possible without repeating. Even better, LFSRs are really simple to generate, and can be made using a single XOR operation to generate each subsequent bit!

A concrete example will be more enlightening. Suppose we want to generate all possible 3-bit addresses. A maximum length LFSR for this has 3 bits of state, and generates the next state by taking the two most significant bits and XORing them together. Suppose we start with 001. We XOR the two most significant bits together (0 XOR 0 = 0) and add them to the end, getting a new state of 010. Repeating, we then get 101, 011, 111, 110, 100, 001. Note that we stepped through every single non-zero 3-bit number before coming back to our starting point of 001.

Using this in Loki is quite straightforward. The smaller Loki expansion header has three address pins. On the Loki itself, these are hardwired to 0, 0 and 1. Each plank connects the incoming address pins directly to its EEPROM's address pins; it also shifts them left by one - so A1 becomes A2 and A0 becomes A1 - and uses a single XOR gate IC, the [74HC1G86](http://www.nxp.com/documents/data_sheet/74HC_HCT1G86.pdf) to generate the new A0 by XORing A1 and A2 together. Thus, the next plank in the stack sees the next value in the sequence, ensuring we can stack up to 7 planks without any repeating addresses. The XOR IC and the EEPROM (a [CAT24C32](http://www.onsemi.com/pub_link/Collateral/CAT24C32-D.PDF) or larger) together cost less than $0.50 in quantity, so this adds a negligible cost to the average expansion plank. Here's an example schematic for the relevant part of an expansion plank:

![](https://lh4.googleusercontent.com/1nT5oD77_QteH6qhmQM9W_kFVk6sfqL5uQ_tRlcDJEyFcrFz4o5VJLTz9AMn7efEExYBpKiVSRxk_D0fytjXx6g5wRlB15nXlf7_DvPk4bGnBQ6cDi9R)

This system has incidental benefits as well. In addition to providing a general purpose I2C bus to all planks independent of the GPIO pins, it also provides a way for planks to attach to it without risk of address conflicts. As long as the I2C ICs they use have a different fixed prefix to the EEPROMs (which use the 7-bit prefix 0x50), they can use the same address pins for their own ICs.

The end result of this is a rather nice plug-and-play system that Just Works. I'm currently working on the bootloader host software, which together with the bootloader, can autodetect all the expansion planks installed on a Loki, and present you with details of each, along with an accurate pin mapping from microcontroller pin to plank pin, with useful pin names. Keep an eye out for a demo of it soon.