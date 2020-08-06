---
title: "ArgDocs: F1GP Track File Format - Object Shape Examples"
---

# Object Shape Examples (Track File Format)


The following is an example of an ad billboard in the Phoenix track.

<!-- TODO: image -->

The data is 402 bytes long.


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
10 bytes of unknown data, which occurs on a few tracks.


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
            <td>Base color of polygon 4 (yellow, but can be affect by "Unknown" value in an object setting)</td>
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
