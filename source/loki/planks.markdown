---
layout: page
title: "Loki Plank Specification"
date: 2013-02-09 17:41
comments: true
sharing: true
footer: true
---

## <a id="intro">Introduction</a>

The Loki development board provides facilities for connecting a wide variety of expansion boards to augment its built in capabilities. This specification describes the physical and electrical characteristics required of such an expansion, known as a Plank.

Loki's expansion system works by the provision of a number of general purpose IO pins (GPIO), and, on a separate header, power and ground rails, an I2C bus, and address pins.

The expansion system uses a stacking system similar to that used by other development boards. Unlike those boards, the Loki uses surface mount headers to allow reassignment of pins, solving the issue of pin conflicts between shields. For more details, see the section titled "[Electrical Connections - GPIO](#gpio)".

Every plank is either a standard plank, in which case more planks may be stacked on top of it, or a top plank, in which case no other planks can be stacked on top of it. A plank SHOULD be designed as a standard plank unless it is impractical to do otherwise - for instance, because it includes controls or displays that require physical access from above.

## <a id="formfactor">Form Factor</a>

The Loki board and expansion planks fit the Dangerous Prototypes "Sick of Beige" 8049 form factor. This dimensional drawing specifies the relevant measurements of the Loki and its connectors and mounting holes. All dimensions are in millimeters.

![Loki Plank Dimensional Drawing](/images/Loki Plank Dimensional Drawing.png)

A plank MAY be shorter than depicted, as long as all connectors are still in place. A plank MAY extend beyond the marked dimensions in any direction.

A plank SHOULD include mounting holes in the same positions as those in the drawing, provided it extends that far.

An Eagle library containing the footprint for a plank, and boards and schematics with partially pre-routed configurations are provided [here](https://github.com/arachnidlabs/loki/tree/master/schematics/resources) for the convenience of implementers.

## <a id="powerconf">Electrical Connections - power and configuration</a>

A standard 10 pin, 0.1" spaced surface mount pin header MUST be attached to the bottom of the plank in the position indicated in the bottom right of the dimensional drawing. A corresponding receptacle MUST be placed on the top of the plank, unless the plank is a 'top plank'.

From left to right, the pins are:
<table>
<tr><th>VIN</th><td>Input voltage</td></tr>
<tr><th>+5v</th><td>5v@1A Rail</td></tr>
<tr><th>+3v3</th><td>3.3v@300mA Rail</td></tr>
<tr><th>GND</th><td>Ground rail</td></tr>
<tr><th>Reset</th><td>MCU reset, active low</td></tr>
<tr><th>SCL</th><td>I2C Clock</td></tr>
<tr><th>SDA</th><td>I2C Data</td></tr>
<tr><th>A0</th><td>Plank address line 2</td></tr>
<tr><th>A1</th><td>Plank address line 1</td></tr>
<tr><th>A2</th><td>Plank address line 0</td></tr>
</table>


The VIN pin provides access to the unregulated power supplied to the Loki, and is connected directly to the onboard 5V regulator's input. Unregulated power may be avaible from it, depending on operating conditions, or the plank can supply power to the VIN pin. The plank MUST NOT supply both VIN and +5V simultaneously. The VIN pin may have no voltage on it even when the Loki is running - for instance, when it is being powered over USB.

VIN is limited to 20v. The plank will never be supplied more than this on VIN, and MUST NOT apply more than 20v to VIN.

+5V provides access to the output of the Loki's +5v regulator. This is  switching regulator, which can supply up to 1A. A plank MUST NOT attempt to draw more than 1A from the regulator. If it expects to draw a significant amount of power, it SHOULD provide its own power source, even if it does not plan to exceed 1A. The +5V line will always be powered when the Loki is powered.

A plank MAY supply +5V itself to the Loki. If it plans to do this, it MUST only do so when VIN is not being powered by another device.

All planks MUST include a CAT24C or compatible EEPROM of at least TBDk for configuration purposes, connected to the I2C SCL and SDA lines. The EEPROM's address lines MUST be connected to the corresponding address lines on the configuration header.

All planks MUST include an XOR gate such as the 74HC1G86 to generate the next bit of the I2C address, as described below, unless the plank is a top plank.

Address lines are forwarded from the input to the output as follows:
<table>
<thead>
<tr><th>Output Pin</th><th>Input Pin</th></tr>
</thead>
<tr><td>A0</td><td>A1 xor A2</td></tr>
<tr><td>A1</td><td>A0</td></tr>
<tr><td>A2</td><td>A1</td></tr>
</table>


A top plank does not need to include this circuitry.

If a plank consumes no IO pins (for instance in the case of a plank that acts as a power supply, or only uses the I2C bus), the EEPROM MAY be omitted. If the EEPROM is omitted, the plank MUST pass the address lines through directly, without shifting or XORing them.

### Recommended schematic for configuration header

![](/images/loki plank schematic.png)

### Suggested board layout for configuration header.

![](/images/loki plank power connector.png)

## <a id="gpio">Electrical Connections - GPIO</a>

A standard 16x2 pin 0.1" header MUST be attached to the bottom of the plank in the position indicated in the top right of the dimensional drawing. A corresponding receptacle MUST be placed on the top of the plank, unless the plank is a top plank. If the plank is a top plank, the header used may be thru-hole instead of surface mount.

Loki has 32 GPIOs exposed on the GPIO header. Pins are numbered starting with the top right pin, number 1, and proceeding top to bottom, right to left, making the bottom left pin number 32. Pins are broken into two banks, with pins 1-16 forming bank 1, and pins 17-32 forming bank 2.

A plank requiring GPIO pins MUST take equal numbers of pins from each of the two banks. If a plank requires an odd number of IOs, it should take the extra pin from a bank selected at random. A plank SHOULD take the first pins from each bank.

A plank MUST connect unused input-side IO pins to its output-side pins, reallocating them so as to fill the first pins on each bank. For example, if a plank uses pins 1.1 and 1.2, it should connect the input pin 1.3 (denoted I1.3) to the output pin 1.1 (denoted O1.1), then I1.4 to O1.2, and so forth. As a result, the remaining pins in each bank will always form an unbroken block. A plank MUST NOT reassign pins between banks.
Pin reallocation with one pin from each GPIO bank consumed.

All GPIOs use 3.3v logic levels. A plank MUST NOT cause a voltage of more than 3.3 volts to be applied to any of the GPIO pins.

## <a id="eeprom">Configuration EEPROM contents</a>

The configuration EEPROM on each plank stores information about the plank's name and version number, a unique identifier for both the plank design and the unit, fields describing which pins the plank uses from each bank, and pin names for the pins being used. This information allows an attached computer, via the bootloader, to present information on attached planks, including pin assignments between the plank's pins and the PSoC processor's pins.

The EEPROM is laid out as follows:

<table class="protocoldesc">
<thead>
  <tr><th>7</th><th>6</th><th>5</th><th>4</th><th>3</th><th>2</th><th>1</th><th>0</th><th>7</th><th>6</th><th>5</th><th>4</th><th>3</th><th>2</th><th>1</th><th>0</th></tr>
</thead>
<tr>
  <td colspan="16">"LK"</td>
</tr>
<tr>
  <td colspan="16">Maker ID</td>
</tr>
<tr>
  <td colspan="16">Plank ID</td>
</tr>
<tr>
  <td colspan="3">Reserved</td>
  <td>Supplies5V</td>
  <td>SuppliesVin</td>
  <td>TopPlank</td>
  <td>IsHost</td>
  <td>Configured</td>
  <td colspan="8">Reserved</td>
</tr>
<tr>
  <td colspan="8">Name length</td>
  <td colspan="8">Name</td>
</tr>
<tr>
  <td colspan="16">...</td>
</tr>
<tr>
  <td colspan="8">Version length</td>
  <td colspan="8">Version</td>
</tr>
<tr>
  <td colspan="16">...</td>
</tr>
<tr>
  <td>GPIO 1 in</td>
  <td>GPIO 1 out</td>
  <td>GPIO 1 analog</td>
  <td colspan="5">GPIO 1 name length</td>
  <td colspan="8">Name</td>
</tr>
<tr>
  <td colspan="16">...</td>
</tr>
<tr>
  <td colspan="16">...</td>
</tr>
<tr>
  <td>GPIO 32 in</td>
  <td>GPIO 32 out</td>
  <td>GPIO 32 analog</td>
  <td colspan="5">GPIO 32 name length</td>
  <td colspan="8">Name</td>
</tr>
<tr>
  <td colspan="16">...</td>
</tr>
</table>

All numbers are stored little-endian.

Strings are stored prefixed by a single byte containing their length. GPIO name strings have their length byte combined with flags that indicate if they are input, output, or analog pins; the top 3 bits contain these flags while the lower 5 bits contain the length of the string. Strings are packed one after another, with no intervening padding.

The layout is designed to fit in a 256 byte eeprom; while a plank may equip itself with a larger one, it is wise to design with this in mind.

## <a id="i2c">I2C Bus</a>

The Loki configuration and power header is equipped with an I2C bus. This bus exists primarily to communicate with the EEPROM each plank is equipped with, but may also be used by planks for their own purposes, provided adequate provisions are made to avoid address conflicts.

The 7-bit I2C addresses 0x50 - 0x58 are reserved for use by the board configuration EEPROMs. The address 0x50 is used by the Loki's onboard EEPROM.

A plank SHOULD make adequate provision to minimize the possibility of conflicts with I2C devices on other planks. If the I2C device in use is provisioned with address configuration pins, it is recommended that the plank make use of the A0, A1 and A2 lines to configure these pins.

The I2C bus is equipped with 2.2k pullup resistors between the SDA and SCL lines and the 3.3v rail. A plank SHOULD NOT add its own pullup resistors.
