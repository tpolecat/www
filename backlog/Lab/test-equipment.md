# Test Equipment

## Modern Test Equipment

There's kind of a chicken-and-egg problem with used instrumentation, because you need working instruments in order to repair and calibrate old instruments. So my approach at first was to buy new, good quality hobbyist-level instruments rather than cheaper, better, likely-broken instruments on eBay.

- [**Korad KA3005P**](https://www.amazon.com/dp/B0085QLNFM?th=1). This is a very nice 30V, 5A linear bench power supply that's only 10" deep so it fits on my shelf. I have two of them and want to get a third (a lot of old boards want +5 and then +/-12). This is still cheaper than a good 3-rail power supply.
- [**EEVblog BM786 Multimeter**](https://eevblog.store/products/eevblog-bm786-multimeter). I use a multimeter more than any other tool and I think this is generally true for anyone who works with electronics. I started out wih a much cheaper [**Extech EX330**](https://www.amazon.com/gp/product/B000EX0AE4?th=1) and it's great, but I recently got the Brymen as a gift and I really like the extra precision and faster response. I also have an inexpensive [**xxx**]() clamp meter but haven't needed to use it much. Seems to work fine.
- [**Rigol DS1202Z-E Digital Oscilloscope**](https://www.amazon.com/gp/product/B08HQL386T). This scope works great and I love it, but I wasn't sure what I needed at the time and I should have gotten a lower-bandwidth scope with 4 channels. I was looking specifically for a scope with protocol decoding (SPI, I2C, RS232, etc.) and I have used that feature a lot.
- [**UNI-T UTG962E Arbitrary Waveform Generator**](https://www.amazon.com/UNI-T-UTG962E-Arbitrary-Generator-Dual-Channel/dp/B0BP6TZCRK). When I was just doing digital circuits I got by just fine using a 555 timer to generate square waves, but once I started playing around with analog I really needed a true function generator. This one works great. My only complaint is that there's no built-in way to make it generate a set number of pulses.
- [**Component Tester**].
- [**DreamSourceLab DSLogic Plus**](https://www.amazon.com/DreamSourceLab-USB-Based-Analyzer-Sampling-Interface/dp/B08C2QN9GQ?th=1). Build quality is fantastic and the software works well, but keep in mind that modern logic analyzers are most intended for serial protocols like SPI and I2C; they don't have enough probes to look at parallel buses and the software can't deal with them anyway. So I use my HP 1661A (see below) for computer work.
- [**Bus Pirate**](). In principle this is a cool tool for playing around with components, but I haven't had a lot of luck with it and the documentation isn't very good. I like the idea though.
- [**Hantek 1833C LCR Meter**](https://www.amazon.com/gp/product/B0BWRWMF4Y?th=1). I got this instrument specifically so I could check capacitors on old computers I'm repairing. Works great.
- [**82¢ Logic Probe**](https://www.aliexpress.us/item/3256801412362236.html). These things are basically free and they're great. I got a bag of them from AliExpress use them all the time.
- Test Leads, Mini Grabbers

## Vintage Test Equipment

After a while I gained enough confidence to try out old instruments and was able to get all of them working.

- [**Tektronix 2213 Analog Oscilloscope**](). Digital scopes aren't very good for x-y displays, so I got this scope to use with my [Scopetrex]() and curve tracer (see below). Most of the knobs had broken off so I [printed]() new ones.
- [**HP 4957A Protocol Analyzer**](https://www.curiousmarc.com/instruments/hp-4957a-protocol-analyzer). I got this for debugging serial issues and also so I would have a nice portable VT-100 compatible terminal. It had a weird defect that took a long time to find, but the [repair]() was easy.
- [**HP 1661A Logic Analyzer**](). Modern logic analyzers like the DSLogic Plus (above) are small and very fast but don't provide many channels. Older logic analysers on the other hand are big and slow (by modern standards) but provide a huge number of channels, allowing you to probe essentially every line in a vintage computer at the same time. This was the key to diagnosing and repairing the [GIGI].
- [**Heathkit IT-1121 Semiconductor Curve Tracer**](). This was in the free pile at VCFSW! It's a really nice transistor/diode tester that uses an analog oscilloscope as its display. "Real" curve tracers like the Tektronix 576 are huge and very expensive and definitely beyond my ability to repair, so I'm really pleased to have found this one.
- [Heathkit IC tester]

## Loser Test Equipment

Some stuff that didn't work out:

- **Current-Unlimited Power Supplies**. When I first got started I had a bunch of little 5V power supplies to use with breadboards, and a variable power brick with a little dial for adjusting voltage. These problem is that they're not current-limited, so it's very easy to burn up parts when I put them in backwards.
