---
layout: page-side
title: "Minishift"
date: 2014-03-15 17:55
comments: true
sharing: true
footer: true
toc: true
section: minishift
---
**Minishift is now available for preorder! Get yours [here](https://www.tindie.com/products/arachnidlabs/minishift/)!**

<iframe width="560" height="315" src="//www.youtube.com/embed/DGM5Mnr_MeA?rel=0" frameborder="0" allowfullscreen></iframe>

The Minishift is a compact and affordable 8x8 LED matrix display that speaks SPI, and can be driven from any microcontroller platform, or with an optional interface board, over USB.

<img src="front.png" width="400">

Each Minishift module operates independently, and they chain together to form larger displays, limited only by the amount of power you can supply them. They speak a trivial SPI protocol, with each display acting like an 8 byte shift register, making it extremely easy to work with them. Sample code for the Arduino will be available before preorders ship.

<img src="back.png" width="400">

An optional USB-SPI interface is available, which makes it easy to drive a series of Minishifts from your computer. Python libraries and sample code, as well as a display driver daemon, will also be available soon. The USB interface can drive 8-9 Minishifts fully lit, or more if you will only be displaying text or other graphics that don't light all the LEDs at once.

<img src="usb-interface.png" width="400">

Minishifts and the USB interface are sold as kits, with all surface mount parts populated, leaving only the connectors and LED matrix to solder yourself. Full instructions are provided.

# Specifications
## Minishift

 * 64 LEDs in an 8x8 matrix
 * Operates at 5v or 3.3v (5v recommended for maximum brightness)
 * Integrated controller acts like an SPI shift register
 * Chainable to create larger displays
 * <5mA idle current usage each, rising to approximately 60mA with all LEDs on
 * Integrated mounting holes allow attachment to enclosures, mounting plates, etc

## USB Interface

 * Uses the MCP2210 USB-SPI bridge
 * Provides a HID interface; no OS drivers required
 * Python libraries available soon, functional on OSX, Linux and Windows
 * Supplies up to 500mA to Minishifts (8-9 fully illuminated, or more partially illuminated)

# Source

Full source code and schematics for the Minishift and related libraries are available [on GitHub](https://github.com/arachnidlabs/minishift/).
