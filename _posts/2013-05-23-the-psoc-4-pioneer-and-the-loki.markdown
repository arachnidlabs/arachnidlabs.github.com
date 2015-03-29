---
layout: post
title: "The PSoC 4 Pioneer and the Loki"
date: 2013-05-23 22:41
comments: true
categories: loki
---

Recently, Cypress released a new range of processors, the [PSoC 4](http://www.cypress.com/?id=4749), and a new development kit for them, the [Pioneer](http://www.cypress.com/?rID=77780). The PSoC 4 is Cypress's new line of low power configurable microprocessors. They're based on the Arm Cortex M0 architecture, and have much more basic analog and digital capabilities than the 3 and 5, but still retain the PSoC's incredible reconfigurability. The pioneer is an Arduino clone based on the PSoC 4 processor; it's got onboard program and debug capabilities using an onboard PSoC 5(!) configured for interactive debugging. The whole board sells for $30 US.

A lot of people have been asking me about the Loki and my plans for it, especially in view of the release of the Pioneer. This is something I've been giving a lot of thought to. The Pioneer has a lot of advantages - it's made by Cypress, it's at a price point I can't match with the Loki, and it has onboard debugging, something I wasn't able to build into the Loki at a reasonable price. Whilst the Pioneer lacks Loki's very cool and flexible expansion system, it's able to take advantage of the entire ecosystem of existing Arduino shields out there.

Loki could still have a very viable niche as a 'big brother' to the Pioneer, since the PSoC 5 is so much more capable than the 4. I'm considering releasing it with this in mind - possibly redesigned to fit an Arduino Mega / Due form factor to take best advantage of the Arduino ecosystem and to provide a simple upgrade path. Sadly, this would mean giving up on the Loki's expansion system and the flexibility that grants.

In the short term, however, I've decided to put Loki on hold while I see how the Pioneer pans out, and to give me time to work on other projects. Keep an eye out for more progress in a little while. In the meantime, though, I do have another very cool project that uses the PSoC 5 in the pipeline - expect an announcement on that in the next few days!
