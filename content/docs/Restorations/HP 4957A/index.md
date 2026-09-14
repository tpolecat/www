---
title: HP 4957A
---

The HP 4957A Protocol Analyzer is an adorable little instrument from 1991 for analyzing serial protocols including RS-232, RS-449, and V.35 (the only one I know or care about is RS-232). I learned about this instrument from CuriousMarc, who has an [article](https://www.curiousmarc.com/instruments/hp-4957a-protocol-analyzer) on his website about upgrading ROMs on these machines, which we will come back to.

I got mine at [VCFSW](https://www.vcfsw.org) in 2024 for $90 if I recall correctly. It was part of a grand haul that kept me busy for some time.

![](vcfsw.png "(Wee chap on the left.)")

### Initial Assessment

On booting it up it made some excited beeps which I enjoyed very much, but I immediately noticed that it didn't say "4957" like it was supposed to, and the labels for the hot keys weren't being displayed. They appeared just fine on an external monitor though, and otherwise it seemed to be in good working order.

![](problem.png)

Further investigation confirmed that half-intensity video just wasn't showing up anywhere. I thought it might be setting somewhere but couldn't find anything, and also was unable to find anyone else who had encountered this issue. But I had a huge pile of new hardware to play with so I set this aside for a while.

### Debugging

Some months later it occurred to me that the problem could be a hardware incompatibility; perhaps the original owner had upgraded this machine to the A0002 software when it really only works with A0001. To test this I programmed the old software and tried it out.

{{<tabs>}}
  {{<tab name="Programming">}}![](eeproms.png){{</tab>}}
  {{<tab name="Installed">}}![](eeproms_2.png){{</tab>}}
{{</tabs>}}

No dice, same behavior. I swapped the ROMs back and continued poking around since I had the machine opened up, and figured out what all the potentiometers did. Unfortunately none of the adjustments helped. Half-intensity video seemed to be entirely missing, and the lack of schematics or any kind of service manual was extremely irritating.

{{<tabs>}}
  {{<tab name="Focus">}}![](focus.png){{</tab>}}
  {{<tab name="VSize & VPos">}}![](vsize.png){{</tab>}}
{{</tabs>}}

So I buckled down and started poking around for video and found the missing signal. I tried to reverse-engineer the circuit but I was lost in a twisty maze of analog SMD parts, all alike. As an aside, SMD marking is *extremely* frustrating because markings are not even a little bit unique. Identically marked SOT-23 parts could be transistors, diodes, two diodes, voltage regulators, who knows. It's really dumb.

Anyway the breakthrough came when I noticed that the pads for a unpopulated part looked funny. On closer inspection it was clear that there *had been* a part here, but it had been bashed off at some point.

![](bash.png "Bashed off SOT-23 in lower left.")

Based on similarty to a nearby circuit I just kind of guessed that this was a zener diode and just kind of guessed at the value and hacked one in.

![](zener.png "Shut up, it's fine.")

And behold! A working instrument.

![](working.png)

I feel like I got really lucky on this one, but I will take the win any way I can get it.

