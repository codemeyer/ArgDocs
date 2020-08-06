---
title: "ArgDocs: F1GP Track File Format - Racing Line"
---

# Racing Line (Track File Format)

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
            <td>Sideways adjustment of the starting point</td>
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

The _High Radius_ and _Low Radius_ values are combined to provide an effective radius value.

<!-- TODO: high/low radius calculation -->

Note that the effective radius may turn out to be 0, but the racing line will still follow the
curvature of the [track section](/argdocs/file-format/track/track-sections/) it is located at.

The Best Line Segment part of the file is ended by two null values, i.e. 0x00 00.


[Back to F1GP Track File Format](/argdocs/file-formats/track/)
