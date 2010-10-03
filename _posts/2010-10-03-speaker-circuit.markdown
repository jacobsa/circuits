---
layout: post
title: Speaker Circuit
---

![Speaker circuit](/circuits/images/speaker_circuit.png)

The input is assumed to line in the range 0-3.3 V. The speaker is assumed to be
8 Ω, 0.5 W.

<!-- P_{avg} = \frac{V_{RMS}^2}{R} = \frac{V_{peak}^2}{2R} = \frac{(1.65 V)^2}{16 \Omega} \approx 0.170 W -->
<!-- http://www.codecogs.com/latex/eqneditor.php -->
![Average power calculation](/circuits/images/speaker_power.png)

A capacitor is used for AC coupling, to remove the DC offset (which would
otherwise be 1.65 V). Leaving in the DC offset would leak power and cause
distortion.
