---
layout: post
title: Registers
---

Just for fun, I'm working on building a basic CPU. At this point I think it
will contain three user addressable 8-bit registers (`r1`, `r2`, `r3`) as well
as a `PC` register and two registers to contain the high and low bytes of the
current instruction.

I've been reading a lot about register and latch ICs, and I think I've figured
out how to build the registers. They'll need to connect to an 8-bit bus, so
that e.g. with a `mov r1, r2` instruction `r2` will own the bus, writing its
value to it, and `r1` will latch the value on the bus.
