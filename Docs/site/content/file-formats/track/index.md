---
title: "ArgDocs: F1GP Track File Format"
---

# F1GP Track File Format

The game comes with the 16 tracks used in the 1991 F1 season, with tracks as varied as
the tight streets of Monaco to the long, long straights of Hockenheim.

The track files are named "F1CTxx.DAT", where "xx" is a number from "01" to "16".

Because of the similarity between the F1GP and GP2 file formats, a lot of the information below
has been deduced using Maxime Labelle's
["The Grand Prix 2 Track File Format (Beta 0.5)"](http://www.waa63.ch/racesim/TEIC/primer/GP2TrackFileFormat.htm)
and by playing around with Paul Hoad's GP2 Track Editor. Another invaluable resource has been
the [Chequered Flag](http://chequeredflag.sourceforge.net/) F1GP track editor by Barrie Millar, Klaus Six and René Smit.
René Smit and Alejandro Cáceres have also contributed a large amount of research and code.


<table class="table table-bordered table-striped table--small">
    <thead>
        <tr>
            <th>File Info</th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Size</td>
            <td>Varying (original tracks between 13,368 to 20,497 bytes)</td>
        </tr>
        <tr>
            <td>Checksum?</td>
            <td>Yes</td>
        </tr>
    </tbody>
</table>

The documentation below uses "$..." to describe a location in the file,
and "0x.." to describe a hex value.

The track file contains the following information. For more details, see each section.

- [Horizon Image](/argdocs/file-formats/track/horizon/)
- [Offsets](/argdocs/file-formats/track/offsets/)
- [Object Shapes](/argdocs/file-formats/track/object-shapes/)
- [Object Settings](/argdocs/file-formats/track/object-settings/)
- [Track Data Header](/argdocs/file-formats/track/track-data-header/)
- [Track Sections](/argdocs/file-formats/track/track-sections/)
- [Computer Car Racing Line](/argdocs/file-formats/track/racing-line/)
- [Computer Car Setup and Behavior](/argdocs/file-formats/track/cc-setup-behavior/)
- [Pit Lane Sections](/argdocs/file-formats/track/track-sections/) (identical to Track Sections)
- [Camera Definitions](/argdocs/file-formats/track/camera-definitions/)
- [Additional Data and Behavior](/argdocs/file-formats/track/additional-data-behavior/)

The final four (4) bytes of the track contain the [checksum](/argdocs/misc/checksum/).

If the checksum is incorrect, F1GP will not load the track file.
