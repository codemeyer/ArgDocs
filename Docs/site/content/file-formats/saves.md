---
title: "ArgDocs: F1GP Saved Games (between races)"
---

# F1GP Saved Games

There are different kinds of saved games. The documentation here refers to
games that have been saved _between races_ during a championship season.

For information about games that are saved _during_ season races, see
the [F1GP Saved Games(during races)](/argdocs/file-formats/saves-racing/) page.

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
        <td>Fixed (3,578 bytes)</td>
    </tr>
    <tr>
        <td>Checksum?</td>
        <td>Yes</td>
    </tr>
    </tbody>
</table>


## Unknown

The first 828 bytes contain the number of races completed, plus a lot of
(so far) unknown information, but it probably contains information about preferences
such as race length, session lengths, possibility of rain, etc.

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th class="text-right">Position</th>
        <th>Description</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="text-right">26</td>
        <td>Number of races completed</td>
        <td>Zero-based</td>
    </tr>
    </tbody>
</table>


## Results

The results at each race is stored as a number of 16 byte blocks, ordered by the driver's number.

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th class="text-right">Position</th>
        <th>Description</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="text-right">828</td>
        <td>Results for driver 1</td>
        <td>Each entry is 16 bytes long</td>
    </tr>
    <tr>
        <td class="text-right">828 + (n*16)</td>
        <td>Results for driver n</td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">1452</td>
        <td>Results for driver 40</td>
        <td></td>
    </tr>
    </tbody>
</table>


## Driver Names

The names of drivers, teams and engines is stored in the file, starting at location 2094.

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th class="text-right">Position</th>
        <th>Description</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="text-right">2094</td>
        <td>Driver 1 name</td>
        <td>Each name entry is 24 bytes long, padded with null (\0)</td>
    </tr>
    <tr>
        <td class="text-right">2094 + (n*24)</td>
        <td>Driver n name</td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">...</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">3030</td>
        <td>Driver 40 name</td>
        <td></td>
    </tr>
    </tbody>
</table>


## Team Names

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th class="text-right">Position</th>
        <th>Description</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="text-right">3054</td>
        <td>Team 1 name</td>
        <td>Each name entry is 13 bytes long, padded with null (\0)</td>
    </tr>
    <tr>
        <td class="text-right">3054 + (n*13)</td>
        <td>Team n name</td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">...</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">3301</td>
        <td>Team 20 name</td>
        <td></td>
    </tr>
    </tbody>
</table>


## Engines

<table class="table table-bordered table-striped table--small">
    <thead>
    <tr>
        <th class="text-right">Position</th>
        <th>Description</th>
        <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td class="text-right">3314</td>
        <td>Engine 1 name</td>
        <td>Each name entry is 13 bytes long, padded with null (\0)</td>
    </tr>
    <tr>
        <td class="text-right">3314 + (n*13)</td>
        <td>Engine n name</td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">...</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td class="text-right">3561</td>
        <td>Engine 20 name</td>
        <td></td>
    </tr>
    </tbody>
</table>


## Checksum

The final four (4) bytes, starting at index 3574, contain
the [checksum](/argdocs/misc/checksum/) for the file.
