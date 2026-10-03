+++
draft = true
title = 'DEC GIGI'
+++

The DEC GIGI (a.k.a. the VK100) is a color graphics terminal from 1981.

### Bring-Up


### Whitening

I have had good luck bleaching yellowed plastic in a bath of drug store hydrogen peroxide, so I waited for a sunny day and soaked the GIGI's case for a few hours. The effect is pretty dramatic.

![](whitening_1.png "Bleached top, unbleached bottom.")

The final result was really excellent. Quite happy with it.

![](whitening2.png)

### Serial Line Interposer

One of the baffling things about the GIGI is that it doesn't have hardware flow control; it relies on XON/XOFF characters in the serial data stream (software flow control) rather than using the CTS/RTS signals on the RS-232. My Altair's serial card doesn't support software flow control (nor does CP/M) so it was very easy to overrun the GIGI's input buffer and end up with missing or garbled text.

To fix this I built a little microcontroller circuit that intercepts XON/XOFF and toggles the CTS line in response, effectively turning the GIGI's software flow control into hardware flow control. I added an LED that lights up when the serial stream is paused and the GIGI is catching up.

<video src="interposer.mp4" controls>Your browser does not support the video tag.</video>

It worked great, so I turned it into a little board. My serial card has the ability to supply +12V on pin 9 (normally unused) so I took advantage of this to run the interposer without an external power connection.

![](interposer.png "The interposer board, with its embarrassingly over-powered microcontroller.")

