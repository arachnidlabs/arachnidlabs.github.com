---
layout: page-side
title: "Fan Kit Assembly Instructions"
date: 2015-01-31 11:41
comments: true
sharing: true
footer: true
section: reload-pro
---
Congratulations on your new fan kit! The fan kit will expand your Re:load Pro's thermal dissipation capacity from 25 watts to approximately 50 watts. Installation is fairly straightforward, but it's important that you follow the instructions below in order to install it correctly.

Photographs and a video walkthrough are coming shortly.

# Attaching the fans

Take the four hexagonal spacers from the fan kit and screw them into the provided mounting holes on the back of the Re:load Pro. Tightening them to finger tightness is sufficient here.

Next, take the mounting plate with the fans attached, and place it on top of the spacers so the fans face towards the Re:load Pro heatsink. Use the four screws provided in the kit to attach the mounting plate to the spacers, and tighten with the included 2.5mm hex key.

# Disassembling the Re:load Pro

In order to attach the electronic components of the fan kit, you first need to disassemble the Re:load Pro.

Begin by taking the 0.9mm hex key included in the kit to undo the grub screw on the knob on the front of the Re:load Pro. Remove the knob and set it aside.

Use a phillips head screwdriver to remove the four screws from the front panel of the Re:load Pro. Carefully remove the front panel, taking care not to damage any of the connectors attached to it.

Use a fingernail or a flat head screwdriver to pull forward on the two tabs retaining the ribbon cable connector, and gently pull the ribbon cable connector free. Remove the three quick-connect connectors from the banana jacks. Set aside the front panel.

Now remove the four phillips head screws from the heatsink on the back of the Re:load Pro and set them aside. Carefully slide out the Re:load Pro PCB from the enclosure. You may want to leave the PCB partly in the enclosure so it remains supported from both ends for ease of installation. Treat the PCB and heatsink carefully; the heatsink is heavy, and is connected to the PCB only by the TO220 FET and its screw, which is easily bent.

# Installing the controller PCB

Take the fan controller PCB from the kit and the two rows of headers. Solder the headers onto the bottom of the fan controller PCB.

Carefully feed the four fan wires through the pre-drilled hole in the back of the Re:load Pro heatsink. Solder each fan to one of the fan connectors on the controller PCB.

Slot the fan controller PCB with headers into the expansion slot on the Re:load Pro. Orient the controller PCB so the thermistor is on the side closest to the heatsink. Turn over the Re:load Pro PCB and solder the fan controller PCB pins.

# Installing the thermistor

The thermistor allows the fan controller to sense the temperature of the heatsink and adjust the fan speed accordingly. It has a ring connector for easy connection to the FET. Carefully unscrew the screw connecting the FET to the heatsink. Place the ring connector on the outside of the FET (farthest from the heatsink and closest to the screw), and refasten the screw.

# Reassembling the Re:load Pro

Slide the Re:load Pro back into the enclosure and secure the four screws connecting the heatsink to the enclosure.

Reattach the three quick-connect terminals to the front panel's banana jacks. Take care to connect them the correct way around; the blue connector on the right side of the front panel connects to the leftmost internal terminal, while the red and black banana jacks connect to the remaining red and black wires.

Carefully slot the ribbon connector for the display back into the ribbon cable connector on the PCB and push it in gently. Use fingernails or a flat-head screwdriver to push the retaining clips in so it is held securely.

Fasten the front panel on to the unit with the four phillips head screws. Reattach the knob using the supplied 0.9mm hex key, taking care to ensure it is at least 0.5mm out from the front panel so you can still press the encoder button.

# Testing the fan kit

To test the fan kit, connect the Re:load Pro to a load. The fans will initially be off, but as the heatsink temperature increases, they will start spinning, ramping up to full speed as the heatsink temperature increases.
