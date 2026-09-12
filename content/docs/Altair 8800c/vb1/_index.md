---
title: Solid State Music VB-1
draft: false
---

{{< tabs >}}

  {{< tab name="Front" >}}![](assets/vb1-front.png "VB-1 Front"){{< /tab >}}
  {{< tab name="Back" >}}![](assets/vb1-back.png "VB-1 Back"){{< /tab >}}

{{< /tabs >}}

The Solid State Music VB-1 is an early video card for S-100 computers. As far as I can tell there is no surviving documentation for this particular card (at least online) although there is a good manual available for the [VB-1B](https://www.s100computers.com/Hardware%20Manuals/SSM/SSM%20VDB-1.pdf) which is very similar.

### Restoration

I got this card for $15 at [VCFSW](https://www.vcfsw.org) with assurance that it absolutely did not work, which was correct. The card stores characters in a 1k page of internal memory that's mapped into the main system's address space, and it otherwise doesn't interact with this host system. So in principle I would be able to power up the card *in vitro* and see a screen full of garbage.

![](assets/vb1-power.png "VB-1 requires +8V, +16V, and -3V.")

The first attempt failed, with the monitor unable to sync and the video signal was much too slow, which led me to a dead counter IC. After replacing this I was able to catch some glimpses of garbage.

![](assets/vb1-garbage.png "Behold, garbage.")

The garbage display was encouraging, but it was flickering. The only moving part was the DIP switches, so I replaced them and the flickering went away. I also ended up replacing the 5V regulator (hoping a newer one would run cooler), and changed the Molex output headers to JST-VH, which I prefer. So with these fairly minor repairs we're in business.

### Configuration and Interfacing

The VB-100 has a block of DIP switches that configure the display mode and the address range it listens to.

![](assets/vb1-switches.png "VB-1 DIP Switches")

- `GRPH` switches to the graphics character set when set to ON.
- `64CL` sets the display to 64 characters per line when ON, otherwise it's 32 double-width characters per line.
- `A[15:10]` set the start of the 1k page of internal RAM (lower bits are all zero). The host machine either needs to have no memory in this region (as was typical at the time) or this memory needs to be masked out. The sense of these switches is reversed, so ON means zero; here the address is set to F400.

Masking memory regions in and out can be complicated, but fortunately I had built up a [Flex64](https://deramp.com/flex64k.html) which gives control over 1k blocks in upper memory. This allowed me to turn the F400 page off.

![](assets/flex64.png "Flex64 Card")

With this done, all that was left was seeing if I could write to the display.

### Testing on the Altair

