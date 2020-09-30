# Fuzz Bucket

Version: 1.1
Date: 2018-08-11

The Fuzz Bucket is an 8HP eurorack fuzz and delay module design
submission for the
[2018 Synthcube Module Design Contest](https://www.muffwiggler.com/forum/viewtopic.php?f=4&t=200914).
It is made up of a two transistor fuzz circuit and an MN3005 bucket
brigade delay (BBD). Unlike most delay implementations which aim to
mask sampling and reconstruction error, the Fuzz Bucket provides
direct unfiltered access to delay line inputs and outputs as well
as override of the BBD clock. All of the aliasing, distortion,
and clock noise peculiar to bucket brigade delay is celebrated
as a primary effect instead of being hidden away as an unwanted
problem. In addition, a silicon "fuzz face" is grafted onto
one of the audio inputs, to add some extra colour.

## Overview

![Display Arrangement](fuzzbucket_block.svgz "Block Diagram")

Two audio inputs are scaled and mixed before being fed into
a 4096 stage delay line. Input channel A passes through
a two transistor fuzz circuit, while input channel B is
passed through unmodified. When nothing is patched into an
input, it is fed with a copy of the module output.

A two-phase clock drives the bucket brigade delay line from
an input signal at one half the frequency input. When
no external clock signal is patched in, an internally generated
clock signal is used.

## Controls & Connections

 - Internal rate control - sets the rate of the internal
   clock generator from roughly 3kHz to 3MHz. Above 200kHz
   (roughly 4 o'clock position), the MN3005 BBD is overclocked.

 - External clock override - AC coupled BBD clock override
   input. Any signal with at least 2V of swing between high
   and low values can be used. Note that the BBD frequency
   is one half that of the input clock. When no connector
   is present, the internal clock is routed to the BBD.

 - Clock output - outputs a copy of the internal clock,
   even when an external override is present.

 - Input A fuzz amount - controls how much fuzz is applied
   to the signal on input A.

 - Input A level - adjusts the level of fuzzed signal from
   input A that is fed into the delay line.

 - Input B level - adjusts the level of clean signal from
   input B that is fed into the delay line.

 - Input A - AC coupled signal input routed through
   a fuzz circuit before being fed into the delay line.
   When no connector is present, this input is shorted to the
   module output.

 - Input B - AC coupled signal input fed into the delay line.
   When no connector is present, this input is shorted to the
   module output.

 - Outputs - Two copies of the module output.

## Availability

Full and partial kit options available at
[Synthcube](https://synthcube.com/cart/tags/fuzzbucket).

## Links

 - Schematic: [PDF](fuzzbucket_schematic-1.1.pdf)
 - BoM: [CSV](fuzzbucket_bom.csv)
 - Muff Wiggler: [fuzzbucket delay/fuzz euro SMT 8hp](https://muffwiggler.com/forum/viewtopic.php?f=17&t=214588): 
 - Synthcube: [https://synthcube.com/]

## Acknowledgements

The fuzz block applied to input A is a crude adaptation
of the classic two transistor fuzz face circuit as published on
[ElectroSmash](https://www.electrosmash.com/fuzz-face)
utilising notes on the use of silicon transistors in 
[The Technology of the Fuzz Face](http://www.geofex.com/Article_Folders/fuzzface/fftech.htm)
by R. G. Keen.

The delay core and the two-phase clock that drives it is based
on a circuit published in Barry Klein's Electronic Music Circuits.

## License

CC0 (Public Domain)

