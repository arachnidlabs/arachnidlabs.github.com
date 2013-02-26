---
layout: post
title: "Labs update"
date: 2013-02-26 22:57
comments: true
categories: loki, reload, stencil8
---

Busy week this week, but little progress on things that seem important.

I bought a label printer to simplify the process of shipping out orders. Combined with Tindie's new CSV export option, I can now take a bunch of orders and automatically generate and print labels; the labels have a datamatrix in the corner that when scanned with my phone sends my browser to the relevant order page, so I can see what to pack and click 'shipped' when I'm done. Automation!

Incidentally, the label printer, a Brother QL-700, turns out to be really excellent. It uses label rolls in simple plastic caddies, which when inserted identify themselves to the printer by a simple punched-hole-and-switch system. Threading the labels into the printer is simplicity itself, making changing label types really easy. On top of that, it shows up as a standard printer. It also exposes a USB drive with a 'lite' version of their software, or you can download a much more capable package from Brother's site. To my great surprise, the label software is actually pretty decent, with sophisticated layout and mail-merge options built right in. The only major problem I've been able to identify so far is poor unicode support. I wrote a simple Python script to read and munge Tindie's CSV files into a format more suitable for a mail merge.

All the parts for the Re:load have arrived by now barring the PCBs and some extra thermal paste for the unexpected surge in orders. Both have shipped from China, and should be with me soon; once they arrive I can start shipping, at which point all my automation becomes truly useful. I spent a few hours on the weekend and Monday packing kits; I think it takes me a little over 1 minute per kit all up, including sticking labels and packing the bags with parts. I've done 100, and will do the rest soon. It's curiously calming, though also prone to giving one RSI.

I continue to fight with the CNC shop to get the rest of the tooling blocks done. They swear they'll call me tomorrow with good news. Fingers crossed.

I finally plugged in the Loki Sound Plank and gave it a simple test run. As hoped, it works perfectly, at least the bits I've tested so far. Ideas for a sample that shows it off are appreciated.
