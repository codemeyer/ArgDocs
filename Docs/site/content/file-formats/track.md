---
title: "ArgDocs: F1GP Track File Format"
---

# F1GP Track File Format

The game comes with the 16 tracks used in the 1991 F1 season, with tracks as varied as
the tight streets of Monaco to the long, long straights of Hockenheim.

The track files are named "F1CTxx.DAT", where "xx" is a number from "01" to "16".

Because of the similarity between the F1GP and GP2 file formats, a lot of the information below
has been deduced using Maxime Labelle's
["The Grand Prix 2 Track File Format (Beta 0.5)"](http://www.waa63.ch/racesim/TEIC/primer/GP2TrackFileFormat.htm)
and by playing around with Paul Hoad's GP2 Track Editor. Another invaluable resource has been
the [Chequered Flag](http://chequeredflag.sourceforge.net/) F1GP track editor by Barrie Millar, Klaus Six and René Smit.
René Smit has also contributed a large amount of research, particularly regarding the
camera definitions and computer car behavior.


<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>File Info</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Size</td>
            <td>Varying (original tracks between 13,368 to 20,497 bytes)</td>
        </tr>
        <tr>
            <td>Checksum?</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>

The documentation below uses "$..." to describe a location in the file,
and "0x.." to describe a hex value.


## Horizon Image

The first 4,096 bytes represent the horizon image, as a 512 x 8 bitmap.
This means that the first 512 bytes represent the first horizontal line of the image,
the next 512 bytes are the second line, etc.

Each byte indicates the color in the [palette](/argdocs/misc/palette/).


## Offsets

The Offset section begins at $1000.

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>Position</th>
            <th>Description</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$1000</td>
            <td>Unknown Long 1</td>
            <td></td>
        </tr>
        <tr>
            <td>$1004</td>
            <td>Unknown Long 2</td>
            <td></td>
        </tr>
        <tr>
            <td>$1008</td>
            <td>Checksum offset</td>
            <td>Add 0x1010 (4112) to get location in file</td>
        </tr>
        <tr>
            <td>$100A</td>
            <td>Object list data offset</td>
            <td>Add 0x1010 (4112) to get location in file</td>
        </tr>
        <tr>
            <td>$100C</td>
            <td>Track data offset</td>
            <td>Add 0x1010 (4112) to get location in file</td>
        </tr>
    </tbody>
</table>


## Object Shapes

This data contains the 3D representation of various track side objects such as
buildings, billboards and grandstands.

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="text-right">Position</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">$100E</td>
            <td>Number of object shapes</td>
        </tr>
        <tr>
            <td class="text-right">$1010</td>
            <td>Offset of first internal object</td>
        </tr>
        <tr>
            <td class="text-right">+4*n</td>
            <td>Offset of <em>n</em>'th internal object</td>
        </tr>
    </tbody>
</table>

The shape data for each object starts at the offsets specified.
For each item in the list of offsets, data goes from offset position to
last byte before next offset.

For the last item, the shape data ends when we reach the $100A object list data offset.


### Object Shape Details

These are still not fully decomposed, but contain an identifier, a number of offsets, and
varying amounts of data at these offsets. Most likely, the data represents points, lines,
polygons, etc, to create a 3D object.

The 3D objects in GP2 are built up in a similar fashion, and comparing those values to the ones
in F1GP, more info will be discovered.


## Object Settings

16 bytes repeated until we reach the $100C track data header.

The object settings represent instances of 3D objects, or other special objects, that are placed
around the track.

For example, the same 3D object can be reused but with differing rotations, distance from track
and colors.

<table class="table table-bordered table-striped table--medium">
    <thead>
    <tr>
        <th>Field</th>
        <th>Type</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>Id</td>
        <td>byte</td>
        <td>
            If 17 or greater, represents the Id of the 3D object defined
            at index (Id-17) in the Object Shape section.
        </td>
    </tr>
    <tr>
        <td>Detail Level</td>
        <td>byte</td>
        <td>Flag determining which detail levels will show the object, and also affects drawing order</td>
    </tr>
    <tr>
        <td>Unknown</td>
        <td>short</td>
        <td>Possibly color related for 3D objects</td>
    </tr>
    <tr>
        <td>Distance from Track</td>
        <td>short</td>
        <td>
            The distance between the object and the center of the track, negative values
            indicate left side, positive values indicate right side
        </td>
    </tr>
    <tr>
        <td>Angle X</td>
        <td>short</td>
        <td>Angle X</td>
    </tr>
    <tr>
        <td>Angle Y/Z</td>
        <td>short</td>
        <td>
            Angle Y/Z, except when Id=5, then it represents the index of
            a <a href="/argdocs/track-data/trackside-objects/">track-side object</a>
        </td>
    </tr>
    <tr>
        <td>Unknown 2</td>
        <td>short</td>
        <td>Possibly related to drawing order</td>
    </tr>
    <tr>
        <td>Height</td>
        <td>short</td>
        <td>Height above ground</td>
    </tr>
    <tr>
        <td>Id2</td>
        <td>short</td>
        <td>Sub-Id?</td>
    </tr>
    </tbody>
</table>

The first 17 (or so) object settings for each track are very similar, and refer to such items as road signs, etc.


## Track Data Header

The track data header starts at the short value at $100C + 0x1010, e.g. $384A for the Phoenix track.
This is the starting position called $TDH in the table below.

The header is either 28 or 32 bytes long depending on whether the kerbs have two or three colors.

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="text-right">Field</th>
            <th>Type</th>
            <th>Description</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">$TDH</td>
            <td>short</td>
            <td>Starting angle of first track segment</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+2</td>
            <td>short</td>
            <td>Starting height of first segment</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+4</td>
            <td>short</td>
            <td>X-coordinate of track center</td>
            <td>? in GP2</td>
        </tr>
        <tr>
            <td class="text-right">+6</td>
            <td>short</td>
            <td>Z-coordinate of track center</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+8</td>
            <td>short</td>
            <td>Y-coordinate of track center</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+10</td>
            <td>short</td>
            <td>Start width of 1st track segment</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+12</td>
            <td>short</td>
            <td>Pole position side</td>
            <td>768 = right, -768 = left</td>
        </tr>
        <tr>
            <td class="text-right">+14</td>
            <td>short</td>
            <td>Pit side</td>
            <td>0 = right, ? = left</td>
        </tr>
        <tr>
            <td class="text-right">+15</td>
            <td>byte</td>
            <td>Surrounding area color</td>
            <td>0 = green, 0xC0/192 = gray, 128=gray</td>
        </tr>
        <tr>
            <td class="text-right">+16</td>
            <td>byte</td>
            <td>Starting width of right verge</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+17</td>
            <td>byte</td>
            <td>Starting width of left verge</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+18</td>
            <td>byte</td>
            <td>Kerb type (two or three colors)</td>
            <td>4 = three colors, otherwise 3</td>
        </tr>
        <tr>
            <td class="text-right">+19</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+20</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 8</td>
        </tr>
        <tr>
            <td class="text-right">+21</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+22</td>
            <td>byte</td>
            <td>Kerb upper color</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+23</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+24</td>
            <td>byte</td>
            <td>Kerb lower color</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+25</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+26</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 8</td>
        </tr>
        <tr>
            <td class="text-right">+27</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+28</td>
            <td>byte</td>
            <td>Kerb upper color 2 (if triple color)</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+29</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+30</td>
            <td>byte</td>
            <td>Kerb lower color 2 (if triple color)</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+31</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


## Track Sections

After the track data header comes the different track section.

Each track section can have a number of related [track commands](/argdocs/track-data/track-commands/) defined.
Commands are defined _before_ the section that they belong to.

The track section attributes are 10 bytes long.

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th>Field</th>
        <th>Type</th>
        <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>Section Length</td>
        <td>ushort</td>
        <td>Length of section in units of 16 feet (approx 4.87m)</td>
    </tr>
    <tr>
        <td>Arc</td>
        <td>short</td>
        <td>Angle value as a signed integer</td>
    </tr>
    <tr>
        <td>Height</td>
        <td>short</td>
        <td>Height gradient along the section</td>
    </tr>
    <tr>
        <td>Flags</td>
        <td>short</td>
        <td>Various flags, see below</td>
    </tr>
    <tr>
        <td>Right verge width</td>
        <td>byte</td>
        <td>Width of right verge</td>
    </tr>
    <tr>
        <td>Left verge width</td>
        <td>byte</td>
        <td>Width of left verge</td>
    </tr>
    </tbody>
</table>

Track section definitions end with 0xFF FF.


### Track Section Flags

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="text-right">Bit</th>
            <th>Description</th>
            <th>Comment</th>
            <th>Hex</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">0</td>
            <td>Pitlane entrance</td>
            <td>Used on all pit lane sections that have garages?</td>
            <td>0x1</td>
        </tr>
        <tr>
            <td class="text-right">1</td>
            <td>Pitlane exit</td>
            <td>Used on all pit lane sections that have garages?</td>
            <td>0x2</td>
        </tr>
        <tr>
            <td class="text-right">2</td>
            <td>Kerb height selector</td>
            <td>Set for low kerbs, not set for high kerbs</td>
            <td>0x4</td>
        </tr>
        <tr>
            <td class="text-right">3</td>
            <td>Road signs (300/200/100)</td>
            <td></td>
            <td>0x8</td>
        </tr>
        <tr>
            <td class="text-right">4</td>
            <td>
                Join the right-side fence from the starting point of the
                section with the starting point of the next non-bridged section.
            </td>
            <td></td>
            <td>0x10</td>
        </tr>
        <tr>
            <td class="text-right">5</td>
            <td>
                Join the left-side fence from the starting point of the
                section with the starting point of the next non-bridged section.
            </td>
            <td></td>
            <td>0x20</td>
        </tr>
        <tr>
            <td class="text-right">6</td>
            <td>Road sign (arrow)</td>
            <td></td>
            <td>0x40</td>
        </tr>
        <tr>
            <td class="text-right">7</td>
            <td>Road signs (arrow/100)</td>
            <td></td>
            <td>0x80</td>
        </tr>
        <tr>
            <td class="text-right">8</td>
            <td>Unknown 1</td>
            <td>Never used in default tracks</td>
            <td>0x100</td>
        </tr>
        <tr>
            <td class="text-right">9</td>
            <td>Unknown 2</td>
            <td>Never used in default tracks</td>
            <td>0x200</td>
        </tr>
        <tr>
            <td class="text-right">10</td>
            <td>Right Kerb</td>
            <td>Section has kerb on the right side of the track</td>
            <td>0x400</td>
        </tr>
        <tr>
            <td class="text-right">11</td>
            <td>Left Kerb</td>
            <td>Section has kerb on the left side of the track</td>
            <td>0x800</td>
        </tr>
        <tr>
            <td class="text-right">12</td>
            <td>Remove Right Wall</td>
            <td>Hides the right wall, can still be hit</td>
            <td>0x1000</td>
        </tr>
        <tr>
            <td class="text-right">13</td>
            <td>Remove Left Wall</td>
            <td>Hides the left wall, can still be hit</td>
            <td>0x2000</td>
        </tr>
        <tr>
            <td class="text-right">14</td>
            <td>Unknown 3</td>
            <td></td>
            <td>0x4000</td>
        </tr>
        <tr>
            <td class="text-right">15</td>
            <td>Unknown 4</td>
            <td>Never used in default tracks</td>
            <td>0x8000</td>
        </tr>
    </tbody>
</table>

Road sign flags can be combined in various ways, e.g. by setting both bit 3 and 6,
the signs will appear on track as 300/Arrow/100.


## Best Line Segments

This defines the line that computer cars drive around the track, and also applies
steering help to the player's car, especially keyboard users.

The first segment is always 8 bytes long, defined like this:

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>Field</th>
            <th>Type</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Length</td>
            <td>byte</td>
            <td>Length of first segment</td>
        </tr>
        <tr>
            <td></td>
            <td>byte</td>
            <td>Always 0x80 (128)</td>
        </tr>
        <tr>
            <td>Displacement</td>
            <td>short</td>
            <td></td>
        </tr>
        <tr>
            <td>Correction</td>
            <td>short</td>
            <td></td>
        </tr>
        <tr>
            <td>Radius</td>
            <td>short</td>
            <td></td>
        </tr>
    </tbody>
</table>

After this, a number of segments appear. The segments are of two kinds, either
"Normal" or a "Wide Radius" variant.
The "Wide Radius" version is used for pieces of track that have a very long
curvature, e.g. the back straight between turns 7 and 8 at Montreal which isn't really a straight, but
in fact a very long curve. Of the total number of best line segments,
"Wide Radius" segments don't appear very often. In fact, they only account for around 1% of all best line segments.

The type of segment is identified by the second byte in each segment.

Normal segments, 6 bytes long:

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>Field</th>
            <th>Type</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Length</td>
            <td>byte</td>
            <td>Length of segment</td>
        </tr>
        <tr>
            <td></td>
            <td>byte</td>
            <td>Always 0x00</td>
        </tr>
        <tr>
            <td>Correction</td>
            <td>short</td>
            <td></td>
        </tr>
        <tr>
            <td>Radius</td>
            <td>short</td>
            <td>Positive values for right-hand turns, negative values for left-hand turns. Smaller value for sharper turns.</td>
        </tr>
    </tbody>
</table>

Wide radius segments, 8 bytes long:

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>Field</th>
            <th>Type</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Length</td>
            <td>byte</td>
            <td>Length of segment</td>
        </tr>
        <tr>
            <td></td>
            <td>byte</td>
            <td>Always 0x40</td>
        </tr>
        <tr>
            <td>Correction</td>
            <td>short</td>
            <td></td>
        </tr>
        <tr>
            <td>High Radius</td>
            <td>short</td>
            <td></td>
        </tr>
        <tr>
            <td>Low Radius</td>
            <td>short</td>
            <td></td>
        </tr>
    </tbody>
</table>

The Best Line Segment part of the file is ended by two null values, i.e. 0x00 00.


## Computer Car Setup and Behavior

Contains the [default computer car setup](/argdocs/track-data/default-setups/),
and various computer car behavior.

Always 38 bytes.

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="text-right">Index</th>
            <th>Type</th>
            <th>Description</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">$CCS</td>
            <td>byte</td>
            <td>Front wing</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+1</td>
            <td>byte</td>
            <td>Rear wing</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+2</td>
            <td>byte</td>
            <td>1st Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+3</td>
            <td>byte</td>
            <td>2nd Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+4</td>
            <td>byte</td>
            <td>3rd Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+5</td>
            <td>byte</td>
            <td>4th Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+6</td>
            <td>byte</td>
            <td>5th Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+7</td>
            <td>byte</td>
            <td>6th Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+8</td>
            <td>byte</td>
            <td>Tyre Compound</td>
            <td>52=A, 55=D, actual compound used may vary</td>
        </tr>
        <tr>
            <td class="text-right">+9</td>
            <td>byte</td>
            <td>Brake Balance</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+10</td>
            <td>short</td>
            <td>Grip Factor</td>
            <td>Multiplies driver corner speed factor</td>
        </tr>
        <tr>
            <td class="text-right">+12</td>
            <td>short</td>
            <td>CC non-race late braking factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+14</td>
            <td>short</td>
            <td>CC race late braking factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+16</td>
            <td>short</td>
            <td>Time factor non-race</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+18</td>
            <td>short</td>
            <td>Acceleration</td>
            <td>16384 everywhere except Mexico, where it's 13017</td>
        </tr>
        <tr>
            <td class="text-right">+20</td>
            <td>short</td>
            <td>Air Resistance</td>
            <td>16384 everywhere except Mexico, where it's 13017</td>
        </tr>
        <tr>
            <td class="text-right">+22</td>
            <td>short</td>
            <td>Tyre wear qualifying</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+24</td>
            <td>short</td>
            <td>Tyre wear non-qualifying</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+26</td>
            <td>short</td>
            <td>Fuel load</td>
            <td>100% race, measured in pounds (lbs). Fuel is consumed linearly with the distance covered. Shorter races decrease the fuel load.</td>
        </tr>
        <tr>
            <td class="text-right">+28</td>
            <td>short</td>
            <td>Time factor race</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+30</td>
            <td>short</td>
            <td>CC power factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+32</td>
            <td>short</td>
            <td>CC wet race late braking factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+34</td>
            <td>short</td>
            <td>Unknown</td>
            <td>Some track distance in feet</td>
        </tr>
        <tr>
            <td class="text-right">+36</td>
            <td>short</td>
            <td>Default pit lane view distance</td>
            <td></td>
        </tr>
    </tbody>
</table>



## Pit lane sections

Defined in exactly the same way as <a href="#track-sections">track sections</a>.



## Camera Definitions

By default, the game places a camera at the left side of every 16 track length units. The command definitions
here can then move them further back, swap them to the right side, or just remove them.

Variable length from 14 bytes (Phoenix) to 60 (Spa-Francorchamps)

Terminated by 0xFF FF

<!-- TODO: table? -->


## Computer Car Behavior, etc

Always 28 bytes

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="text-right">Field</th>
            <th>Type</th>
            <th>Description</th>
            <th class="text-right">Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">Unknown 1</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 00</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 2</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 01</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 3</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 02</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 4</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 03</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 5</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. 04 for slow tracks (US,MON,HUN,AUS), otherwise always 09</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 6</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 05</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 7</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 06</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 8</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 07</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 9</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 08</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 10</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 09</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 11</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 10</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 12</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. 11 for slow tracks (US,MON,HUN,AUS), otherwise always 02</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 13</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 12</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 14</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 13</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 15</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 14</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 16</td>
            <td>byte</td>
            <td>?</td>
            <td class="text-right">Possibly not used. Known values: 15</td>
        </tr>

        <tr>
            <td class="text-right">Formation Length</td>
            <td>short</td>
            <td>Cars will not steer left/right until this segment index at the start of the race</td>
            <td class="text-right">Known values: 20, 35, 50, 118, 200, 203</td>
        </tr>
    <tr>
        <td class="text-right">Lap time indication (ms)</td>
        <td>int</td>
        <td>
            Used in calculation of maximum number of runners non-race and hotseat duration.
            Divided by (104 * session minutes) for max runners non-race
        </td>
        <td class="text-right">Known values: 86000, 80000, etc</td>
    </tr>
        <tr>
            <td class="text-right">Lap Count</td>
            <td>short</td>
            <td>Lap count for 100% race</td>
            <td class="text-right"></td>
        </tr>

        <tr>
            <td class="text-right">Strategy (lap for first pit stop)</td>
            <td>short</td>
            <td>Close to 33% or 50% race distance</td>
            <td class="text-right">Known values: 26, 27, 30, 37, 39, 43</td>
        </tr>

        <tr>
            <td class="text-right">Strategy chance</td>
            <td>short</td>
            <td></td>
            <td class="text-right"></td>
        </tr>
    </tbody>
</table>

"Known values" are from tracks 01 (Phoenix) to 06 (Mexico City)


## Checksum

The final four (4) bytes of the track contain
the [checksum](/argdocs/misc/checksum/).

If the checksum is incorrect, F1GP will not load the track file.
