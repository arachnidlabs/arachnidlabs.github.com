---
layout: disquspost
title: "The Loki Sound Plank"
date: 2013-01-25 20:18
comments: true
categories: loki
---

Time for a look at another one of the initial expansion planks for the Loki: The Sound plank.

![](https://lh3.googleusercontent.com/-97CVCWIpImk/UQLmDzpt3-I/AAAAAAAACa8/k8ygv6WcPkA/w388-h290-n-k/P1010190.JPG)

This plank takes advantage of the PSoC processor's built in analog functionality to offer audio input and output options few microcontroller platforms can offer - at least, not affordably! The plank supports two stereo line jacks - one for line level output, the second for either input or output - and a 1W mono amplifier that can drive small speakers. It also has an IR receiver module as an option.

The plank takes 6 IO lines: Two for each line jack, one for digital volume control of the amplifier, and one for the IR receiver. As you can see from the photo, it doesn't need very many components at all: a couple of film capacitors on each jack provide DC blocking, while the line in has protection diodes to protect the microcontroller against overvoltage. The amplifier is a single chip, the [TDA7052A](http://media.digikey.com/pdf/Data%20Sheets/NXP%20PDFs/TDA7052A_AT.pdf). It provides a 1 watt mono amplifier with an absolute minimum of external components. The speaker output is provided on a screw terminal at the bottom of the board.

All of this is complemented beautifully by the PSoC's built in analog features. Analog features vary from chip to chip in the PSoC 5 range, but all have at least one ADC and one DAC; most have 2 or more DACs. In addition, most of the line have configurable analog blocks, which can be configured to act as programmable gain amplifiers and as sample-and-hold units, amongst other functions. Finally, most of the line have dedicated opamps that are accessible both internally on external pins.

When placed at the bottom of the stack, the Sound Plank is configured such that the outputs of two of the dedicated opamps are connected to the line out jack. This means the Loki can provide a very low impedance line output, perfect for good quality audio. Even when elsewhere in the stack, or connected to a processor that does not have dedicated opamps, the built in analog hardware still provides a good analog path.

Once connected, the user has a lot of options. The configurable analog blocks can be set up as sample and hold devices, allowing a single DAC to drive multiple channels, or the outputs can be driven directly from multiple DACs. PWM can even be used, if desired - all configured inside the chip. On the input side, the ADC can be configured to sample alternately from each channel at anything up to 700k samples per second.

All up, the Audio Plank will provide an exceptionally flexible solution for simple audio input and output on the Loki.
