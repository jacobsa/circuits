---
layout: post
title: Push-button Debouncer
---

![Push-button Debouncer](/circuits/images/push_button_debouncer.png)

A simple circuit for debouncing a push-button, taken from the great explanation
[here] [ganssle]. The 4093 quad-NAND gate chip is used for its Schmitt trigger,
which keeps the logic level steady and well-defined. In this circuit it inverts
its input so that its output is high while the button is pressed, and is
suitable for feeding into other CMOS chips.

[ganssle]: http://www.ganssle.com/debouncing-pt2.htm
