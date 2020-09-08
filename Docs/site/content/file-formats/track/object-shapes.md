---
title: "ArgDocs: F1GP Track File Format - Object Shapes"
---

# Object Shapes (Track File Format)

This data contains the 3D representation of various track-side objects such as
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


## Object Shape Details

Object shapes contain the data that represents the points, polygons and vectors of the 3D object.


<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column-25">Type</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>short</td>
            <td>Unique header value, meaning unknown</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Offset to the <a href="#scale-values">Scale value</a> data</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Header value "2", see <a href="#header-values">Header values</a> below</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Offset to the <a href="#graphical-elements-data">Graphical elements</a> data</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Header value "3", see <a href="#header-values">Header values</a> below</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Offset to the <a href="#point-data">Point data</a></td>
        </tr>
        <tr>
            <td>short</td>
            <td>Header value "4", see <a href="#header-values">Header values</a> below</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Offset to the <a href="#vector-data">Vector data</a></td>
        </tr>
        <tr>
            <td>short</td>
            <td>Header value "5", see <a href="#header-values">Header values</a> below</td>
        </tr>
        <tr>
            <td>bytes (always 10)</td>
            <td>
                Unknown data, always 10 bytes long (possibly related to the
                following graphical element data)
            </td>
        </tr>
        <tr>
            <td>short</td>
            <td>Offset to <a href="#graphical-elements-list-data">graphical element list</a> data (?)</td>
        </tr>
        <tr>
            <td>short</td>
            <td>Header value "6", see <a href="#header-values">Header values</a> below</td>
        </tr>
        <tr>
            <td>byte (0 or 10)</td>
            <td>Unknown data. 10 bytes long if it exists. The only tracks that have objects where
            this data exists are Hockenheim, Spa, Monza and Adelaide</td>
        </tr>
        <tr>
            <td>bytes (length varies)</td>
            <td><a href="#scale-values">Scale value</a> data.</td>
        </tr>
        <tr>
            <td>bytes (length varies)</td>
            <td><a href="#graphical-elements">Graphical elements</a> data.</td>
        </tr>
        <tr>
            <td>bytes (length varies)</td>
            <td><a href="#point-data">Point</a> data.</td>
        </tr>
        <tr>
            <td>bytes (length varies)</td>
            <td><a href="#vector-data">Vector</a> data.</td>
        </tr>
        <tr>
            <td>bytes (length varies)</td>
            <td><a href="#graphical-elements-list-data">Graphical element list</a> data</td>
        </tr>
    </tbody>
</table>


### Header values

HeaderValue2, HeaderValue3, HeaderValue4, HeaderValue5 and HeaderValue6
are always identical.

Interestingly, they are also identical to the Unknown2 and Unknown4 values in
the [general track offset](/argdocs/file-formats/track/offsets) data.

This value increases for each track, i.e. Phoenix has the lowest value and
Adelaide has the highest.


### Scale values

This is a list of values (short) that are used in the point data declarations
below.

One or more [points](#point-data) can refer to the same scale value, meaning that
it is easy to resize an object by simply changing a single scale value.


### Graphical Elements data

A graphical element is either a polygon, a bitmap or a line.

_NB: This data is still being investigated and understood, it is possible that
some of the info here is incorrect, and/or will be amended soon._

After a small header which contains which points to calculate, then comes one byte
equal to 0xFF, and after that each element in itself.

To figure out if the upcoming data is a polygon, a bitmap or a line, first read
the byte.


<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="column-30">Value</th>
            <th>Type</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                0x80<br />
                0x88<br />
                0xD0<br />
            </td>
            <td><a href="#bitmap">Bitmap</a></td>
        </tr>
        <tr>
            <td>
                0x82<br />
                0x86<br />
            </td>
            <td><a href="#bitmap">Bitmap</a> (extended)</td>
        </tr>
        <tr>
            <td>0xA0 (160)</td>
            <td><a href="#line">Line</a></td>
        </tr>
        <tr>
            <td>Any other value</td>
            <td><a href="#polygon">Polygon</a>, value indicates color (see below)</td>
        </tr>
    </tbody>
</table>


#### Polygon

Each polygon has the same structure, and can contain between 3 and 12 sides
(plus twinned polygons).

Sides are read until the end of the list is reached (at 0x00).

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th>Item</th>
            <th>Size</th>
            <th class="column-50">Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Color</td>
            <td>unsigned byte</td>
            <td>
                The color in the <a href="/argdocs/misc/palette/">palette</a>.
                May be affected by the <em>Unknown</em> value in the
                <a href="/argdocs/file-formats/track/object-settings/">object setting</a>
                that implements the object shape.
            </td>
        </tr>
        <tr>
            <td>Side <em>n</em></td>
            <td>signed byte</td>
            <td></td>
        </tr>
        <tr>
            <td>End</td>
            <td>unsigned byte</td>
            <td>Always zero</td>
        </tr>
    </tbody>
</table>

Each side points to a vector, so to obtain the points that make the polygon,
according to sign you just pick the start point (+ sign)
or the end point (- sign) for each.


#### Bitmap

Bitmap images can be placed in the 3D objects.

For example, each pillar in the tunnel in Monaco is a bitmap.

The purpose of the initial value of the bitmap (0x80, 0x88, 0xD0 or - for extended bitmaps - 0x82 and 0x86)
is not known.

The total length of a bitmap element (including the initial flag) is either 4 ("normal" bitmaps)
or 6 bytes ("extended" bitmaps).

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th>Item</th>
            <th>Size</th>
            <th class="column-50">Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Flag</td>
            <td>byte</td>
            <td>
                0x80, 0x88 or 0xD0 for "normal" bitmaps,
                0x82 or 0x86 for extended bitmaps
            </td>
        </tr>
        <tr>
            <td>Point</td>
            <td>byte</td>
            <td>The <a href="#point-data">point</a> where the bitmap is placed.</td>
        </tr>
        <tr>
            <td>Unknown flag</td>
            <td>byte</td>
            <td>Various values, e.g. 0xFF</td>
        </tr>
        <tr>
            <td>Bitmap index</td>
            <td>byte</td>
            <td>The <a href="/argdocs/track-data/trackside-objects">index of the bitmap</a></td>
        </tr>
        <tr>
            <td>Additional data 1</td>
            <td>byte</td>
            <td>Purpose unknown, only exists in extended bitmaps</a></td>
        </tr>
        <tr>
            <td>Additional data 2</td>
            <td>byte</td>
            <td>Purpose unknown, only exists in extended bitmaps</a></td>
        </tr>
    </tbody>
</table>


#### Line

A line is a single black line from one point to another.

The length of a line definition is always 3 bytes.

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th>Item</th>
            <th>Size</th>
            <th class="column-50">Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Flag</td>
            <td>byte</td>
            <td>Always 0xA0</td>
        </tr>
        <tr>
            <td>Unknown flag</td>
            <td>byte</td>
            <td>Always 8, except for a single object where it is 0.</td>
        </tr>
        <tr>
            <td>Vector? Point?</td>
            <td>byte</td>
            <td>Indicates a line</td>
        </tr>
    </tbody>
</table>

After an element has been read and parsed, read the next byte to identify the
next kind of element, and so on.


### Point data

There are two types of points. Those that use scale values for their X and Y coordinates,
and those that simply reference another point to use the same X and Y coordinates as the original point.

The Z coordinate can always be set separately for each point, both for scale points and
reference points.

_This section will be expanded_


### Vector data

This is a list of point "pairs", defining the point that a vector goes from and to.

Objects that have no 3D content (such as the pit crew) do not have any vector data.


### Graphical Elements list data

Not much is known about this yet.


## Examples

[Object Shape Examples](/argdocs/file-formats/track/object-shape-examples/)



## Misc

Related: http://www.grandprix2.de/Anleitung/tutus/3D_Object_Editing/3d_object_editing.htm


For a list of the 3D objects in the game,
see the [Track-side 3D objects](/argdocs/track-data/trackside-objects-3d/) list

[Back to F1GP Track File Format](/argdocs/file-formats/track/)
