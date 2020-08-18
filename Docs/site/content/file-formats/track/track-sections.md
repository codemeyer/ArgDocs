---
title: "ArgDocs: F1GP Track File Format - Track Sections"
---

# Track Sections (Track File Format)

A track section describes the length and curvature of a part of the track. Track sections can be thought
of as sections of a [Scalextric](https://en.wikipedia.org/wiki/Scalextric) track.

The track section attributes are 10 bytes long.

Each track section can have a number of related [track commands](/argdocs/track-data/track-section-commands/) defined.
See below.

<table class="table table-bordered table-striped table--medium">
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
        <td>Curvature</td>
        <td>short</td>
        <td>Angle value as a signed integer, see <a href="/argdocs/track-data/corner-geometry/">Corner Geometry</a></td>
    </tr>
    <tr>
        <td>Height</td>
        <td>short</td>
        <td>Height gradient along the section</td>
    </tr>
    <tr>
        <td>Flags</td>
        <td>short</td>
        <td>Various flags, see <a href="#track-section-flags">Track Section Flags</a> below</td>
    </tr>
    <tr>
        <td>Right verge width</td>
        <td>byte</td>
        <td>Width of right verge at the end of the section (and start of the next section)</td>
    </tr>
    <tr>
        <td>Left verge width</td>
        <td>byte</td>
        <td>Width of left verge at the end of the section (and start of the next section)</td>
    </tr>
    </tbody>
</table>

The list of Track section definitions ends with 0xFF FF.



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



### Track Section Commands

Commands are used to perform various modifications to the section it is related to, or to the entire track.

Each track section can have a number of related [track commands](/argdocs/track-data/track-commands/) defined.
Note that commands are defined _before_ the section that they belong to.

Each command can have between 1 and 6 arguments, though for some commands, the first argument has no purpose
and is always zero. There is no value that indicates that the list of
arguments has finished, you have to know how many arguments each command has.

The first argument is only a byte long, because it is "paired" in a _short_ with the command type.
The remaining arguments are short values.

As an example, the 0xAC track command, which defines the color of the grass or tarmac, may look like this:

`0x00 0xAC 0x1A 0x00 0x20 0x00 0x20 0x00 0x1D 0x00`

`0xAC` is the command, and `0x00` is the first argument, which is not used in this command.

After that come the remaining four arguments. The first (0x1A 0x00) indicates whether we are changing the color
of the grass or the tarmac. `0x1A` means the tarmac, both for the track and the surrounding area, since
Phoenix is a street circuit without grass. The remaining three commands specify the RGB values (0 to 63).

In comparison, an instance of the 0x80 track command, which places an object
along the track, may look like this:

`0x13 0x80 0x20 0x01`

Here, `0x80` is the command, and `0x13` is the first argument, which here indicates how far along the
track section the object should be placed. `0x20 0x01` is 288, which is a reference to the
[object setting](/argdocs/file-formats/track/object-settings/) that is used.


[Back to F1GP Track File Format](/argdocs/file-formats/track/)
