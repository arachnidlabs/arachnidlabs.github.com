---
layout: disquspost
title: "Using a solder paste dispenser with compressed air tanks"
date: 2013-05-27 13:00
comments: true
categories: paste-dispenser
---

I recently decided to invest in a Solder Paste Dispenser for the lab. The unit I settled on was the same one as [Dangerous Prototypes bought](http://dangerousprototypes.com/forum/viewtopic.php?f=68&t=5121), the PE-983A. I got mine from [this AliExpress listing](http://www.aliexpress.com/item/Hot-sale-Auto-Glue-Dispenser-Solder-Paste-Liquid-Controller-Dropper-YDL-983A-Dispensing-system/757892187.html).

One thing that's dissuaded me from buying a solder paste dispenser for so long is that I'm really not keen on a loud and bulky compressor in my workshop area, and I don't want to spend several times the cost of the dispenser on a small and/or quiet compressor. I'd considered using an airbrush compressor, since they tend to be both quiet and small, but there was scant information on whether or not the smaller working pressure of such a compressor - typically 3 to 4 bar - would be sufficient for solder paste dispensing.

Another idea that occurred to me was using tanks of compressed gas. In theory, they ought to last a very long time, since the dispenser uses very little, and working pressure shouldn't be an issue. There's very little information out there on what sort of connection the dispenser uses for compressed air, though, and if you're new to compressed air fittings like me, there's a bewildering plethora of options out there. I decided to take the plunge and see what I could figure out anyway, with the help of fellow [London Hackspace](http://londonk.hackspace.org.uk/) member artag, to whom I am eternally grateful.

<!-- more -->

After ordering the solder paste dispenser, I picked up [this tank of CO2](http://www.halfords.com/webapp/wcs/stores/servlet/product_storeId_10001_catalogId_10151_productId_217424_langId_-1_categoryId_255210), intended for use as welding gas from Halfords for £16.99, along with [this matching regulator](http://www.halfords.com/webapp/wcs/stores/servlet/product_storeId_10001_catalogId_10151_productId_207319_langId_-1_categoryId_255210) for £17.99. It's not documented there (a common theme with compressed air stuff, it seems), but the regulator has a 4mm pushfit fitting as its output.

![](https://lh3.googleusercontent.com/q0dNB6oQRioeFE_0rf0aqS4HvBkLovcSPHY1W2B3Ovk=w305-h228-p-no)

When the paste dispenser arrived, it turned out to have a 6mm pushfit fitting. (I think this makes me the first person to document this important bit of information anywhere on the web):

![](https://lh6.googleusercontent.com/JTiTEcLbn1hVAcT0iO4wChQTT2Rir7WqW3AzYlMrueU=w173-h228-p-no)

A short trip to EBay later, I had a length of 4mm pushfit tubing, and a 4mm to 6mm pushfit adapter:

![](https://lh6.googleusercontent.com/3UPUxgQ1bBXfURimvkwULuk-FjyerDa9tq3iogEcUIo=w305-h228-p-no)

And we're all go! Opening the valve, we get about 80PSI, plenty for dispensing solder paste with:

![](https://lh6.googleusercontent.com/dPY4NTDbKcmyw4vgZAlU2TdddvN1StJCZ2Cfespf8QQ=w306-h228-p-no)

Some further notes for those of you thinking of doing the same thing:

First off, the regulator's 4mm pushfit fitting is in a 1/8" BSP female thread. You could unscrew this and replace it with a 6mm fitting and skip the adapter; I tried this, but the regulator sometimes refuses to dispense gas, and I couldn't get it working, so I went with the safe option.

Second, I've tried closing the regulator a bit to test the dispenser at 40-50PSI, approximately the working pressure of an airbrush compressor. It works absolutely fine, dispensing only a little slower than it does at 80PSI. When this tank runs out, I think I'll get a cheap compressor instead of a new tank. Airbrush compressors typically have 1/8" male BSP fittings, and you can get adaptors from that to 6mm pushfit on EBay easily. Anyone planning to go the same route should definitely get a compressor with an air tank - that's pretty much mandatory for this application.

If you try this out yourself - either tank air or the compressor option - I'd love to hear about your experiences.
