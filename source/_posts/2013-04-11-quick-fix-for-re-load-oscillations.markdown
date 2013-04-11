---
layout: post
title: "Quick fix for Re:load oscillations"
date: 2013-04-11 21:35
comments: true
categories: reload
---
I've discovered a situation in which Re:load (both regular and epic) can generate ripple on the Device Under Test. This is only of concern to users who are using the Re:load to characterize power supplies - it won't affect you if you are generating a load for other purposes such as testing a device's output capability - and only occurs at voltages between 3 and 5 volts and currents over 1 amp.

Fortunately, this is easily remedied. Here's the procedure:

 1. Cut pin 2 of the MCP6002 opamp IC.
 2. Attach a 10k resistor between pin 2 of the MCP6002 opamp and the left hand leg of the 0.05 ohm shunt resistor.
 3. Attach a capacitor of between 10nF and 100nF (0.1uF) between legs 1 and 2 of the opamp.

Here's a photo of the completed modification:

<img src="https://lh5.googleusercontent.com/-j6B16yiQQWs/UWcgDNHhqtI/AAAAAAAADmc/C1PGuPOen5c/w584-h437-p-o/IMG_20130411_212436.jpg">

If you think this issue might affect you and you're not confident in making the modification yourself, please email me at <a href="mailto:nick@arachnidlabs.com">nick@arachnidlabs.com</a>, and we can arrange for return shipping, and I will perform the modification for you.

Version 2 of the Re:load, which I'm currently designing, will include the modification, as well as having several other improvements, such as a lower minimum voltage and a higher maximum voltage.
