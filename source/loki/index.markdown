---
layout: page
title: "Loki"
date: 2013-02-07 22:06
comments: true
sharing: true
footer: true
---
Loki is a microcontroller development board based on Cypress's [PSoC 5 processor](http://www.cypress.com/?id=2233). What makes the Loki unique is the combination of this very capable and unusual processor with a truly novel design for the expansion system. The PSoC is a uniquely capable processor, consisting of an Arm M3 core with a flexible frontend that incorporates "universal digital blocks", which can be configured to implement almost any imaginable peripheral, coupled with a flexible routing system that lets you route any IO pin to any function. Loki builds on this, with a unique stacking expansion system that ensures that you can stack any expansion boards - or 'planks', in Loki terminology - up to the limit of the available IOs without having to worry about pin conflicts.

![](https://lh5.googleusercontent.com/-yPN_q7JmINg/UQLmIGT-7lI/AAAAAAAACbE/xb4uWjqj3lM/w396-h298-n-k/P1010194.JPG)

The end result of all this is a microcontroller platform that leaps past past your average Arduino clone, allowing you to create more interesting and involved projects, while spending less time messing around with protoboards and bitbashing, and more time on the parts of your project that matter to you. Cypress's [PSoC Creator](http://www.cypress.com/?id=2494) IDE provides a powerful environment in which to develop your code, with high level easy to understand APIs, and a graphical digital design tool for configuring the programmable logic components, while the flexible expansion system lets you combine any expansion planks you need to get your project working. The PSoCs configurability means less glue logic and fewer external components, too, which will mean cheaper and more flexible expansion planks than other systems. For example, the analog audio expansion plank provides stereo line in and out with only a few passive components, relying on the PSoC's built in analog functionality to do the heavy lifting.

If you're interested in contributing to the Loki platform by being an alpha tester, writing code, or designing your own planks, please get in touch by [emailing Nick](mailto:nick@arachnidlabs.com). We're doing everything we can to make Loki a success, and we're looking for collaborators!

== Documentation

[Loki Plank Specification](planks.html)

For more (informal) documentation, you should read [these blog posts about Loki](/blog/categories/loki/).
