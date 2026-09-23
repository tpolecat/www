+++
date = '2026-09-23T10:38:15-05:00'
draft = false
title = 'Testing Servos with a Function Generator'
+++

Very quick post about testing servos without a servo tester, mostly for my own reference but here you go.

<!--more-->

<video src="testing.mp4" controls>Your browser does not support the video tag.</video>

I occasionally build things with SG90 hobby servos and I like to hook them up and see them move without having to deal with a microcontroller. It's easy to do with a function generator.

### Control Signal

SG90 servos (and maybe others, I don't know) are powered by 5V and have a third wire (orange), which is the control signal.

- The control signal is a stream of **20ms pulses**.
- The length of these pulses determines servo demand.
- Pulses vary between **1ms** and **2ms** in width, controlling 180° of movement.
- Behavior outside these ranges is usually undefined, but most servos can go a few tens of degrees past the limits.

### Function Generator Setup

Set up the function generator as follows:

- Amplitide of **5V**, offset **+2.5V** (i.e., swinging between 0V and +5V).
- One of:
  - pulse mode with a period of **20ms** and width of **1.5ms**; or
  - square wave at **50Hz** with duty cycle of **7.5%**.

Wire up power and ground (red and brown) to the servo, connect the control wire (orange) to the function generator's output, and connect function generator ground to the other ground wires. I made a little board so I can just plug everything in.

The servo should zero itself when you power up and start producing a signal. Adjust the pulse duration between 1ms and 2ms (or 5% and 10% duty cycle) to test range of movement.





