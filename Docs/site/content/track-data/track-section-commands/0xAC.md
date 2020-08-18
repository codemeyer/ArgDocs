---
title: "ArgDocs: F1GP Track Section Command 0xAC - Palette Change"
---

# 0xAC - Palette Change (Track Section Command)

This command is used to make minor changes to how the asphalt (gray)
and grass (green) look for each track. For example, the asphalt in Mexico
is a brighter gray, whilst the asphalt in France is much darker.

This command occurs once or twice per track, always in the first section.
The tracks where it occurs once are Phoenix and Monaco, which do not
have any grass to change the color of.


## Arguments

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th>Arg</th>
            <th>Description</th>
            <th>Common values</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0</td>
            <td>Unknown/unused</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Palette index</td>
            <td>Always 18 (grass) or 26 (asphalt)</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Red color value (0-63?)</td>
            <td>14 to 36</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Green color value (0-63?)</td>
            <td>23 to 42</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Blue color value (0-63?)</td>
            <td>4 to 35</td>
        </tr>
    </tbody>
</table>


## Notes

Changing the color of [palette index](/argdocs/misc/palette/) 26 alters the gray asphalt color.
Palette index 18 alters the green grass.
Changing any other palette index does not seem to have any effect.

Interestingly, changing the green color also seems affect the color of the in-game
messages such as the "Riding with..." text.


## Examples

By setting the colors to 12-12-12, you get a _very_ dark gray.

<img src="/argdocs/images/ts-commands/AC-palette-change-12-12-12.png" alt="Dark gray tarmac" class="img-fluid" />

You can also do something odd, and use 0-0-63 to create a very strong blue track.

<img src="/argdocs/images/ts-commands/AC-palette-change-0-0-63.png" alt="A blue track" class="img-fluid" />



## Occurrences by track
   
<table class="table table-bordered table-striped">
    <thead>
        <tr>
            <th>Location</th>
            <th class="text-right">US</th>
            <th class="text-right">BRA</th>
            <th class="text-right">SM</th>
            <th class="text-right">MON</th>
            <th class="text-right">CAN</th>
            <th class="text-right">MEX</th>
            <th class="text-right">FRA</th>
            <th class="text-right">GB</th>
            <th class="text-right">GER</th>
            <th class="text-right">HUN</th>
            <th class="text-right">BEL</th>
            <th class="text-right">ITA</th>
            <th class="text-right">POR</th>
            <th class="text-right">SPA</th>
            <th class="text-right">JAP</th>
            <th class="text-right">AUS</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Track</td>
            <td class="text-right">1</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">1</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>Pit Lane</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
            <td class="text-right">0</td>
        </tr>
    </tbody>
</table>

<br />

[Back to Track Section Commands list](/argdocs/track-data/track-section-commands/)
