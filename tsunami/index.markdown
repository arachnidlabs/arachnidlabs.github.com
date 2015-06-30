---
layout: page-side
title: "Tsunami"
date: 2015-06-30 07:00
sharing: true
footer: true
toc: true
section: tsunami
links:
    Buy Now: https://www.crowdsupply.com/arachnid-labs/tsunami
    Documentation: https://github.com/arachnidlabs/tsunami-arduino/wiki
    Schematics: https://github.com/arachnidlabs/tsunami
    Source: https://github.com/arachnidlabs/tsunami-arduino
---
**The Tsunami is available for preorder at Crowd Supply! [Get yours here](https://www.crowdsupply.com/arachnid-labs/tsunami)!**

The Tsunami is a powerful and flexible signal generator built on the Arduino platform. It’s the best way to get started experimenting with analog signals, and a great tool for a huge variety of tasks, too.

<img src="tsunami.jpg" width="500">

We’ve taken the versatile processor behind the Arduino Leonardo, and combined it with a Direct Digital Synthesis chip, which makes generating analog signals incredibly straightforward. Then, we’ve added on flexible input and output circuitry, and an easy to use software library, to make working with analog signals as easy as blinking an LED.

We’ve also tried to think of all the other tasks you might want to use the Tsunami for, from testing your audio equipment to communicating over the radio, and added the features you’ll need to get them done. Along with the board itself, we’ll be releasing a huge library of example code and ready-to-go applications that mean you don’t even have to know how to code in order to put the Tsunami to work.

# What can I do with the Tsunami?

Heaps! Here’s a few projects which could make use of the Tsunami:

 * Use it as a building block for a synthesizer
 * Measure unknown signals
 * Measure the response curve of your audio amplifier
 * Implement an APRS modem
 * Generate precise clocks for other devices
 * Make a digital theremin
 * Read and write data tapes from classic computers (Commodore, Atari, etc)
 * Test filters and reactive components (capacitors, inductors, and so forth)
 * Encode and decode your own data for audio transmission
 * Teach yourself about Direct Digital Synthesis
 * Teach yourself about AC and complex impedance
 * Make your own low frequency radio transmitter

 
 We’ve put a lot of effort into making the Tsunami as simple to use as possible, with an easy to use Arduino library that covers all the Tsunami’s functions. Generating a sine wave, for instance, is as simple as telling the Tsunami what frequency you want.

The included Arduino library covers all the Tsunami’s functionality, meaning you don’t have to worry about the low level details of how the hardware works unless you want to.

The Tsunami’s most straightforward functions are frequency generation and counting. The Tsunami uses a high accuracy 2.5PPM (that’s 0.00025%!) crystal, which makes it an excellent tool to generate highly precise frequencies, as well as to measure them with great accuracy. For comparison, your typical “high quality” crystal is between 8 and 25 times less accurate!

With its highly accurate crystal, you can use the Tsunami to generate signals - sine, triangle, and square waves - all the way from DC up to around 2 megahertz. A versatile analog frontend allows you to adjust amplitude from 0 to 6 volts peak to peak, and DC offset by up to 2 volts either side of ground.

Likewise, the Tsunami can be used to measure signals. The processor used in Arduinos has a good quality ADC, but it’s slow, being limited to 15k samples per second. We’ve bypassed that limitation, equipping the Tsunami with a high speed comparator, allowing it to measure frequency, a peak detector, allowing it to measure signal amplitude, and a phase detector allowing it to, er, detect phase. All of these facilities work up to nearly 8 megahertz.

By combining these two building blocks together, you can use the Tsunami to do even more. For instance, by connecting the output of the Tsunami to an analog filter or an audio amplifier, and using the Tsunami’s input to measure what comes out, you can measure how it responds at different frequencies. The phase detector in the Tsunami lets you detect the phase delay, too, allowing you to construct bode plots. The same basic technique can be used to measure unknown inductors, capacitors, or networks of them.

That’s not all you can do with the Tsunami, though. The DDS has built in support for phase and frequency modulation, and the Tsunami adds on support for amplitude modulation too. With just a few lines of code you can take digital data and modulate it onto an audio or RF signal at any frequency the Tsunami supports, and using the Tsunami’s input features, you can demodulate data, too.

All of this is only a taste of the things you can do with the Tsunami. If you’ve got your own plans, we’d love to hear about them in the comments section!

# What’s this about DDS?
DDS - the process of generating waveforms directly from digital data - is a fascinating piece of technology, and it’s increasingly used in applications such as radio communications, test equipment, proximity and motion detection, and in audio synthesizers. Unfortunately, many DDS chips come in difficult to solder packages, and have complex interfaces. We’ve solved both of these issues by designing an affordable development board with a DDS chip onboard, and by providing excellent libraries and comprehensive sample applications you can use in the familiar Arduino environment.

<img src="dds.jpg">

DDS works by having a counter - the ‘phase accumulator’ in the diagram above - driven by a high speed clock, which counts up at a rate determined by a configuration value. The output of that value gets fed into a module that translates the linear ramp up of values into a sine wave, typically by using a lookup table. Then, the output of that is fed into a DAC, producing an analog waveform on the output.

If you’re less interested in DDS itself, and more interested in what you can do with it, the Tsunami makes an excellent signal generator and frequency counter. It can be used for a variety of tasks including measuring capacitors and inductors, complex impedance measurement, qualification of analog filters, and modulating and demodulating data. By the time we’re ready to ship boards to backers, we’ll have fully functional for code for many these applications that you can just load and go. We’ve tried to think through likely uses for the Tsunami, and make sure it has the hardware and peripherals you’ll need to be able to execute those tasks with ease.

# Specifications

 * Generate signals from DC to 2MHz.
 * Supports sine, triangle, and square wave signals.
 * Supports frequency, phase, and amplitude modulation.
 * Adjustable signal amplitude up to 6 volts peak-peak (except square-wave).
 * Can drive a 50 ohm load.
 * Adjustable DC offset from -2V to +2V (except square-wave)
 * Programmable over USB, and USB powered.
 * Arduino Leonardo compatible ATMega32U4 microcontroller with 32KB flash and 2.5KB RAM.
 * 2.5PPM Temperature Controlled Crystal Oscillator (TCXO).
 * AD9838 Direct Digital Synthesis chip with 10 bit DAC.
 * Expansion headers onboard for easy access to I2C and UART interfaces.
