---
layout: post
title: Registers
---

Just for fun, I'm working on building a basic CPU. At this point I think it
will contain three user addressable 8-bit registers (`r1`, `r2`, `r3`) as well
as a `PC` register and two registers to contain the high and low bytes of the
current instruction. (There will also be an ALU and memory.)

I've been reading a lot about register and latch ICs, and I think I've figured
out how to build the registers. They'll need to connect to an 8-bit bus, so
that e.g. with a `mov r1, r2` instruction `r2` will own the bus, writing its
value to it, and `r1` will latch the value on the bus. So each register board
(I'll probably build them on separate pieces of vero) will have the following
terminals:

 *  `D0-7` -- the lines of the bus.

 *  `OUTPUT` (active low) -- when this is low, the register owns the bus and
    outputs its value. When it's high, the register board's outputs are in a
    high impedance state.

 *  `LATCH` -- when you want to write to the register, ensure the bus contains
    the appropriate value and then bring this momentarily high, then low again.
    Keep it low to retain the value.

This seems very easy to build with a [74573 transparent latch] [74573] IC:

 *  `D0-7` are just the inputs to the IC.

 *  Attach `OUTPUT` to the active-low `OE` pin on the IC.

 *  Attach `LATCH` to the `LE` pin on the IC.

 *  Connect the IC's outputs (`Q0-7`) to its inputs (`D0-7`). If I understand
    correctly, this won't cause any problems because when `OUTPUT` is low the
    outputs are high impedance, and when it's high you should have the register
    latched anyway.

The latch IC acts both as the register itself and as a bus transceiver.

I think it would be cool to have each register board also contain an 8-bit LED
display of its current value for debugging purposes, especially when I'm first
building the system. To do that the latch IC needs to always output its
contents though, which means I'll need a separate buffer, like the [74245 bus
transceiver] [74245]. It seems sufficient to put the buffer between the latch
IC's outputs and its inputs, and to connect the LEDs between the latch IC's
outputs and the buffer.

[74573]: http://au.farnell.com/nxp/74hct573n/74hct-cmos-74hct573-dip20-5v/dp/382449
[74245]: http://au.farnell.com/texas-instruments/sn74hct245n/bus-transceiver-octal-74hct245/dp/9591931
