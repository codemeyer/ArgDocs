---
title: "ArgDocs: F1GP Single Setup Files"
---

# F1GP Single Setup Files

Single setup files contain just _one_ car setup.

There is also a [multi-setup](multi-setup) file type containing a
race and qualifying setup for each track, for a total of 32 setups.

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
            <td>Fixed (14 bytes)</td>
        </tr>
        <tr>
            <td>Checksum?</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>


## Setup Data

The setup data is 10 bytes long.

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


## Checksum

The final four (4) bytes contain 
the [checksum](/argdocs/misc/checksum) for the file.
