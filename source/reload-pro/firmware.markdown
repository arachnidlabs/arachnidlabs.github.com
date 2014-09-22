---
layout: page
title: "Firmware updates"
date: 2014-09-22 15:03
comments: true
sharing: true
footer: true
---
The Re:load Pro supports user updatable firmware using a simple prodcedure
detailed below.

New firmware versions incorporate significant improvements and bugfixes, so it's
a very good idea to keep your firmware up to date.

# Download the firmware

The latest firmware can always be found on Github, [here](https://github.com/arachnidlabs/reload-pro/tree/master/firmware/release).
Download the most recent release by clicking on the .cyacd file, clicking 'raw',
then saving the resulting page.

# Installing the updater tool

To install the firmware updates, you'll need Python 2.7 and pip. Go to each of
those pages and follow the instructions to install first Python, then pip. Both
will work on Linux, OSX, and Windows.

Next, you'll need to install the 'cyflash' package. From a command line, run:

    python -m pip install cyflash

# Updating the firmware

Download the latest firmware as described above. Open a command line in the
directory the firmware is in.

Plug your Re:load Pro into your computer and identify what device it shows up as.
On linux and mac, it will show up as something like `/dev/tty.usbserial-somenumbers`.
On Windows, it will show up as a COM port, which you can identify using Device Manager.

Next, you need to put your Re:load Pro into upgrade mode. Press the encoder
button to enter the menu, then scroll down until you see "Upgrade Mode".
Highlight that and press the encoder button again.

Now that you have the firmware and know how your Re:load Pro has identified
itself to your OS, you can issue the update command:

    python -m cyflash --serial device "Reload Pro v1.5.cyacd"

Replace 'device' with the name of your USB device, and the filename with the
filename of the firmware version that you downloaded.

Cyflash will then upload the latest firmware, and your Re:load Pro will reboot.
It should show the new firmware version number on the boot screen.
Congratulations!
