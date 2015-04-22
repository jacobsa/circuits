
---
layout: post
title: IC-controlled LED (Revisited)
---

In my [previous post][prev] about this topic from five years ago, my circuit had
the LED hooked up to the emitter of the transistor:

![Old circuit](/circuits/images/5v_ic_controlled_led.png)

I'm not sure why I did it this way; the "Using a transistor as a switch" section
of that [amazing page][kpsec] about transistors clearly shows the load as being
above the collector, with the emitter attached directly to ground. Moreover,
attaching the emitter to ground makes it possible to drive multiple LEDs
independently with an IC containing multiple transistors with a common emitter
such as the [ULN2003A][], which appears to be a very common source of NPN
transistors in TTL and CMOS designs.

[prev]: http://jacobsa.github.io/circuits/2010/10/03/ic-controlled-led.html
[kpsec]: http://electronicsclub.info/transistorcircuits.htm
[ULN2003A]: http://www.st.com/web/en/resource/technical/document/datasheet/CD00001244.pdf
[led]: http://led.linear1.org/1led.wiz
