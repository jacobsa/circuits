---
layout: post
title: N steps and stop circuit
---

[This site][lm555] has a bunch of useful designs involving 555 timers.

In particular, it has a nice "[N steps and stop][n_steps]" circuit built using a
555 and a 4017 decade counter that would be useful in implementing control
logic. Basically the idea is that you tie the Nth output of the 4017 to a
transistor that will ground the `RESET` pin of the 555. (I'm not sure at this
point why not use an inverter instead; maybe that would be fine too.)

[lm555]: http://home.cogeco.ca/~rpaisley4/LM555.html
[n_steps]: http://home.cogeco.ca/~rpaisley4/LM555.html#33
