---
title: Scopetrex
---

The [Scopetrex](https://github.com/schlae/scopetrex) is a Vectrex clone on a single board, meant to be played on an analog oscilloscope in XY mode. It's a super fun advanced-beginner project with great documentation and a relatively cheap build cost.

## The Build

I ordered boards from JLCPCB and got the parts I needed from Mouser, and took my time with the build.

{{<tabs>}}
  {{<tab name="Getting Started">}}![](build_1.png){{</tab>}}
  {{<tab name="Done!">}}![](build_2.png){{</tab>}}
{{</tabs>}}

I got some sheets of 5x7" acrylic from Amazon and drilled matching holes so I could mount it to the top of the board using standoffs. It looks nice and protects the components from cats.

![](acrylic.png)

I didn't really have any issues. Hooked it up to my Tektronix 2213 and it worked great!

<video src="scope.mp4" controls>Your browser does not support the video tag.</video>

Cool and all, but I wanted it to be cooler.

## Vectorscopes

Enter the formidable Tektronix 1720/1721 vectorscopes. These are broadcast television insruments meant for monitoring video signal quality, but they can also operate as X/Y displays. They usually come in a pair, as mine did, for the low-low price of $60 at [Doug Deals](https://www.dougdeals.com).

<video src="vec1.mp4" controls>Your browser does not support the video tag.</video>

The only problem is, the blanking signal is not passed directly through; IIRC it is mediated by a processor that needs to be put into a special mode in order to work. Lacking the patience for this kind of thing, I just bodged the signal across to where I wanted it. 

<video src="vec2.mp4" controls>Your browser does not support the video tag.</video>

And with this change we get two channels of Scopetrex! (Bad reflection; they're identical in person.)

<video src="vec3.mp4" controls>Your browser does not support the video tag.</video>

The only remaining issue is that the Scopetrex itself isn't rack-mounted.

## Rack Mounting

Kind of excessive but I was very intent on owning the world's only rack-mounted Scopetrex. A little drilling, a little gluing, a lot of coffee later and ... victory!

{{<tabs>}}
  {{<tab name="Drilling">}}![](rack_1.png){{</tab>}}
  {{<tab name="Hacking">}}![](rack_2.png){{</tab>}}
  {{<tab name="Success">}}![](rack_3.png){{</tab>}}
{{</tabs>}}
