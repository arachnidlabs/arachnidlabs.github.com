---
layout: page
title: "manual"
date: 2013-07-17 21:57
comments: true
sharing: true
footer: true
---

Congratulations on your new Minimatrix! Using it is quite straightforward. Here's how!

## Batteries

Minimatrix takes a single CR2032 button cell. Make sure to insert it with the '+' facing outwards; inserting the battery backwards could damage your Minimatrix!

## Power

To turn the minimatrix on or off, press the power button on the remote control, or hold the button on the back of the minimatrix for at least half a second.

When turned off, Minimatrix goes into a low power mode. The battery will last approximately a month in this mode; if you intend to leave it off for a long time, you should remove the battery.

## Changing the message

By default, minimatrix shows a scrolling text message. To enter edit mode:

 1. Press the 'Menu' button on your remote control to enter menu mode. A play symbol will be displayed.
 2. Press the right button on the DPad. A capital 'T' will be displayed.
 3. Press the center button of the DPad to enter edit mode. The first letter in the message will be displayed.

 When in edit mode, the up and down buttons will cycle through characters. Minimatrix has a full character set, including numerous special characters and symbols. Pressing the left and right buttons will scroll through the letters in the message.

 The end of the message is denoted by a special symbol, shown as a box with a cross through it. This is always the last character of the message; if you want to make the message longer, press the up arrow until the desired character is shown. To end a message, press the down arrow until the box-with-cross symbol is shown.

 Exiting edit mode is the same as entering it:

 1. Press the 'Menu' button on the remote.
 2. Press left; a play symbol will be shown.
 3. Press the center button on the DPad to enter play mode.

## Programming from an Arduino

Minimatrix can also be reprogrammed from an Arduino or other microcontroller with an IR emitter. The protocol is quite straightforward, and uses the RC5 IR encoding system.

The protocol details are as follows. A sample Arduino sketch will be available very soon.

All programming codes have the field (second start) bit set to 0. The special commands are as follows:

 - 0x700 - Set data address. OR this with the 8-bit address into the data array to set the current address.
 - 0x600 - Write data. OR this with a data byte; stores the byte at the current address, then increments the address.

The data memory is structed as follows:

 - Flags - 1 byte. Bit 0 signifies display type; if unset, show marquee text; if set, show animation. All other bits are reserved
 - Delay - 1 byte. Delay in 10 millisecond increments between text columns or animation frames.
 - Spacing/framecount - In marquee mode, number of blank columns to insert between letters. In animation mode, number of animation frames to play (max 31)
 - Data - 248 bytes. In marquee mode, contains a null-terminated ASCII string to display. In animation mode, contains a series of 8 byte raw bitmap frames.
