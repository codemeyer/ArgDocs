---
title: "ArgDocs: F1GP Multi-Setup Files"
---

# F1GP Multi-Setup Files

Multi-setup files contain a race and qualifying setup for each track, for a total of 32 setups.

There is also a [single setup](/argdocs/file-formats/setups-single) file type containing
a single race or qualifying setup for a specific track.

<table class="table table-bordered table-striped table--tiny">
    <thead>
        <tr>
            <th>File Info</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Size</td>
            <td>Fixed (326 bytes)</td>
        </tr>
        <tr>
            <td>Checksum?</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>


## Header

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th class="text-right">Position</th>
        <th>Type</th>
        <th>Description</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="text-right">0</td>
        <td></td>
        <td>Separate race and qualifying setups</td>
        <td>0x00 00 = same setups<br>0xFF FF = separate race/qual. setups</td>
    </tr>
    </tbody>
</table>


## Setup Data

Each setup data is 10 bytes long.

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
        <td>Front wing angle</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Rear wing angle</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Gear 1 ratio</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Gear 2 ratio</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Gear 3 ratio</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Gear 4 ratio</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Gear 5 ratio</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Gear 6 ratio</td>
        <td>byte</td>
        <td></td>
    </tr>
    <tr>
        <td>Tyre compound</td>
        <td>byte</td>
        <td>0 = A, 1 = B, 2 = C, 3 = D</td>
    </tr>
    <tr>
        <td>Brake balance</td>
        <td>sbyte</td>
        <td>-32 to 32</td>
    </tr>
    </tbody>
</table>

This is repeated 16 times for qualifying setups, and 16 times for race setups, one pair for each track.


## Checksum

The final four (4) bytes contain
the [checksum](/argdocs/misc/checksum/) for the file.
