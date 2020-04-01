---
title: "ArgDocs: F1GP Media Container Files"
aliases:
    - "/file-formats/item-containers/"
---

# F1GP Media Container Files

Media container files are files that contain a number of items. The items are usually
images or palette data, and some video/animation-related data.

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
            <td>Varying</td>
        </tr>
        <tr>
            <td>Checksum?</td>
            <td>No</td>
        </tr>
    </tbody>
</table>

A container file consists of a header which includes references to all the items
stored within, followed by the actual data.

## Format

### Signature

The first 8 bytes form the word "f1pcanim".

This is followed by a short value containing the number of items in the file.


### Item descriptions

The item descriptions are 14 bytes long. They repeat once for each item stored
in the file.

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th>Field</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Type</td>
            <td>short</td>
            <td>
                There are a number of different item types that exist:<br />
                1768: Probably represents a frame in an animation, occurs in CHAMP.DAT et al<br />
                1769: Large full-screen images, as stored in BACKDROP.DAT and TRACKPIX.DAT<br />
                1774: Small images, as stored in FLAGS.DAT and HELMETS.DAT<br />
                1776: Palette information for the image of type 1769 that follows it<br />
            </td>
        </tr>
        <tr>
            <td>Offset</td>
            <td>int</td>
            <td>Location later in the file where the data is stored</td>
        </tr>
        <tr>
            <td>Length</td>
            <td>int</td>
            <td>Length (in bytes) of the stored data</td>
        </tr>
        <tr>
            <td>Width</td>
            <td>short</td>
            <td>Width of image in pixels</td>
        </tr>
        <tr>
            <td>Height</td>
            <td>short</td>
            <td>Height of image in pixels</td>
        </tr>
    </tbody>
</table>


## Parsing the various image types

### Animation frames (type 1768)

The format of this is still unknown.


### Small images (type 1774)

Read a byte as a signed byte (-128 to 128). If the value is negative,
this represents a number of repeating pixels of the same colour.

Take the value and multiply it by -1 and then add 1 to get the number of
times the same colour will appear.

Then read the next byte. This contains the palette index of the colour
that should be repeated.

For example, all helmets in the default HELMET.DAT file start with the
values <code>D1 DC D1 DC D1 DC D1 DC D1 DC</code>. This is because the first five
lines of all helmet images are the same type of blue.

<code>D1</code> as a signed byte is -47. Multiplying this by -1 and adding 1 gives 48,
which is the width of a helmet image. DC is 220, which is the index of the
blue colour in the palette.

The number of repeating colours can never be greater than the width of the image.

If the value is positive it represents a number of pixels of different colours.

The value that has been read, plus 1, is the number of following bytes that should
be read, where each byte contains the index in the menu palette.

This process then continues until the end of the data has been reached.


### Large images (1769)

This data seems to differ from how the small images are structured, and is not yet
fully understood.


### Palette info (1776)

All palette info items have a width of 256 and a height of 0 (for some reason).
They are always 768 bytes long, where each set of three pixels represents the amount
of Red, Green and Blue in the colour. And 256 * 3 is 768...

<br>

## Container File Details

The media container files in F1GP are BACKDROP.DAT, CHAMP.DAT,
CRASH1.DAT, CRASH2.DAT, CRASH3.DAT, FLAGS.DAT, HELMETS.DAT,
TRACKPIX.DAT and TROPHY.DAT. They are described below.


### BACKDROP.DAT

This file contains the images that are displayed in the background throughout the
game, including the title screen. However, it does not include the images of tracks, those
are stored in TRACKPIX.DAT.

<table class="table table-bordered table-striped">
    <thead>
        <tr>
            <th class="text-right">Index</th>
            <th>Description</th>
            <th>Usage</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">0</td>
            <td>Palette data for image 1</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">1</td>
            <td>Image of Nelson Piquet in the Benetton</td>
            <td></td>
            <td><img src="/argdocs/images/backdrop-image-01.png" alt="BACKDROP.DAT image 01" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">2</td>
            <td>Palette data for image 3</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">3</td>
            <td>Image of marshall waving flag</td>
            <td>Shown between races during a championship season</td>
            <td><img src="/argdocs/images/backdrop-image-03.png" alt="BACKDROP.DAT image 03" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">4</td>
            <td>Palette data for image 5</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">5</td>
            <td>Image of Honda engine</td>
            <td>Shown when viewing the constructors championship standings</td>
            <td><img src="/argdocs/images/backdrop-image-05.png" alt="BACKDROP.DAT image 05" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">6</td>
            <td>Palette data for image 7</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">7</td>
            <td>Title image</td>
            <td></td>
            <td><img src="/argdocs/images/backdrop-image-07.png" alt="BACKDROP.DAT image 07" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">8</td>
            <td>Palette data for image 9</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">9</td>
            <td>Two Lotuses</td>
            <td></td>
            <td><img src="/argdocs/images/backdrop-image-09.png" alt="BACKDROP.DAT image 09" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">10</td>
            <td>Palette data for image 11</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">11</td>
            <td>Mansell's helmet</td>
            <td>Background on the driver selection menu.</td>
            <td><img src="/argdocs/images/backdrop-image-11.png" alt="BACKDROP.DAT image 11" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">12</td>
            <td>Palette data for image 13</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">13</td>
            <td>Williams team member holding a pit board</td>
            <td></td>
            <td><img src="/argdocs/images/backdrop-image-13.png" alt="BACKDROP.DAT image 13" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">14</td>
            <td>Palette data for image 15</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">15</td>
            <td>Nigel Mansell in the pits</td>
            <td>Appears when pressing Esc during a session</td>
            <td><img src="/argdocs/images/backdrop-image-15.png" alt="BACKDROP.DAT image 15" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">16</td>
            <td>Palette data for image 17</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">17</td>
            <td>Car with Agip logos show from behind</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">18</td>
            <td>Palette data for image 19</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">19</td>
            <td>Car in pits</td>
            <td>Setup screen</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">20</td>
            <td>Palette data for image 21</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">21</td>
            <td>Car in pits, wheels off</td>
            <td>Setup screen</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">22</td>
            <td>Palette data for image 23</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">23</td>
            <td>Car in pits, bodywork off</td>
            <td>Setup screen</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">24</td>
            <td>Palette data for image 25</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">25</td>
            <td>Senna spraying champagne</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">26</td>
            <td>Palette data for image 27</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">27</td>
            <td>Nose of car, rendered</td>
            <td>Displayed after winning the championship?</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">28</td>
            <td>Palette data for image 29</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">29</td>
            <td>Senna and a Williams driving through the rain</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">30</td>
            <td>Palette data for image 31</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">31</td>
            <td>McLaren and Williams in Monaco</td>
            <td>Main menu background</td>
            <td><img src="/argdocs/images/backdrop-image-31.png" alt="BACKDROP.DAT image 31" class="img-fluid" /></td>
        </tr>
        <tr>
            <td class="text-right">32</td>
            <td>Palette data for image 33</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">33</td>
            <td>Three drivers on the podium</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">34</td>
            <td>Palette data for image 35</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">35</td>
            <td>Driver sitting with other drivers behind</td>
            <td></td>
            <td><img src="/argdocs/images/backdrop-image-35.png" alt="BACKDROP.DAT image 35" class="img-fluid" /></td>
        </tr>
    </tbody>
</table>
<br />

### CHAMP.DAT

Probably contains the animation that is displayed after winning
the world championship.
<br />


### CRASH1.DAT, CRASH2.DAT and CRASH3.DAT

The different animations that are displayed after retiring from a
race in different ways.
<br />


### FLAGS.DAT

The flags that are displayed when choosing the game language after startup.
Note that these are dependent on the palette stored in BACKDROP.DAT, item index 6.
<br />


### HELMETS.DAT

Contains the images that are displayed on the driver selection menu screen.
Note that these are dependent on the palette stored in BACKDROP.DAT, item index 10.
<br />


### TRACKPIX.DAT

Contains the 16 background images that appear when browsing tracks, plus the image
that appears at the track selection screen.

<br />


### TROPHY.DAT

The animation that appears after you have won a race(?)
