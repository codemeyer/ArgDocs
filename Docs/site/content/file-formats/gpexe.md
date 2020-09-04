---
title: "ArgDocs: F1GP GP.EXE"
---

# F1GP GP.EXE

The GP.EXE file contains most data needed by the game, except for various graphical
elements, sounds and the separate track files.

## Data Locations

This represents the zero-based index of the byte in the file where the data ("Item") begins.

In the data below, "dec" indicates a [decompressed EXE](/argdocs/misc/decompressed-exe/)
(using [UNP 4.11](http://unp.bencastricum.nl))

<table class="table table-bordered table-striped">
    <thead>
        <tr>
            <th class="column-40">Item</th>
            <th class="text-right column-15">EU 1.05</th>
            <th class="text-right column-15">US 1.05</th>
            <th class="text-right column-15">EU 1.05 dec</th>
            <th class="text-right column-15">US 1.05 dec</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><a href="#player-horsepower">Player Horsepower</a></td>
            <td class="text-right">19,848</td>
            <td class="text-right">19,848</td>
            <td class="text-right">24,600</td>
            <td class="text-right">24,548</td>
        </tr>
        <tr>
            <td>AI Grip Level</td>
            <td class="text-right">20,183</td>
            <td class="text-right">20,183</td>
            <td class="text-right">24,935</td>
            <td class="text-right">24,919</td>
        </tr>
        <tr>
            <td><a href="#driver-numbers">Driver Numbers</a></td>
            <td class="text-right">154,936</td>
            <td class="text-right">154,892</td>
            <td class="text-right">180,210</td>
            <td class="text-right">180,146</td>
        </tr>
        <tr>
            <td>Team Horsepower</td>
            <td class="text-right">158,380</td>
            <td class="text-right">158,336</td>
            <td class="text-right">183,996</td>
            <td class="text-right">183,932</td>
        </tr>
        <tr>
            <td>Driver Performance Qual.</td>
            <td class="text-right">158,420</td>
            <td class="text-right">158,376</td>
            <td class="text-right">184,036</td>
            <td class="text-right">183,972</td>
        </tr>
        <tr>
            <td>Driver Performance Race</td>
            <td class="text-right">158,460</td>
            <td class="text-right">158,416</td>
            <td class="text-right">184,076</td>
            <td class="text-right">184,012</td>
        </tr>
        <tr>
            <td><a href="#car-colors">Car Colors</a></td>
            <td class="text-right">158,500</td>
            <td class="text-right">158,456</td>
            <td class="text-right">184,116</td>
            <td class="text-right">184,052</td>
        </tr>
        <tr>
            <td><a href="#helmet-colors">Helmet Colors</a></td>
            <td class="text-right">158,795</td>
            <td class="text-right">158,751</td>
            <td class="text-right">184,436</td>
            <td class="text-right">184,372</td>
        </tr>
        <tr>
            <td><a href="#pit-crew-colors">Pit Crew Colors</a></td>
            <td class="text-right">159,421</td>
            <td class="text-right">159,377</td>
            <td class="text-right">185,076</td>
            <td class="text-right">185,012</td>
        </tr>
        <tr>
            <td><a href="#points-system">Points System</a></td>
            <td class="text-right">158,341</td>
            <td class="text-right">158,297</td>
            <td class="text-right">183,940</td>
            <td class="text-right">183,876</td>
        </tr>
        <tr>
            <td>Rain at 1st Track Flag</td>
            <td class="text-right">106,319</td>
            <td class="text-right">106,319</td>
            <td class="text-right">111,746</td>
            <td class="text-right">111,730</td>
        </tr>
        <tr>
            <td>Chance of Rain</td>
            <td class="text-right">58,394</td>
            <td class="text-right">58,394</td>
            <td class="text-right">63,146</td>
            <td class="text-right">63,130</td>
        </tr>
        <tr>
            <td>Yellow Flags period</td>
            <td class="text-right">23,517</td>
            <td class="text-right">23,517</td>
            <td class="text-right">28,269</td>
            <td class="text-right">28,253</td>
        </tr>
        <tr>
            <td>Retired Cars removed</td>
            <td class="text-right">23,631</td>
            <td class="text-right">23,631</td>
            <td class="text-right">28,383</td>
            <td class="text-right">28,367</td>
        </tr>
        <tr>
            <td>Retire after wall hit</td>
            <td class="text-right">125,420</td>
            <td class="text-right">125,376</td>
            <td class="text-right">131,948</td>
            <td class="text-right">131,884</td>
        </tr>
        <tr>
            <td>Retire after car hit</td>
            <td class="text-right">125,422</td>
            <td class="text-right">125,378</td>
            <td class="text-right">131,950</td>
            <td class="text-right">131,886</td>
        </tr>
        <tr>
            <td>Damage after wall hit</td>
            <td class="text-right">125,428</td>
            <td class="text-right">125,384</td>
            <td class="text-right">131,956</td>
            <td class="text-right">131,892</td>
        </tr>
        <tr>
            <td>Damage after car hit</td>
            <td class="text-right">125,426</td>
            <td class="text-right">125,382</td>
            <td class="text-right">131,954</td>
            <td class="text-right">131,890</td>
        </tr>
        <tr>
            <td><a href="#driver-aids">Driver Aids</a></td>
            <td class="text-right">124,159</td>
            <td class="text-right"></td>
            <td class="text-right">129,990</td>
            <td class="text-right"></td>
        </tr>
        <tr>
            <td>Year Level text</td>
            <td class="text-right">193,671</td>
            <td class="text-right"></td>
            <td class="text-right">423,759</td>
            <td class="text-right"></td>
        </tr>
        <tr>
            <td>Car 3D shape</td>
            <td class="text-right"></td>
            <td class="text-right"></td>
            <td class="text-right">159,915 ?</td>
            <td class="text-right"></td>
        </tr>
        <tr>
            <td><a href="#internal-track">Internal track</a></td>
            <td class="text-right">128,261 (chksum offset?)</td>
            <td class="text-right"></td>
            <td class="text-right">143,481 (chksum offset?)</td>
            <td class="text-right"></td>
        </tr>
        <tr>
            <td>...</td>
            <td class="text-right"></td>
            <td class="text-right"></td>
            <td class="text-right"></td>
            <td class="text-right"></td>
        </tr>
        <tr>
            <td>Total File Length</td>
            <td class="text-right">321,878</td>
            <td class="text-right">321,716</td>
            <td class="text-right">600,480</td>
            <td class="text-right">600,304</td>
        </tr>
    </tbody>
</table>

<table class="table table-bordered table-striped">
    <thead>
        <tr>
            <th class="column-55">Item</th>
            <th class="text-right column-15">Ita 1.05</th>
            <th class="text-right column-15">EU 1.03</th>
            <th class="text-right column-15">US 1.03</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Total File Length</td>
            <td class="text-right">321,748</td>
            <td class="text-right">332,890</td>
            <td class="text-right">332,840</td>
        </tr>
    </tbody>
</table>


## Player Horsepower

The player horsepower value is stored as a short (two bytes).

The default horsepower value for a player is 716, but the value that is
actually stored is 16,384.

The formula for transforming a "normal" horsepower value into the value to store is:

<code>value to store = normal hp * 22 + 632</code>

Therefore, to convert a stored value to the "normal" horspower value, the formula is:

<code>normal hp = (stored value - 632) / 22</code>

Given this, the maximum value that can be stored is 1,460. Going above this value
actually creates "negative" horsepower values, meaning that when accelerating in first gear, the
player car will move _backwards_!


## Driver Numbers

The driver numbers list is a list of 40 bytes, where each byte contains the driver number
for that specific slot.

There are two slots for each team. When looking in the driver selection menu, they read
from top to bottom and left to right. So the first two bytes set the numbers for the
two drivers in the first team (default: McLaren), then Tyrrell, Williams, etc.

To disable a driver, set their number to 0.

A minimum of 26 active drivers is needed, otherwise the game will crash.

Also note that driver numbers cannot be higher than 40.

Drivers cannot share numbers.


## Car Colors

Each car is made up of 16 bytes. The 16 bytes for each car repeat 18 times, once for each team.
The team's appear in the order in the game menu, reading from top to bottom and left to right,
i.e. first McLaren, then Tyrrell, then Williams, etc.

<table class="table table-bordered table-striped">
    <thead>
        <tr>
            <th>Pos.</th>
            <th>Polygon</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0</td>
            <td>Tyres, sidepod air intake, lower rear wing elements</td>
            <td>Always 33 (very dark gray) in default data</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Engine cover</td>
            <td>Main/top part of engine cover</td>
        </tr>
        <tr>
            <td>2</td>
            <td>In front of cockpit</td>
            <td>Area at the top of the nose-cone, just in front of the cockpit. Diagonal Marlboro stripe for McLaren.</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Front wing endplates</td>
            <td></td>
        </tr>
        <tr>
            <td>4</td>
            <td>Rear wing sides</td>
            <td></td>
        </tr>
        <tr>
            <td>5</td>
            <td>Side of nose cone</td>
            <td></td>
        </tr>
        <tr>
            <td>6</td>
            <td>Sidepod</td>
            <td></td>
        </tr>
        <tr>
            <td>7</td>
            <td>Front and rear wing</td>
            <td>These are always the same color</td>
        </tr>
        <tr>
            <td>8</td>
            <td>Nose top/center</td>
            <td>The top center part of the nose cone</td>
        </tr>
        <tr>
            <td>9</td>
            <td>Unknown</td>
            <td>Value varies</td>
        </tr>
        <tr>
            <td>10/A</td>
            <td>Tyre accent color</td>
            <td>Always 36, except for Minardi which has 34 (slightly darker)</td>
        </tr>
        <tr>
            <td>11/B</td>
            <td>Nose area</td>
            <td>Part between the top/center and side of the nose cone. Only visible from far on McLaren.</td>
        </tr>
        <tr>
            <td>12/C</td>
            <td>Cockpit side</td>
            <td></td>
        </tr>
        <tr>
            <td>13/D</td>
            <td>Engine cover side</td>
            <td>The "stripe" beneath the main/top part of the engine cover</td>
        </tr>
        <tr>
            <td>14/E</td>
            <td>Engine cover rear</td>
            <td>The end part of the "stripe" on the engine cover</td>
        </tr>
        <tr>
            <td>15/F</td>
            <td>Sidepod top</td>
            <td></td>
        </tr>
    </tbody>
</table>

**Normal Car Shape**

<img alt="Normal car shape" src="/argdocs/images/car-shape-polygons-normal.png" class="img-fluid" />

**Alternate Car Shape (McLaren)**

<img alt="Alternate car shape" src="/argdocs/images/car-shape-polygons-alternate.png" class="img-fluid" />

When cars are far away, the "special" McLaren car shape appears in the same way as the normal car shape.


## Helmet Colors

Most helmets are made up of 16 different bytes. In non-decompressed EXE files, the exceptions
to this are the helmets for drivers with numbers #13, #16, #36, #37, #38, #39 and #40. These
drivers have helmets where the bottom two-thirds will always have the same color.

<img alt="Helmet color index" src="/argdocs/images/helmet-colors.png" class="img-fluid" />

Index 1 is never visible.

The default visor (index 0) color is 0 (black) and the default visor surround (index 6) is 6.


## Pit Crew Colors

Each pit crew has 16 colors. Most of the colors should not be edited, however, since they
are the colors of the jack, skin, etc.

The interesting ones are:

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>Pos.</th>
            <th>Item</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>3</td>
            <td>Socks</td>
            <td></td>
        </tr>
        <tr>
            <td>4</td>
            <td>Pants, secondary color</td>
            <td></td>
        </tr>
        <tr>
            <td>5</td>
            <td>Shirt, secondary color</td>
            <td></td>
        </tr>
        <tr>
            <td>6</td>
            <td>Shirt, primary color</td>
            <td></td>
        </tr>
        <tr>
            <td>11</td>
            <td>Pants, primary color</td>
            <td></td>
        </tr>
    </tbody>
</table>



## Points System

The points system is stored as a list of bytes, where each value contains the number of points
scored for that position. However, the default EXE file is compressed, which means that positions
7 to 26 are hard-coded to 0 due to the compression.

By default, the points are stored as:

`0A 06 04 03 02 01 1C 00`

This is 10, 6, 4, 3, 2 and 1 for the first six finishers. The `1C 00` combo means that the rest are 0.

After [decompressing](/argdocs/misc/decompressed-exe/) the EXE file, the values are instead stored
like this:

`0A 06 04 03 02 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00`

This allows you to edit the points system for each car.

It is important to note that if a driver fails to finish the race, it seems that they will not score
points, even though the final position is a point scoring one. It has not yet been researched if this
is due to the F1 rule about needing to completely a certain percentage of the race to be classified,
or if it's _always_ like this.


## Driver Aids

The driver aids data specifies which aids are available at each skill level (Rookie, Amateur, Semi-Pro, Pro, Ace)

The driver aids data is five bytes long.

For each level, the available aids are a bit flag in the byte (where the two
top bits are ignored, since there are only six aids)

The bits are set from right to left, so considering the bits as flags:

<table class="table table-bordered table-striped table--tiny">
    <thead>
        <tr>
            <th>Bit</th>
            <th>Aid</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>Auto-brakes</td>
            <td><img alt="Auto brakes" src="/argdocs/images/aids/auto-brakes.png" title="Auto brakes" /></td>
        </tr>
        <tr>
            <td>2</td>
            <td>Auto-gears</td>
            <td><img alt="Auto gears" src="/argdocs/images/aids/auto-gear.png" title="Auto gears" /></td>
        </tr>
        <tr>
            <td>4</td>
            <td>Self-correcting spin</td>
            <td><img alt="Self-correcting spin" src="/argdocs/images/aids/self-correcting-spin.png" title="Self-correcting spin" /></td>
        </tr>
        <tr>
            <td>8</td>
            <td>Indestructible</td>
            <td><img alt="Indestructible" src="/argdocs/images/aids/indestructible.png" title="Indestructible" /></td>
        </tr>
        <tr>
            <td>16</td>
            <td>Ideal line</td>
            <td><img alt="Ideal line" src="/argdocs/images/aids/ideal-line.png" title="Ideal line" /></td>
        </tr>
        <tr>
            <td>32</td>
            <td>Suggested gear</td>
            <td><img alt="Suggested gear" src="/argdocs/images/aids/suggested-gear.png" title="Suggested gear" /></td>
        </tr>
    </tbody>
</table>

For instance, the rookie settings bits are:

`00111111` meaning that all aids are available.

While the ace settings bits are:

`00000010` meaning that only auto-gears is available.


## Internal track

Each GP.EXE contains an instance of the Silverstone track (F1CT08.DAT) inside it.
