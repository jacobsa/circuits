---
layout: post
title: Simplified Adders
---

In the previous [adders post] [v1] the circuits used NAND and XOR gates. But
you can do better in terms of number of gates (and therefore amount of
soldering) by using AND and XOR. The half adder has only two gates instead of
three:

![Half adder with AND gate](/circuits/images/half_adder_v2.png)

The full adder has the same number of gates as before, but they've switched
from NAND to AND in order to keep using only two types of gates throughout:

![Full adder with AND gate](/circuits/images/full_adder_v2.png)

[v1]: /circuits/2010/10/02/adders.html
