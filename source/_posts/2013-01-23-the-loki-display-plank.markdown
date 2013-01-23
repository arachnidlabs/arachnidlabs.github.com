---
layout: post
title: "The Loki Display Plank"
date: 2013-01-23 18:24
comments: true
categories: loki
---
Today we'll take a quick look at one of Loki's initial expansion boards, the display plank.

![](https://lh4.googleusercontent.com/-m1Fb6XIYXtY/UP70JDEByeI/AAAAAAAACW4/rKQrUnBIxjU/w317-h237-n-k/P1010181.JPG)

The display plank is a straightforward user interface plank, featuring an 84x48 dot matrix LCD display with backlight, and a 5-way (4 directions plus center click) digital joystick. It takes up 8 GPIO pins from the Loki, and it's a "top plank", meaning nothing else can be stacked on top of it.

I wanted this to be a substitute for the expansion boards featured in other embedded systems that feature a 16x2 character display. I figure that a simple graphic LCD will be a lot more interesting and versatile, and no harder to drive with the right libraries.

The display is worth a closer look. It's an integrated module originally designed for the Nokia 5110 mobile phone, which makes it a bit on the venerable side, but with the significant advantage that it's now really affordable - in bulk, it can be obtained for less than $1 per display, a price that's hard to beat. I think of it as the [Casio F91W](http://en.wikipedia.org/wiki/Casio_F91W) of displays. Breakout boards are available from places like [SparkFun](https://www.sparkfun.com/products/10168), but I opted to build it directly onto the plank, to save money and improve the form factor.

The integrated controller on the LCD is the PCD8544, and speaks SPI, with an additional command/data selector pin. The protocol is well documented and quite straightforward. One of my first todos after getting the bootloader host finished and the alpha boards made is to write a library for this in PSoC creator, so that the display can simply be memory mapped and written to by blitting directly to memory, which should make using it super-easy.

The display attaches to the board with four metal clips; slots on the plank accommodate these and hold it in place. Electrical connections are via a flexible connector on the back; they simply make contact with bare pads on top of the PCB, no soldering required. If you're building your own, bear in mind that a standard 1.6mm PCB is far too thick; use 1.0mm FR4 instead.

The display itself doesn't include the backlight; it's up to the host to provide that. I've done this with four 0805 white LEDs behind the module, which light it up nicely. It'd be easy to trade these out for other colors, too. An n-channel MOSFET gives the Loki control of backlight illumination.

Finally, the joystick. This is a part I picked up in bulk from China, courtesy of a good friend, and it works pretty much how you'd expect: 5 switches, with a common pole between them. The switch is connected with the common pole to ground, and the 5 switches connected directly to Loki IO lines; it's up to Loki to pull these high using the built in pullups.

All in all, the display plank is a flexible board for basic user interaction, and I hope to be able to provide it at a much lower price than most similar expansion boards using character displays. I think this is going to make for some great demo apps, too - [Snake][1], anyone? If you've got an idea for a great way to show the plank off, don't hesitate to leave a comment, too!

[1]http://en.wikipedia.org/wiki/Snake_(video_game)