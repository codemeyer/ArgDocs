---
title: "ArgDocs: F1GP Track File Format - Object Shape Examples"
---

# Object Shape Examples (Track File Format)


The following is an example of an ad billboard in the Phoenix track.

From one side:

<img src="/argdocs/images/object-shape-examples/01sh43-1a.png" alt="Object shape example" class="img-fluid" />

And the other side:

<img src="/argdocs/images/object-shape-examples/01sh43-1b.png" alt="Object shape example" class="img-fluid" />

The total length of the data that describes this object is 402 bytes.


## Initial Data

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column 33">Hex</th>
            <th class="column 10">Dec</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>00 06</td>
            <td>1536</td>
            <td>Header</td>
        </tr>
        <tr>
            <td>04 27</td>
            <td>9988</td>
            <td>Offset to scale values</td>
        </tr>
        <tr>
            <td>F5 15</td>
            <td>5621</td>
            <td>Header "2"</td>
        </tr>
        <tr>
            <td>08 27</td>
            <td>9992</td>
            <td>Offset to graphical elements</td>
        </tr>
        <tr>
            <td>F5 15</td>
            <td>5621</td>
            <td>Header "3"</td>
        </tr>
        <tr>
            <td>23 27</td>
            <td>10019</td>
            <td>Offset to point data</td>
        </tr>
        <tr>
            <td>F5 15</td>
            <td>5621</td>
            <td>Header "4"</td>
        </tr>
        <tr>
            <td>63 27</td>
            <td>10083</td>
            <td>Offset to vector data</td>
        </tr>
        <tr>
            <td>F5 15</td>
            <td>5621</td>
            <td>Header "5"</td>
        </tr>
        <tr>
            <td>
                00 00 00 00 FF 7F 00 E0<br />
                0D 00
            </td>
            <td></td>
            <td>Unknown data</td>
        </tr>
        <tr>
            <td>75 27</td>
            <td>10101</td>
            <td>Offset to graphical element data</td>
        </tr>
        <tr>
            <td>F5 15</td>
            <td>5621</td>
            <td>Header "6"</td>
        </tr>
    </tbody>
</table>

Since the scale value offset points to the location we have now reached, there is no additional
10 bytes of unknown data, which occurs in a few objects on some tracks.


## Scale Values

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column-33">Hex</th>
            <th class="column-10">Dec</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>00 06</td>
            <td>1536</td>
            <td>Scale value</td>
        </tr>
        <tr>
            <td>A0 04</td>
            <td>1184</td>
            <td>Scale value</td>
        </tr>
    </tbody>
</table>


## Graphical Elements


<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column-20">Hex</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>00 01</td>
            <td>Header</td>
        </tr>
        <tr>
            <td>FF</td>
            <td>End of header</td>
        </tr>
        <tr>
            <td>08</td>
            <td>Base color of polygon 1 (white, but can be affected by "Unknown" value in an object setting)</td>
        </tr>
        <tr>
            <td>02 03 FC FF</td>
            <td>Points in polygon 1 (signed bytes)</td>
        </tr>
        <tr>
            <td>00</td>
            <td>End of polygon 1</td>
        </tr>
        <tr>
            <td>09</td>
            <td>Base color of polygon 2 (red, but can be affected by "Unknown" value in an object setting)</td>
        </tr>
        <tr>
            <td>05 06 F8 F9</td>
            <td>Points in polygon 2 (signed bytes)</td>
        </tr>
        <tr>
            <td>00</td>
            <td>End of polygon 2</td>
        </tr>
        <tr>
            <td>00</td>
            <td>Base color of polygon 3 (black, but can be affected by "Unknown" value in an object setting)</td>
        </tr>
        <tr>
            <td>07 08 FA FB</td>
            <td>Points in polygon 3 (signed bytes)</td>
        </tr>
        <tr>
            <td>00</td>
            <td>End of polygon 3</td>
        </tr>
        <tr>
            <td>03</td>
            <td>Base color of polygon 4 (yellow, but can be affected by "Unknown" value in an object setting)</td>
        </tr>
        <tr>
            <td>04 FD FE 01</td>
            <td>Points in polygon 4 (signed bytes)</td>
        </tr>
        <tr>
            <td>00</td>
            <td>End of polygon 4</td>
        </tr>
    </tbody>
</table>

On one side of the ad billboard, polygon 1 is the large white area,
which has polygon 2, the smaller red bar, inside it.

On the other side of the ad billboard, polygon 4 is the large yellow area,
which has polygon 3, the smaller black bar, inside it.

The parsed data reads like this:

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="column-40">Color</th>
            <th>Vectors</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>8</td>
            <td>2, 3, -4, -1</td>
        </tr>
        <tr>
            <td>9</td>
            <td>5, 6, -8, -7</td>
        </tr>
        <tr>
            <td>0</td>
            <td>7, 8, -6, -5</td>
        </tr>
        <tr>
            <td>3</td>
            <td>4, -3, -2, 1</td>
        </tr>
    </tbody>
</table>

Where each number is a <a href="#vectors">vector</a>, and a negative value means
that the vector is reversed. If reversed, it means that what is normally the start
point is now the end point, and vice versa.



## Points

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column-33">Hex</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>00 00 22 00 00 00 00 00</td>
            <td>Point 1</td>
        </tr>
        <tr>
            <td>00 00 02 00 00 00 00 00</td>
            <td>Point 2</td>
        </tr>
        <tr>
            <td>00 80 00 00 00 03 00 00</td>
            <td>Point 3</td>
        </tr>
        <tr>
            <td>01 80 00 00 00 03 00 00</td>
            <td>Point 4</td>
        </tr>
        <tr>
            <td>00 00 24 00 C0 00 00 00</td>
            <td>Point 5</td>
        </tr>
        <tr>
            <td>04 80 00 00 40 02 00 00</td>
            <td>Point 6</td>
        </tr>
        <tr>
            <td>00 00 04 00 C0 00 00 00</td>
            <td>Point 7</td>
        </tr>
        <tr>
            <td>06 80 00 00 40 02 00 00</td>
            <td>Point 8</td>
        </tr>
    </tbody>
</table>

_The point data will be explained further soon_

This calculates to:

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="column-20">Index</th>
            <th class="column-20">X</th>
            <th class="column-20">Y</th>
            <th class="column-20">Z</th>
            <th class>Type</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0</td>
            <td>0</td>
            <td>-1536</td>
            <td>0</td>
            <td>Scale</td>
        </tr>
        <tr>
            <td>1</td>
            <td>0</td>
            <td>1536</td>
            <td>0</td>
            <td>Scale</td>
        </tr>
        <tr>
            <td>2</td>
            <td>0</td>
            <td>-1536</td>
            <td>768</td>
            <td>Reference</td>
        </tr>
        <tr>
            <td>3</td>
            <td>0</td>
            <td>1536</td>
            <td>768</td>
            <td>Reference</td>
        </tr>
        <tr>
            <td>4</td>
            <td>0</td>
            <td>-1184</td>
            <td>192</td>
            <td>Scale</td>
        </tr>
        <tr>
            <td>5</td>
            <td>0</td>
            <td>-1184</td>
            <td>576</td>
            <td>Reference</td>
        </tr>
        <tr>
            <td>6</td>
            <td>0</td>
            <td>1184</td>
            <td>192</td>
            <td>Scale</td>
        </tr>
        <tr>
            <td>7</td>
            <td>0</td>
            <td>1184</td>
            <td>576</td>
            <td>Reference</td>
        </tr>
    </tbody>
</table>




## Vectors

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="column-20">Hex</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>00 00</td>
            <td>Always starts with 00 00</td>
        </tr>
        <tr>
            <td>00 01</td>
            <td>Vector from points 0 to 1</td>
        </tr>
        <tr>
            <td>00 02</td>
            <td>Vector from points 0 to 2</td>
        </tr>
        <tr>
            <td>02 03</td>
            <td>Vector from points 2 to 3</td>
        </tr>
        <tr>
            <td>01 03</td>
            <td>Vector from points 1 to 3</td>
        </tr>
        <tr>
            <td>04 05</td>
            <td>Vector from points 4 to 5</td>
        </tr>
        <tr>
            <td>05 07</td>
            <td>Vector from points 5 to 7</td>
        </tr>
        <tr>
            <td>04 06</td>
            <td>Vector from points 4 to 6</td>
        </tr>
        <tr>
            <td>06 07</td>
            <td>Vector from points 6 to 7</td>
        </tr>
    </tbody>
</table>




## Graphical Elements List


<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column-33">Hex</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                08 00 08 00 0E 00 0E 00<br />
                00 00 06 00 00 80 12 00<br />
                0C 00 00 80
            </td>
            <td>Unknown (so far)</td>
        </tr>
    </tbody>
</table>


## Putting it all together

Since this 3D object is actually very flat, we can disregard an entire axis.

Mapping out the object with its coordinates, we arrive at something looking like this:

<img src="/argdocs/images/object-shape-examples/01sh43-coords.png" alt="Object shape 43 coordinates" class="img-fluid" />

You can see the data in the <a href="#points">Points</a> declaration above.

_NB: The 0,0 coordinate is not an actual defined point, it is just displayed in the
image as a reference._

Replacing each actual point coordinate with its index (which we will need for further calculations), it now looks like this:

<img src="/argdocs/images/object-shape-examples/01sh43-points.png" alt="Object shape 43 points" class="img-fluid" />

We will now show the vectors, as green arrows with their default direction indicated.

<img src="/argdocs/images/object-shape-examples/01sh43-points-vectors.png" alt="Object shape 43 points and vectors" class="img-fluid" />

_NB: The first declared vector in an F1GP object is always from point 0 to point 0,
so not relevant or shown here._

As previously described, there are four polygons in
the <a href="#graphical-elements">Graphical elements</a> definitions above.

Starting with the first polygon, it is defined by the following vector declaration:

`2, 3, -4, -1`

This means that it starts with vector 2 (point 0 to point 2), then goes along vector 3 (point 2 to point 3).
After this, vector 4 is declared, but as a negative. This means that we reverse the direction of vector 4
and go from point 3 to point 1. The next vector, 1, is also negative, so we go from the end at
point 1 and close the polygon at point 0.

So the polygon is made up of the following points, in order:

`0 -> 2 -> 3 -> 1 -> 0`

As we can see from the image above, this is the large square. The color is index 8, which - if we look in
the [palette](/argdocs/misc/palette/) - we see is the white color.

In the same way, the next polygon is the red inner bar (color 9) goes along vector 7 and 8
(points 4 to 6 to 7), then vector 6 in
reverse (i.e. point 7 to 5) and then vector 5 in reverse (points 5 to 4), so:

`4 -> 6 -> 7 -> 5 -> 4`

The story repeats for the next two polygons, but pretty much all in reverse:

`7, 8, -6, -5`

and

`4, -3, -2, 1`
