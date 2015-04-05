---
layout: disquspost
title: "The Loki Motor Plank"
date: 2013-02-01 22:41
comments: true
categories: loki
---

Last of the initial set of Loki planks - but certainly not least - I present the Loki Motor Plank:

![](https://lh5.googleusercontent.com/-QQby0ZFF-Ns/UQxDbCFsXeI/AAAAAAAACcc/FlMHnQw8qOw/w397-h298-n-k/P1010198.JPG)

The Motor Plank is a straightforward DC motor driver utilizing the [TB6612FNG](https://www.pololu.com/file/download/TB6612FNG.pdf?file_id=0J86) dual H-Bridge motor driver. It's capable of driving two DC motors at up to 1.2A each - or you can parallel it to drive a single motor at a higher current.

The board uses six GPIO pins, for the A, B and PWM inputs on each H-Bridge. The board features screw terminals for the motors and optional DC power in, and bicolor LEDs to indicate motor speed and direction. An optional jumper allows you to connect the motor driver's power rail to the Loki's VIN terminal. This gives you the flexibility of powering the motors straight from the Loki if using a DC adaptor and low power motors, powering the Loki from the motor driver screw terminals, or of having two entirely separate supplies for motor and Loki.

The plank's naturally pretty straightforward to operate: simply set the A and B inputs for the desired direction of motion on each motor, and PWM the PWM pins to control motor speed.

Of course, the Loki's flexibility when it comes to GPIO and peripherals makes it easy to implement motor driving schemes other than Sign-Magnitude; I look forward to seeing someone implement [Locked Anti-Phase Drive](http://modularcircuits.tantosonline.com/blog/articles/h-bridge-secrets/lock-anti-phase-drive/) with no CPU overhead!
