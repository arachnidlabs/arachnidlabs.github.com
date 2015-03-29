---
layout: post
title: "Review: Headphone Amplifier Kit from diyourfaceoff"
date: 2013-05-25 18:11
comments: true
categories: tindie review
---

Recently, [diyourfaceoff](https://www.tindie.com/stores/diyourfaceoff/), a fellow Tindie seller, listed a [headphone amplifier kit](https://www.tindie.com/products/diyourfaceoff/headphone-amplifier-kit/) on Tindie. As an owner of a moderately nice pair of headphones, I thought it'd be interesting to pick one up.

After pledging, however, and having done a lot more research about headphone amp design, it became apparent that maybe the ultra-simple CMOY design that this kit is based on wasn't entirely up to scratch. As part of my research, I got turned on to another open source amp design, the [Objective2 headphone amplifier](http://nwavguy.blogspot.co.uk/2011/07/o2-headphone-amp.html). There's a pile of resources at that link, including design discussions about the O2 design and other common designs like the CMOY - well worth a look. I particularly like NwAvGuy's emphasis on objective measurements - no fuzzy audiophile nonsense here. While waiting for diyourfaceoff's kit to arrive, I ordered and built an O2 kit from [Head 'n' HiFi](http://www.headnhifi.com/o2-kit-full). When my CMOY kit arrived too, it seemed like it was about time to do a review and comparison.

<!-- more -->

# Construction

First off, impressions of the kit. It arrived in a bubble bag, with most of the components in a ringgrip bag inside. It was satisfactorially packaged, but I was a little unimpressed that everything wasn't in a single bag - the larger parts were simply loose in the shipment packagaing. A minor issue. Included in the package were all the parts, the PCB - still with mousebite tabs hanging off it - an A4 sheet with a BoM, and a length of solder, which was a nice touch. The volume control is clearly a high quality part, and the battery snap was nice and solid; the headphone jacks seemed a little flimsy.

Assembling the kit is fairly straightforward following the [provided build instructions](http://www.diyourfaceoff.com/cmoy), though I found the suggested assembly order a bit odd and went with my usual practice of starting with the lowest profile parts and working my way up. Another nice touch was the labelling of the resistors: all of them had values written on the paper tape, which saved a significant amount of time. One minor issue is that the holes for the resistors are a little too close for the resistors provided, meaning they tend to stick up a bit off the board.

More significantly, some of the footprints were odd. The film capacitors have polarity indicators marked even though they're not polar; the electrolytics had footprints marked as long oblongs instead of round, and the footprint for the LED shows a flat but no anode indicator, while the provided LED lacks a flat on one side.

For practical use, I forsee a significant problem: there's no enclosure, nor does the PCB appear to be designed to fit in a standard one. Having a bare circuit board on one's desk seems less than ideal.

# Design

Sadly, diyourfaceoff hasn't published the schematics or design files for his implementation of the CMOY design - a significant omission given the open source nature of the design. There are a lot of CMOY variants out there, too. Looking at the components, however, we can learn something about the design.

First off, there's no evidence of a dedicated rail splitter of any sort, and the 2 channel opamp is entirely occupied with processing the 2 channel audio. With no bipolar power supply, a virtual ground is mandatory for an amp like this - how is it being generated? A little Googling on CMOY designs and some examination of the PCB reveals it: Using a resistive divider! Two 4.7k resistors between 9v and ground create a virtual ground reference point, which is buffered with large 220uF electrolytic capacitors. This is, to say the least, far from ideal. Any current through ground will tend to push the voltage away from 1/2 the battery voltage, and this will have a number of negative effects on the amp, as we'll soon see.

# Testing

First off, basic tests. You'll be pleased to know neither amp will destroy your headphones: both have negligible DC bias on their outputs.

My approach for more sophisticated testing was simple: Connect both amps to a signal source - in this case, my phone running a tone generator - run them on battery power, and use my oscilloscope to measure the input and output signals at a number of frequencies and with both sine and square waves. I started off with the O2 amp; here it is handling a 900hz sine wave:

![](http://i.imgur.com/owiLZQF.png)

In all these images, the top signal is the output waveform, the bottom signal is the input waveform, and the middle signal is the arithmetic difference between the two. In all cases the volume has been adjusted for unity gain, so ideally the middle signal should be effectively flat at 0. As you can see, my test signal isn't entirely clean, but it ought to suffice for the test. Here, the O2 amp is faithfully reproducing the input, and only some low level noise shows up on the difference.

Here's the O2 handling 300hz and 100hz sine waves, respectively:

![](http://i.imgur.com/FD5e6Ox.png) ![](http://i.imgur.com/0nug4Sb.png)

Again, it does a champion job, faithfully reproducing the input waveforms. Square waves are a little trickier, but it manages those too:

![](http://i.imgur.com/jNhsGHD.png) ![](http://i.imgur.com/UWRI2Pv.png) ![](http://i.imgur.com/aW4ly7T.png)

Depicted above are 900hz, 300hz and 100hz square waves, respectively. Again, the input is more or less indistinguishable from the output.

Let's try out the CMOY design. I've already predicted the poor virtual ground will introduce issues; am I right?

![](http://i.imgur.com/OXSGF5m.png)

That's the CMOY handling a 900hz sine wave. It's fairly faithful, but notice a little bit of ripple in the output waveform. Let's see how it handles lower frequencies, 300hz and 100hz:

![](http://i.imgur.com/LHDDXpR.png) ![](http://i.imgur.com/felQJkf.png)

Hm, that difference signal is getting significantly bigger. As predicted, the problem here is the virtual ground: lower frequency signals are slow enough to significantly charge or discharge the capacitors creating the reference voltage, and that introduces phase shift in the output signal. The lower the frequency, the worse the effect.

If that's right, then this problem should be much more noticeable with a square wave signal, and indeed it is. Here's the CMOY handling 900hz, 300hz and 100hz square waves:

![](http://i.imgur.com/rEX8o9J.png) ![](http://i.imgur.com/JGEgYhu.png) ![](http://i.imgur.com/UWUyooX.png)

By the time we get down to 100hz, the effects are impossible to ignore. Our square waves no longer look very square - they're well on their way to being triangle waves! This effect gets worse with volume, of course - the higher you turn up the volume, the more power flows through the virtual ground, and the larger the deviation induced.

# Conclusion

While a simple it, and reasonably well presented, diyourfaceoff's headphone amplifier has a few issues - and one fatal flaw. While it uses a high quality opamp, that becomes a moot point due to the poor design of its power supply. Unfortunately, I can't recommend it to anyone as an amplifier solution - you'd be better off plugging your headphones in direct, or splashing out a bit more and getting the O2.

I also feel like the lack of schematics and design files are worth a mention. The CMOY design on which the amp is based on is open source; it would be only fair to release the design files likewise.
