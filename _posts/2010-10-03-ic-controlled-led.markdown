---
layout: post
title: IC-controlled LED
---

**Update**: Make sure to see the [new post][] on this topic, containing a better
circuit.

[new post]: http://jacobsa.github.io/circuits/2015/04/22/ic-controlled-led.html

Some ICs, like the 555 timer, are able to source enough current to drive an
LED. However many aren't, and instead a transistor can be used to switch
current directly from a voltage source:

![Transistor-switched LED circuit](/circuits/images/5v_ic_controlled_led.png)

In the circuit above, A is the IC output. It's assumed that logical one is +5V,
and the LED is a red one (with a 1.8 V drop and safe current of about 20 mA).
If you switch LEDs or voltage levels, recalculate the value for the 180 Ω
resistor using an [LED calculator] [led], and the 5.6 kΩ resistor using the
"Choosing a suitable NPN transistor" section [here] [kpsec].

[led]: http://led.linear1.org/1led.wiz
[kpsec]: http://electronicsclub.info/transistorcircuits.htm
