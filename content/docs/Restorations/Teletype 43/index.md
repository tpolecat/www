+++
draft = true
title = 'TTY Model 43'
+++

The Teletype Model 43 (1977) was the last and worst electromechanical terminal manufactured by the Teletype Coroporation. It features a classic mechanical keyboard and a dot-matrix print head. Although construction is mostly metal on the inside, there are plenty of brittle plastic parts to contend with. The outer case is non-brittle but is strangely flexible, like a trash can.

Mine arrived dirty, yellowed, bestickered, and hardwired to an acoustic coupler.

![](initial.png "This just in.")

### Inspection

The TTY actually looked to be in pretty good mechanical shape, apart from some broken plastic parts. I gave everything a good cleaning and added silicone lubricant where it seemed like a good idea.

![](internals.png "Mechanical goodness.")

Parts needing replacement included the paper guides (one of which was missing entirely), a broken nub on the page separator, broken stabilizing ears for the rear bustle cover, and a missing thumb tab on the front cover. All were straightforward to reproduce and print (design files [here](https://github.com/tpolecat/3d-models/tree/main/TTY%2043)) other than the paper guides, which were complex and took a few tries to get right.

{{<tabs>}}
  {{<tab name="Paper Guides">}}![](parts_1.png "Broken part, and replacements."){{</tab>}}
  {{<tab name="In Action">}}<video src="parts_2.mp4" controls>Your browser does not support the video tag.</video>{{</tab>}}
{{</tabs>}}

### Re-Inking

One of the hurdles to overcome when working with old dot-matrix printers is that ribbon cartridges are increasingly impossible to find. Luckily there was one in my Model 43, but it was totally dried out and crusty.

The cartridge would be easy to reproduce, but the ribbon itself is an issue because (unlike most printer/typewriter ribbons) it's a **continuous loop** of a very specific length that re-inks itself over an roller as it's pulled through the cartridge. My only real option was to see if I could re-ink the roller and hope the crusty ribbon would loosen up on its own after contacting wet ink again.

![](ink_0.png "The situation. Soaking the roller.")

My first attempt at re-inking was with ink jet ink, which was very, very wrong and didn't work at all. Next try (after cleaning the roller again) was with [oil-base stamp refill ink](https://www.amazon.com/dp/B0782YY5RD). It took a few hours of dripping and waiting for the ink to soak in, and in the end it worked. The resulting test pattern was kind of sloppy at first but it cleared up once the ribbon went around a few times.

<video src="ink_2.mp4" controls>Your browser does not support the video tag.</video>

### RS-232

Next up was figuring out how to interface the TTY to a computer. It arrived hardwired to an acoustic coupler (which I removed and will return to at some point) and had no other ports. Fortunately the [service manual](https://bitsavers.org/communications/teletype/43/) describes the location of the TTL serial signals, which I was able to pick up and run through a [MAX232](https://www.ti.com/product/MAX232) transceiver and on to a DB-25 connector. I printed some brackets for all this stuff and attached them inside the bustle chassis.

{{<tabs>}}
  {{<tab name="Top View">}}![](rs232_1.png "Bustle-mounted DB25 and MAX232"){{</tab>}}
  {{<tab name="Rear View">}}![](rs232_3.png "MAX232 Board and DB25"){{</tab>}}
{{</tabs>}}

Fortuntely all the supporting electronics in the TTY seemed to be working just fine, so with that I was able to communicate with my Mac.

<video src="rs232_2.mp4" controls>Your browser does not support the video tag.</video>

### End Result

Last up was some cosmetic whitening via a peroxide soak in the Texas sun. End result is a fully-working, pretty good-looking Teletype.

![](done.png "Sparkly clean and fully working.")