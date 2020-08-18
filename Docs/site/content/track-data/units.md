---
title: "ArgDocs: Track units"
---

# F1GP Track Units

This page lists a number of units and formulas related to these units.


## Track Length Unit (TLU)

This is used to define the length of a track section, as well as some related properties
in track section commands.

1 TLU is 16 feet, i.e. approx. 4.87 meters.


## Track width

Track widths in F1GP usually range from around 1200 up to 2000.

The formula for turning a track width into meters is:

For the track, divisor = 32768 / 30 (=1092.266666).

For the pit lane, 32768 / 20 (=1638.4)

<em>trackWidth(meters) = (trackWidth(value) * 2 / divisor) * 4.87</em>

So for example, a track width of 1900 is approximately 16.9 meters.


## Verge width

The verge width is relative to the track width. This means that a verge width of 5 will be larger
if the track width is 1900, than if it is e.g. 1200.

The formula for turning the verge width into meters is the following:

First of all, there is a divisor that differs between the track and the pit lane.

For the track, divisor = 32768 / 30 (=1092.266666)

For the pit lane, 32768 / 20 (=1638.4)

The formula is:

<em>vergeWidth = (value * 34.1333 * trackWidth / 1000) / 1092.26666 * 4.87</em>

For example, if the track is 1900 width and the verge has a value of 5, the actual
verge width is approximately 1.45 meters.


The track and verge width formulas were figured out by Robin de Paus.
See <a href="http://www.grandprix2.de/Anleitung/tutus/Command_Lib/command_lib%20gp3%20gp2/cmdlib3a.htm">here</a> for
the original source.
