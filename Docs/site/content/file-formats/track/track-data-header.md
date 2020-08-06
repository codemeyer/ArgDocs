---
title: "ArgDocs: F1GP Track File Format - Track Data Header"
---

# Track Data Header (Track File Format)

The track data header starts at the short value at $100C + 0x1010, e.g. $384A for the Phoenix track.
This is the starting position called $TDH in the table below.

The header is either 28 or 32 bytes long depending on whether the kerbs have two or three colors.

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="text-right">Field</th>
            <th>Type</th>
            <th>Description</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">$TDH</td>
            <td>short</td>
            <td>Starting angle of first track segment</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+2</td>
            <td>short</td>
            <td>Starting height of first segment</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+4</td>
            <td>short</td>
            <td>X-coordinate of track center</td>
            <td>? in GP2</td>
        </tr>
        <tr>
            <td class="text-right">+6</td>
            <td>short</td>
            <td>Z-coordinate of track center</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+8</td>
            <td>short</td>
            <td>Y-coordinate of track center</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+10</td>
            <td>short</td>
            <td>Start width of 1st track segment</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+12</td>
            <td>short</td>
            <td>Pole position side</td>
            <td>768 = right, -768 = left</td>
        </tr>
        <tr>
            <td class="text-right">+14</td>
            <td>short</td>
            <td>Pit side</td>
            <td>0 = right, 10 = left</td>
        </tr>
        <tr>
            <td class="text-right">+15</td>
            <td>byte</td>
            <td>Surrounding area color</td>
            <td>0 = green, 0xC0/192 = gray, 128=gray</td>
        </tr>
        <tr>
            <td class="text-right">+16</td>
            <td>byte</td>
            <td>Starting width of right verge</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+17</td>
            <td>byte</td>
            <td>Starting width of left verge</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+18</td>
            <td>byte</td>
            <td>Kerb type (two or three colors)</td>
            <td>4 = three colors, otherwise 3</td>
        </tr>
        <tr>
            <td class="text-right">+19</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+20</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 8</td>
        </tr>
        <tr>
            <td class="text-right">+21</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+22</td>
            <td>byte</td>
            <td>Kerb upper color</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+23</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+24</td>
            <td>byte</td>
            <td>Kerb lower color</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+25</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+26</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 8</td>
        </tr>
        <tr>
            <td class="text-right">+27</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+28</td>
            <td>byte</td>
            <td>Kerb upper color 2 (if triple color)</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+29</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td class="text-right">+30</td>
            <td>byte</td>
            <td>Kerb lower color 2 (if triple color)</td>
            <td>Index in special kerb palette</td>
        </tr>
        <tr>
            <td class="text-right">+31</td>
            <td>byte</td>
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


[Back to F1GP Track File Format](/argdocs/file-formats/track/)
