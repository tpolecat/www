+++
date = '2026-09-17T13:28:53-05:00'
draft = true
title = 'GALs by Example, Part 3'
+++

<!--more-->

### GAL16V8 in Registered Mode

![](registered.svg)


### A Parallel-Load Shift Register

![](shift.svg)

```pld {filename="shift.pld"}
GAL16V8
SHIFT

CLK /LOAD /CLR D3 D2 D1 D0 NC SDIN GND
/OE SDOUT  NC  Q3 Q2 Q1 Q0 NC NC   VCC

Q0.R    = /CLR &  LOAD & D0
        # /CLR & /LOAD & SDIN

Q1.R    = /CLR &  LOAD & D1
        # /CLR & /LOAD & Q0

Q2.R    = /CLR &  LOAD & D2
        # /CLR & /LOAD & Q1

Q3.R    = /CLR &  LOAD & D3
        # /CLR & /LOAD & Q2

SDOUT.R = /CLR & /LOAD & Q3

DESCRIPTION
A 4-bit parallel load shift register.
```


```xml {filename="buffer.xml"}
<?xml version="1.0" encoding="utf-8"?>
<logicic>
  <database type="LOGIC">
    <custom name="whatever-you-want">
      <ic name="shift" type="5" voltage="5V" pins="20">

          <vector> C 01 1011 X X G 0 L X HLHH XXV </vector> <!-- Load -->
          <vector> X XX XXXX X X G 1 Z X ZZZZ XXV </vector> <!-- Disable -->
          <vector> X XX XXXX X X G 0 L X HLHH XXV </vector> <!-- Enable -->
          <vector> C 11 XXXX X 0 G 0 H X LHHL XXV </vector> <!-- Shift a 0 -->
          <vector> C 11 XXXX X 1 G 0 L X HHLH XXV </vector> <!-- Shift a 1 -->
          <vector> C 11 XXXX X 1 G 0 H X HLHH XXV </vector> <!-- Shift a 1 -->
          <vector> C X0 XXXX X X G 0 L X LLLL XXV </vector> <!-- Clear -->
          
        </ic>
    </custom>
  </database>
</logicic>    
```

