+++
date = '2026-09-13T15:23:37-05:00'
draft = false
title = 'I Fixed the Air Conditioner'
+++

![](lowes.png)

The AC went out last night and it was 82° inside this morning. All the HVAC contractors are super busy in Texas in the summer, and the best we could get was an appointment in three days. Not good enough. So I decided to give it a look myself.

 <!--more--> 

{{< callout type="error" >}}
  I am not an electrician, I am a hobbyist. I have some experience with mains power but I am absolutely
  not qualified to tell you how to do this kind of thing. This is just a report about what I did and how it
  worked out.
{{< /callout >}}

It turns out the most common failure, a dead run capacitor, is easy to diagnose and easy to fix. My symptoms were:

- The outside fan was spinning (this was unusual) but the compressor wasn't running.
- From time to time it would buzz for a couple seconds.

The problem is that without some capacitance to provide a phase shift in the current, the compressor motor can't start or keep running. The fan motor seemed to get by ok for some reason. In any case, the big capacitor was rusty and bulging so I suspected that was the problem. Here's what I did to diagnose.

- Turned the air conditioning off at the thermostat.
- Pulled out the cutoff breaker in the utility box for the AC unit.
- Removed the service panel.
- Checked AC voltage inside to be sure it was really disconnected.
- Checked DC voltage across the capacitor, between the compressor terminal (3 prongs) and common (4 prongs), and between the fan terminal (2 prongs) and common. Normally these will be zero because the capacitor will drain through the motor coils, but if a coil is broken then the cap can contain a deadly amount of energy that needs to be discharged Watching the number go down while I hold multimeter probes across the terminals is the way I like to do this, rather than making a huge bang with a screwdriver. In my case all were zero.
- Checked resistance across the same pairs of terminals. It was a few ohms for the compressor coil and a few tens of ohms for the fan coil, which seemed reasonable. They were not shorted, which made me fairly confident the motors were ok.
- Checked capacitance across the same pairs of terminals. Nothing. Multimeter didn't recognize that anything was connected. I took a photo of the wiring and then disconnected the cap and checked it on the LCR meter and it was just a few picofarads on both sides. Completely dead.

Now confident in my belief that the cap was bad I entered Lowe's with a purposeful stride and walked to the capacitor section. However there was no such section so I strode back out and drove down the street to Home Depot, which did have a capacitor in the neighborhood of what I needed. Mine was a 45/5 and those were sold out, so I got a 50/5. A little extra can't hurt. I assume.

Anyway, back home, plugged everything in and it worked. House is back down to 75° and everyone's mood is much improved. Total cost was $25 and I am now a local hero.

