---
title: "ArgDocs: F1GP Track File Format - Offsets"
---

# Offsets (Track File Format)

The Offsets section begins at $1000.

<table class="table table-bordered table-striped table--medium">
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
            <td>Base offset</td>
            <td>Always 0x1010 (4112)</td>
        </tr>
        <tr>
            <td>$1002</td>
            <td>Unknown short</td>
            <td>This value also appears in 3D object definitions</td>
        </tr>
        <tr>
            <td>$1004</td>
            <td>Unknown short</td>
            <td></td>
        </tr>
        <tr>
            <td>$1006</td>
            <td>Unknown short</td>
            <td>This value also appears in 3D object definitions</td>
        </tr>
        <tr>
            <td>$1008</td>
            <td>Checksum offset</td>
            <td>Add 0x1010 (4112, i.e. base offset) to get location in file</td>
        </tr>
        <tr>
            <td>$100A</td>
            <td>Object list data offset</td>
            <td>Add 0x1010 (4112, i.e. base offset) to get location in file</td>
        </tr>
        <tr>
            <td>$100C</td>
            <td>Track data offset</td>
            <td>Add 0x1010 (4112, i.e. base offset) to get location in file</td>
        </tr>
    </tbody>
</table>

[Back to F1GP Track File Format](/argdocs/file-formats/track/)
