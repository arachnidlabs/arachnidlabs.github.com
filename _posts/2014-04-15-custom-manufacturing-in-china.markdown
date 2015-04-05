---
layout: disquspost
title: "Custom manufacturing in China"
date: 2014-04-15 19:31
comments: true
categories: reload-pro china
---

One of the primary requirements for the [Re:Load Pro](https://www.kickstarter.com/projects/nickjohnson/re-load-pro-a-dc-active-load) was an enclosure and heatsink. The two need to integrate well - ideally with the heatsink taking the part of one end-panel - and the heatsink needs to be sufficiently large for the heat dissipation requirements of the Re:load Pro. After much searching, I came to the reluctant conclusion that such an enclosure doesn't presently exist, and that my only option was to get the enclosure, the heatsink, or both custom manufactured.

I've sourced parts from Chinese manufacturers before, including getting parts, such as the [LED matrices](https://www.tindie.com/products/arachnidlabs/8x8-pixel-square-pixel-led-matrix-yellow-green/) for the [Minishift](https://www.tindie.com/products/arachnidlabs/minishift/) and [Minimatrix](https://www.tindie.com/products/arachnidlabs/minimatrix/) made to order, but sourcing something with high setup costs, such as a custom extrusion, was a new experience.

Step one was to design a part and generate a suitable manufacturing drawing from which to quote. I took the dimensions of an existing heatsink, along with [various design guides](http://www.aavid.com/product-group/extrusions-na/custom) and produced this design:

<img src="/images/heatsink_drawing.png" width="500">

I found some suppliers on aliexpress who seemed to specialise in heatsink extrusions, and shopped it around to them. I got quotes back from a number of suppliers, with a wide range of prices. Tooling/mold fees ranged from $500USD to $1,300, while per-unit prices ranged from $1.85 each to $3.50, and they all had minimum orders around 500 pieces. Most were willing to negotiate down on the MOQ in order to get a sale, but some additionally had an additional setup fee if you ordered less than a certain weight of aluminium.

I ended up picking a supplier towards the lower end of the price range, though not the absolute cheapest, with a tooling cost of $600, and a per-unit cost of $2.30, and authorising them to go ahead and produce the mould. This was an occasion for some paranoia, since unlike the CNC and 3d printing processes we're all used to being a bit blase with, any screwups here would necessitate a new mould, and another $600 tooling fee.

The breakdown of the per-unit costs were:

 * $0.85 material cost
 * $0.09 'blanking' cost
 * $1 For post-extrusion CNC
 * $0.17 to anodise each unit black
 * $0.17 packaging

Tooling took some time: nearly a month, though that was interrupted by Chinese New Year, which extended things somewhat. The tooling fee includes production of 3 sample units, which arrived a week later. I couldn't be happier with the quality of the extrusion, machining, and finish:

<img src="/images/heatsink_photo.jpg" width="500">

These are the exact extrusions you'll get as part of your enclosure if you [back the Re:load Pro](https://www.kickstarter.com/projects/nickjohnson/re-load-pro-a-dc-active-load).

Although one data point isn't a lot to work from, I've found the whole experience to be surprisingly straightforward and hassle-free so far, though I'll report back when I've ordered the final extrusions for the production run. A few things to bear in mind when considering ordering custom work from China yourself:

 * Get multiple quotes from different manufacturers. The range in both setup and per-unit costs was enormous across different suppliers.
 * Ask for photos and drawings of other work they've done. I avoided the cheapest supplier because they seemed suspiciously cheap, and didn't have much evidence of other high quality work.
 * Ask for a drawing of their own or other evidence they've understood your technical drawings correctly and will produce them to spec. The manufacturer I used included a drawing of the extrusion with their quote.
 * Make sure you get samples to test the production quality, fit and finish before placing a full scale order.
 * Make sure you fully understand the MOQ and any setup fees before ordering anything.

Have you had custom work done in China? What was your experience with it like?
