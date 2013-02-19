---
layout: page
title: "Re:load assembly instructions"
date: 2013-02-19 19:54
comments: true
sharing: true
footer: true
---

## Parts list

The parts in your kit will depend on whether you have a regular Re:load or the "Epic" version. The list below shows the parts for both kits.

<table>
  <thead>
    <tr><th>Designation</th><th>Re:load Part</th><th>Epic Re:load part</th><th>Quantity</th></tr>
  </thead>
  <tr><th></th><td colspan="2">Re:load PCB</td><td>1</td></tr>
  <tr><th>Q1</th><td>BTS117 TO-220 MOSFET</td><td>BTS141 TO-220 MOSFET</td><td>1</td></tr>
  <tr><th></th><td>12 watt heatsink</td><td>20 watt heatsink</td><td>1</td></tr>
  <tr><th>R1</th><td colspan="2">3 watt 0.05 ohm resistor</td><td>1</td></tr>
  <tr><th>R6</th><td colspan="2">10k ohm potentiometer</td><td>1</td></tr>
  <tr><th>IC1</th><td colspan="2">MCP6002 8-DIP Op-Amp</td><td>1</td></tr>
  <tr><th>IC2</th><td colspan="2">LP2950 3.0v precision LDO regulator</td><td>1</td></tr>
  <tr><th>JP1</th><td colspan="2">2 terminal 5.0mm spring terminal</td><td>1</td></tr>
  <tr><th>D1</th><td colspan="2">BAT42 Schottky Diode</td><td>1</td></tr>
  <tr><th>C2</th><td colspan="2">33uF Electrolytic Capacitor</td><td>1</td></tr>
  <tr><th>C3</th><td colspan="2">1uF Ceramic Capacitor</td><td>1</td></tr>
  <tr><th>C1</th><td colspan="2">0.1uF Ceramic Capacitor</td><td>1</td></tr>
  <tr><th rowspan="3">R3<br>(See instructions)</th><td colspan="2">510k ohm resistor</td><td>1</td></tr>
  <tr><td colspan="2">160k ohm resistor</td><td>1</td></tr>
  <tr><td colspan="2">75k ohm resistor</td><td>1</td></tr>
  <tr><th>R4, R5</th><td colspan="2">10k ohm 1% resistor</td><td>2</td></tr>
  <tr><th>R7</th><td colspan="2">100 ohm resistor</td><td>1</td></tr>
  <tr><th></th><td colspan="2">Packet of thermal paste</td><td>1</td></tr>
  <tr><th></th><td colspan="2">M3 6mm machine screw</td><td>1</td></tr>
  <tr><th></th><td colspan="2">M3 nut</td><td>1</td></tr>
</table>

## Assembly instructions

First, place the resistors R3, R4, R5 and R7, and the diode D1 as marked. The resistors can face either way, but make sure you match the diode's stripe with the one printed on the board.

Several alternative choices are provided for R3, which determines the range of currents that can be set for the Re:load. Choose R3 according to the maximum current you want to be able to set:

<table>
  <thead>
    <tr><th>Max current</th><th>R3 value</th></tr>
  </thead>
  <tr><td>1 amp</td><td>510k</td></tr>
  <tr><td>3 amps</td><td>160k</td></tr>
  <tr><td>6 amps</td><td>75k</td></tr>
</table>

Selecting a smaller max current allows you to adjust the current within that range more accurately.

If you have a regular Re:load, do not select the 75k resistor for 6 amps. Your Re:load will not do 6 amps; it will still max out at 3, making half the potentiometer's range useless!

The diode is present to protect Re:load against damage due to reverse polarity. All diodes have a voltage drop, however, and the result of the Re:load's protection diode is a slight decrease in efficiency at low voltages. If you anticipate using the Re:load at low voltages - below about 4 volts - a lot, and need higher currents and better constant-current performance at those voltages - you may want to (at your own risk!) leave out the protection diode D1, replacing it with a wire link instead. If you do this, beware - hooking Re:load up in reverse polarity will most likely destroy it!

After inserting the resistors and diode, turn the PCB over like so:

![](stage1.JPG)

Now, solder the components in, making sure they're close to the PCB, then clip off the excess leads:

![](stage2.JPG)

Turning the PCB over, we can see the parts soldered neatly in place:

![](stage3.JPG)

Now insert and solder the Opamp in the position marked IC1. Make sure that you insert it the right way around, matching up the indentation on the IC with the one on the board's silkscreen.

![](stage4.JPG)

Next, add the voltage regulator and the two ceramic capacitors. Make sure to insert the voltage regulator the right way around, so it matches the drawing on the board's silkscreen. The capacitors can go in either way around. Each one has a different lead spacing, so it's easy to tell which goes where.

![](stage5.JPG)

Now solder in the large 0.05 ohm shunt resistor in the space marked R1.

![](stage6.JPG)

Add the spring terminals and the electrolytic capacitor. There's only one sensible direction for the spring terminals to go. The capacitor is polarised - make sure to match up the longer '-' lead with the marked pin on the board.

![](stage7.JPG)

Now the potentiometer. You will have to wiggle it a bit and press reasonably hard before the pins clip into the slots. Once it's in, solder both the electrical contacts and the mounting pins to keep it in place.

![](stage8.JPG)

Now for the transistor and the heatsink. It's important to attach the transistor to the heatsink before adding either to the PCB.

First, take out the packet or syringe of thermal paste. Apply it to the back of the transistor. You don't need a thick coating, just enough to cover the whole part.

Then, line the transistor up against the heatsink so that the hole in the transistor is aligned with the middle hole on the heatsink. The legs should stick down so that the thicker part of the legs are entirely above the bottom of the heatsink. Otherwise, the transistor will not fit neatly on the board. Insert the provided screw and nut, and tighten with a screwdriver.

![](stage9.JPG)

Finally, insert the heatsink and the transistor into their holes on the PCB. Some care will be needed to line everything up neatly. Once you have, solder the transistor and heatsink to the board. You will need a lot of heat and a fair bit of solder to solder the heatsink pins!

![](stage10.JPG)

Congratulations! You've built your Re:load! Now read on to calibrate and use it.

## Calibration

The Re:load has two test pads near the front for reading off the instantaneous current. Because all components have some natural variation, calibration is required for this value to be accurate. The calibration procedure is simple, but if you don't care about the accuracy of the current measurement, you can skip this.

 1. Attach the Re:load to a current source such as a bench supply, in series with a multimeter set to measure current. Take care to get the polarity on everything right!
 2. Turn on the power supply
 3. Adjust the Re:load's potentiometer until the multimeter reads exactly 1 amp
 4. Remove the multimeter from the circuit and reconnect the Re:load. Configure the multimeter for voltage measurement.
 5. Attach the multimeter across the current sense test pads. Adjust the trimpot on the bottom of the board (not the big potentiometer!) until the multimeter reads exactly 0.1 volts.

## Use

Using the Re:load is simple - if you followed the calibration procedure, you've already done it. Hook the Re:load up to a power source of at least 3.3 and no more than 30 volts. Re:load will attempt to draw a fixed amount of current; adjusting the potentiometer adjusts Re:load's current draw.

In addition to current and voltage limits, Re:load has a maximum capacity to absorb energy. For the regular Re:load this is approximately 12 watts; the larger heatsink on the Epic increases this to approximately 20 watts. These values will vary depending on ambient temperature and airflow. Re:load can be run at powers significantly higher than these values, but it will eventually overheat, at which point the thermal cutoff in the transistor will activate, and it will stop drawing current until it is disconnected from the circuit and reconnected.

Re:load is very robust. A diode protects the sensitive electronics against reverse polarity, but the transistor contains a body diode that will conduct current if connected backwards. As a result, Re:load will draw a lot of current when connected in reverse. This causes no problems for Re:load in the short term, but it's possible it may overload your supply! In theory, if left connected in reverse for long enough, the temperature could rise sufficiently to damage the transistor, since the thermal cutoff won't activate when reverse biased. So don't do that. Re:load is also not rated for over 30 volts; above that the voltage regulator for the electronics may fail, causing the opamp to fail as well.

Below approximately 4 volts, Re:load's maximum current is reduced. At 3.3 volts, the regular Re:load can draw at most 2 amps, while the Epic can draw about 3.7 amps. This is due to the voltage drop across the protection diode and voltage regulator causing the supply voltage to the opamp circuit to go below 3 volts, and manifests as a slight variation from Re:load's normal constant current behaviour. If you expect to be running Re:load at low voltages often and need better performance at these voltages, you may want to consider leaving out the protection diode as described in the assembly instructions above.

Re:load will operate below even 3.3 volts, but it will no longer operate as a constant current device, and its maximum current diminishes rapidly, down to nearly zero at approximately 2 volts.

## Re:load hacks

Have you done something cool and unusual with Re:load? I'd love to hear about it! Please [email me](mailto:nick@arachnidlabs.com) and let me know!