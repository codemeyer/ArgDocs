---
title: "ArgDocs: F1GP Name File"
---

# F1GP Name File

Contains the names of drivers, teams and engines.

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
            <td>Fixed (1,484 bytes)</td>
        </tr>
        <tr>
            <td>Checksum?</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>


## Driver Names

Drivers are ordered by the numbers they have and not by the order
in which they appear in the game menu. There are always 40 drivers in each name file,
even though the game only supports a maximum of 36 drivers.

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="text-right">Position</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">0</td>
            <td>Driver 1 name</td>
            <td>Each name entry is 24 bytes long, padded with null (\0)</td>
        </tr>
        <tr>
            <td class="text-right">(<em>n</em>*24)</td>
            <td>Driver <em>n</em> name</td>
            <td>For zero-based <em>n</em></td>
        </tr>
        <tr>
            <td class="text-right">...</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">936</td>
            <td>Driver 40 name</td>
            <td></td>
        </tr>
    </tbody>
</table>

Note that a driver name can be max 23 bytes long, as the final null is needed for padding.
In the game, the name may appear cut off if it exceeds around 18 characters.
When you enter names in-game, it calculates the width of the name and does not allow you
to enter one that would be cut off.

For instance, using the in-game editing options a name such as "Heinz-Harald Frentzen" cannot
be entered, because the game knows that it will be cut off. If you use a tool
(such as [ArgEditor](/argeditor)) to create a name file, entering "Heinz-Harald Frentzen" will
be OK, but will appear in in-game messages as "Heinz-Harald Frentz" or similar.


## Team Names

Teams are ordered by the way they appear in the game menu. There are always 20 teams in each name file,
even though the game only supports 18 teams.

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="text-right">Position</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">960</td>
            <td>Team 1 name</td>
            <td>Each name is 13 bytes long, padded with null (\0)</td>
        </tr>
        <tr>
            <td class="text-right">960+(<em>n</em>*13)</td>
            <td>Team <em>n</em> name</td>
            <td>For zero-based <em>n</em></td>
        </tr>
        <tr>
            <td class="text-right">...</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">1207</td>
            <td>Team 20 name</td>
            <td></td>
        </tr>
    </tbody>
</table>


## Engines

The engine for each team is ordered in the same way as the teams, i.e. by the way they appear in the game menu.

<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th class="text-right">Position</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">1220</td>
            <td>Engine 1 name</td>
            <td>Each name is 13 bytes long, padded with null (\0)</td>
        </tr>
        <tr>
            <td class="text-right">1220+(<em>n</em>*13)</td>
            <td>Engine <em>n</em> name</td>
            <td>For zero-based <em>n</em></td>
        </tr>
        <tr>
            <td class="text-right">...</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">1467</td>
            <td>Engine 20 name</td>
            <td></td>
        </tr>
    </tbody>
</table>

There are always 20 engines in each name file, even though the game only supports 18 teams/engines.


## Checksum

The final four (4) bytes, starting at index 1480,
contain the [checksum](/argdocs/misc/checksum/) for the file.
