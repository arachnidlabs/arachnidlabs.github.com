---
layout: post
title: "Freeloader"
date: 2013-02-25 20:49
comments: true
categories: freeloader
---

When I chose Cypress's PSoC processors as the platform for Loki, one of my concerns was to make sure that Loki's hardware and software design were as open and free as possible. Requiring binary distributions or closed licenses wasn't acceptable to me, as I suspect it wouldn't be to a lot of the maker community. Mostly, this is up to me, but in some areas it was a little tougher.

Cypress has an excellent IDE for the PSoC 3 and 5, PSoC creator. It's generally very nice to work with, and it's free - but free as in beer, not free as in freedom. Again, this isn't normally an issue - they impose no restrictions on how you can redistribute source you author with the tools - but the license that's applied to the API and components that come with PSoC creator does not permit redistribution of source, only of compiled binaries. I wanted to use the built in PSoC bootloader component for Loki, and I wanted to make changes to it, but I couldn't do so as long as it was licensed in a way that meant I would not be able to release the source for my amendments.

Before I went down the long road of writing my own bootloader from scratch, I decided to get in touch with Cypress to see if they would be prepared to do anything. I dropped them a line, and was very pleasantly surprised to hear back shortly afterwards from someone on Cypress's legal team. We had a very cordial discussion where he made sure he understood my needs and requirements, went off to consult with the engineers, then came back to say that yes, they would be happy to relicense the bootloader component under an OSS license; would the BSD license do? Yes, it would do very nicely. The only additional requirement they added is that it not be called "Bootloader", so as to prevent confusion with the official component.

As a result, I'm delighted to present [Freeloader](http://github.com/arachnidlabs/freeloader/), an OSS fork of the official Cypress bootloader component, relicensed under the BSD license. I'm certain this will be of great interest and use to the maker community and anyone building OSS projects based on the PSoC; I hope we can build a community to improve and enhance the bootloader beyond the excellent starting point Cypress has provided.

In my ideal world, Cypress would have already licensed their entire SDK under the BSD license. But I'm seriously impressed with their response to my request, and what it implies of their engineering and management culture. I think it bodes well for Cypress's interactions with the OSS, OSHW and hobbyist community in future that they were prepared to listen and engage with someone who wouldn't even register as a blip on most company's radars.

You can find the complete source for Freeloader [here](http://github.com/arachnidlabs/freeloader/). If you have any interest in the PSoC and devices based off it, I'd encourage you to check it out, use it, and improve on it.
