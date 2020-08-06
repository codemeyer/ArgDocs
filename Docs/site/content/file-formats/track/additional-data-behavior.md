---
title: "ArgDocs: F1GP Track File Format - Additional Data and Behavior"
---

## Additional Data and Behavior (Track File Format)

This part is always 28 bytes long.

<table class="table table-bordered table-striped table--large">
    <thead>
        <tr>
            <th class="column-20 text-right">Field</th>
            <th class="column-10">Type</th>
            <th class="column-33">Description</th>
            <th class=" text-right">Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">Unknown 1</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 00</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 2</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 01</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 3</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 02</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 4</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 03</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 5</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. 04 for slow tracks (US,MON,HUN,AUS), otherwise always 09</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 6</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 05</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 7</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 06</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 8</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 07</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 9</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 08</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 10</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 09</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 11</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 10</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 12</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. 11 for slow tracks (US,MON,HUN,AUS), otherwise always 02</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 13</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 12</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 14</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 13</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 15</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 14</td>
        </tr>
        <tr>
            <td class="text-right">Unknown 16</td>
            <td>byte</td>
            <td></td>
            <td class="text-right">Possibly not used. Always 15</td>
        </tr>
        <tr>
            <td class="text-right">Formation Length</td>
            <td>short</td>
            <td>
                At the start of the race, AI cars will not steer left/right until
                after reaching this track length.
            </td>
            <td class="text-right">Examples: 20, 35, 50, 118, 200, 203</td>
        </tr>
        <tr>
            <td class="text-right">Lap time indication (ms)</td>
            <td>int</td>
            <td>
                Used in calculation of maximum number of runners non-race and hotseat duration.
                Divided by (104 * session minutes) for max runners non-race
            </td>
            <td class="text-right">Examples: 86000, 80000, etc</td>
        </tr>
        <tr>
            <td class="text-right">Lap Count</td>
            <td>short</td>
            <td>Lap count for 100% race</td>
            <td class="text-right"></td>
        </tr>
        <tr>
            <td class="text-right">Strategy (lap for first pit stop)</td>
            <td>short</td>
            <td>Close to 33% or 50% race distance</td>
            <td class="text-right">Examples: 26, 27, 30, 37, 39, 43</td>
        </tr>
        <tr>
            <td class="text-right">Strategy chance</td>
            <td>short</td>
            <td>Likelihood of applying strategy above</td>
            <td class="text-right"></td>
        </tr>
    </tbody>
</table>


[Back to F1GP Track File Format](/argdocs/file-formats/track/)
