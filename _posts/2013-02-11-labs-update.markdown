---
layout: disquspost
title: "Labs Update"
date: 2013-02-11 19:42
comments: true
categories: loki, reload
---

The weekend was spent in various Loki and Arachnid Labs related activities. The most boring (but necessary) of these was finding and setting up an accounting package of some sort to keep track of where all the money comes from and goes to (mostly goes to, so far).

I redesigned the layout of the EEPROMs onboad each Loki plank to use a lot less space, opening up the possibility of switching from discrete EEPROMs and XOR gates to an integrated solution such as an ATTiny45 MCU. This won't be any cheaper - it may, in fact, be marginally more expensive - but it will make every plank's BoM one part shorter, and reduce layout size. The programmer tool has been updated to read and write the new EEPROM format.

One change in the new format is that instead of using (long) GUIDs to indicate a plank's identity, I've switched to a system similar to USB, with "Maker IDs" and "Plank IDs" of two bytes each. This requies centralized allocation of IDs, but unlike USB-IF, I don't intend to charge people for the privelige; they'll be available if and when needed. I'll probably also allocate a generic Maker ID for anyone who doesn't want to register for their own for whatever reason.

Currently, these IDs serve two purposes. The most significant is that they'll allow a future version of the Loki bootloader to identify what planks are attached and compare that to the ones that were attached when the program was bootloaded. A user configurable option will be provided to enable the board to refuse to boot if the configuration does not match. Sophisticated programs may also choose to use the IDs in a similar way to USB, allowing them to be reconfigured by plugging in new boards.

The second purpose is for convenience; a URL can be generated from the maker ID and plank ID to an as-yet-unwritten registry, which will redirect to the plank creator's page, with documentation.

I also finished converting the plank specification from a Google Doc to a page; it can be found [here](/loki/planks.html), and that URL will be its new home from now on; the google doc will be obsoleted. I've updated that document with details of the EEPROM layout. I'm still working on the Loki reference manual.

Some time over the weekend was spent dealing with Re:load logistics. I've ordered the usuall dull items like postage bags and labels, as well as a couple of other shinier things I have planned. Since the number preordered is so much higher than I expected, I've been looking at other suppliers and asking for quotes. One surprise was that Farnell no longer have enough of the larger heatsink in stock to satisfy my preorders; the good news is that I found an alternate supplier who has a compatible heatsink with even better thermal performance (2.6C/W vs the current 3.3C/W), so all Epic Re:load purchasers will now be getting a free upgrade to an improved heatsink. I also ordered a truly excessive 1000 packets of thermal paste from a supplier in China. I chose express shipping; hopefully the Chinese New Year won't delay them too much.

On Sunday I took the plunge an ordered an SMD reflow oven off EBay; it'll be arriving some time this week. Even though the Re:load has only one SMD part to solder before sending out the kit, this still ought to speed things up a bit.

Last but not least I sent the updated Loki board off to [Hackvana](http://www.hackvana.com/) for fabrication, along with a couple of new prototype plank designs: the constant current LED plank you've already seen, and a new one that's yet to be announced.
