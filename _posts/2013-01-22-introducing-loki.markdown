---
layout: disquspost
title: "Introducing Loki"
date: 2013-01-22 18:45
comments: true
categories: loki
---
<img src="/images/loki.svg" style="width: 100px;" />    Time to unveil Arachnid Labs' first project!

Loki is a microcontroller development board based on Cypress's [PSoC 5 processor](http://www.cypress.com/?id=2233). What makes the Loki unique is the combination of this very capable and unusual processor with a truly novel design for the expansion system. The PSoC is a uniquely capable processor, consisting of an Arm M3 core with a flexible frontend that incorporates "universal digital blocks", which can be configured to implement almost any imaginable peripheral, coupled with a flexible routing system that lets you route any IO pin to any function. Loki builds on this, with a unique stacking expansion system that ensures that you can stack any expansion boards - or 'planks', in Loki terminology - up to the limit of the available IOs without having to worry about pin conflicts.

![](https://lh5.googleusercontent.com/-yPN_q7JmINg/UQLmIGT-7lI/AAAAAAAACbE/xb4uWjqj3lM/w396-h298-n-k/P1010194.JPG)

The end result of all this is a microcontroller platform that leaps past past your average Arduino clone, allowing you to create more interesting and involved projects, while spending less time messing around with protoboards and bitbashing, and more time on the parts of your project that matter to you. Cypress's [PSoC Creator](http://www.cypress.com/?id=2494) IDE provides a powerful environment in which to develop your code, with high level easy to understand APIs, and a graphical digital design tool for configuring the programmable logic components, while the flexible expansion system lets you combine any expansion planks you need to get your project working. The PSoCs configurability means less glue logic and fewer external components, too, which will mean cheaper and more flexible expansion planks than other systems. For example, the analog audio expansion plank provides stereo line in and out with only a few passive components, relying on the PSoC's built in analog functionality to do the heavy lifting.

In the next few days we'll go into more detail about the Loki architecture and the PSoC, but today I'd like to cover the basic specs and my vision for the system.

<!-- more -->

## Specifications ##

The PSoC 5 moniker covers a range of processors, with speeds from 33 to 66MHz, a wide variety of RAM and Flash sizes, and different degrees of digital and analog flexibility. I haven't settled on a specific processor for the final units yet; it's possible Loki will be available in two versions, a cheaper 'Lite' and a more capable 'Pro' version. Regardless, many things won't change:

 * 32 GPIO pins, each of which can be connected to any digital or analog peripheral the processor is capable of synthesizing.
 * Native Full-speed USB 2.0 support, which can be configured to act as any endpoint type.
 * USB bootloader - the development board is all you need to get started.
 * Powered over USB or with 6-20V DC via a barrel jack.
 * Onboard 5v switching regulator and 3.3v linear regulator, available to expansion planks.
 * Onboard Micro-SD card slot, for massive onboard storage; supported natively in the PSoC creator software.
 * Dedicated I2C bus, used for configuration and available to expansion planks.

And a few highlights of the PSoC processor that powers it all:

 * Up to 66MHz clock speed
 * Flexible clocking system can generate a wide variety of clock signals using the external 24MHz Xtal, the onboard main oscillator, low speed oscillator, and an onboard PLL. Clocks can be further divided to generate almost any imaginable frequency for use by the configurable logic blocks.
 * Up to 24 universal digital blocks, each consisting of two CPLDs and a sophisticated ALU. Together these can be used to implement almost any conceivable digital peripheral, with no involvement from the CPU. Multiple blocks can be chained together to create larger peripherals.
 * Versatile DMA controller allows data transfers between logic blocks, main memory, and the CPU, without extra CPU overhead.
 * Up to 256KB flash and up to 64KB onboard SRAM.
 * Built in capacitative touch sense support.
 * All GPIOs are configurable as open drain high/low, pull-up, pull-down, Hi-Z, or strong output.
 * Built in timer/counter/PWM blocks allow common functions to be implemented while preserving UDB resources.
 * Built in ADCs and DACs.
 * Up to 4 built in configurable analog blocks, configurable as Programmable Gain Amplifier, Transimpedance Amplifier, mixer, sample and hold, and more.
 
As you can see, all of this adds up to a highly versatile and powerful system, without having the steep learning curve that solutions like FPGAs can have. All your familiar microcontroller tricks still work here, but with an extra boost added by the flexibility of being able to reconfigure your peripherals to suit the task at hand.
 
## Roadmap ##
 
I'm designing and building the Loki because I think there's the potential here for something genuinely new and innovative, and something that contributes back to the maker community. I think Loki will offer new opportunities to people embarking on challenging microcontroller projects, and I hope we'll see a thriving ecosystem of clones, expansion planks, tools and projects based on it. With that in mind, I'm releasing all my code and all the designs under OSS and OSHW licenses, and I encourage people to take those designs and run with them. As Arduino has amply demonstrated, an open community benefits everyone. 

Loki's targeted primarily at people with prior experience with microcontrollers or at least programming, but I'm determined to make the getting started experience first class for novice and veteran alike. Cypress already provides a rich set of appnotes, articles and videos targeted at PSoC development; I'll be adding to that with informative blog posts, instructional videos and demo projects, along with thorough documentation of the Loki platform itself. I'll also be blogging my progress as I go.

A system like this lives or dies on the ecosystem that springs up around it, and I'm likewise determined to support that community in every way possible. In the coming weeks I'll be setting up mailing lists and other ways for people to engage with me and each other over the platform. Anyone who wants to get started early with plank development will have my full support: I'll even offer to manufacture the PCBs for you and supply you with some of the parts you need to get started.

Finally, the platform itself will only get better with user feedback. I want to hear comments and criticism about every part of the platform. The best time to change things is now, before release, making Loki a better tool for everyone. With that in mind, I will shortly be putting together several more alpha units along with some of the initial planks, and sending them out to testers for evaluation and feedback. If you think that could be you, keep an eye out for the call for testers soon.