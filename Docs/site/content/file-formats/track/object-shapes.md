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

Defines polygons, bitmaps, etc.

Each GraphicElement is an N-gon with 3 to 12 sides, plus twinned polygons and bitmaps.
After a small header which contains which points to calculate, then comes one byte
equal to 0xFF, and after that each element in itself. Each polygon has the same structure:

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
                Palette? Possibly affected by another value in the
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

When the object contains a reference to a "flat" object (such as a pit crew or
a tree) then the definition may be slightly different.


### Point data

There are two types of points. Those that use scale values for their X and Y coordinates,
and those that simply reference another point to use the same X and Y coordinates as the original point.

The Z coordinate can always be set separately.

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
