---
title: "ArgDocs: F1GP Track File Format - Object Settings"
---

# Object Settings (Track File Format)

Object settings represent instances of 3D objects, or other special objects, that are placed
around the track.

For example, the same 3D object can be reused several times, but with differing rotations,
distance from track and other data.

Each object settings consists of 16 bytes.

Object settings are read until the values specified in the $100C track data header is reached.


<table class="table table-bordered table-striped table--large">
    <thead>
    <tr>
        <th style="width:20%">Field</th>
        <th style="width:10%">Type</th>
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
        <td>Possibly color related for 3D objects (bit flags?)</td>
    </tr>
    <tr>
        <td>Distance from Track Center</td>
        <td>short</td>
        <td>
            The distance between the object and the center of the track. Negative values
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
            Angle Y/Z, except when Id=5 (or 1 or 13), then it represents the index of
            a <a href="/argdocs/track-data/trackside-objects/">track-side object</a>
        </td>
    </tr>
    <tr>
        <td>Unknown 2</td>
        <td>short</td>
        <td>Possibly related to drawing order (bit flags?)</td>
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

The first 17 object settings for each track are very similar, and refer to such items as road signs, etc.


[Back to F1GP Track File Format](/argdocs/file-formats/track/)
