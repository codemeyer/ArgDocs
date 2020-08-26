---
title: "ArgDocs: F1GP Preferences File (F1PREFS.DAT)"
---

# F1GP Preferences File (F1PREFS.DAT)

Game preferences are stored in the F1PREFS.DAT file.

Not to be confused with F1PREFS.286, F1PREFS.386 and F1PREFS.486 which (probably)
contain presets based on the speed of the computer, applied during setup.

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
        <td>Fixed (1,166 bytes)</td>
    </tr>
    <tr>
        <td>Checksum?</td>
        <td>Yes</td>
    </tr>
    </tbody>
</table>


## Preferences

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
            <td class="text-right">855</td>
            <td>Frame Rate (FPS) flag?</td>
            <td>02 when Frame Rate (FPS) is 23.0 or lower, 03 when FPS is 25.0</td>
        </tr>
        <tr>
            <td class="text-right">1034</td>
            <td>Path to name file to load automatically, 32 bytes</td>
            <td>Max 31 chars, always padded with at least one \0</td>
        </tr>
        <tr>
            <td class="text-right">1066</td>
            <td>Path to setup file to load automatically, 32 bytes</td>
            <td>Max 31 chars, always padded with at least one \0</td>
        </tr>
        <tr>
            <td class="text-right">1130</td>
            <td>Indicates if a name file should be loaded automatically</td>
            <td>0x00 = no, 0xFF = yes</td>
        </tr>
        <tr>
            <td class="text-right">1131</td>
            <td>Indicates if a setup file should be loaded automatically</td>
            <td>0x00 = no, 0xFF = yes</td>
        </tr>
        <tr>
            <td class="text-right">1160</td>
            <td>Frame Rate (FPS)</td>
            <td>
                8.1 fps = 0x25, 8.3 fps = 0x24, 23.0 fps = 0D, 25.0 fps = 0C
            </td>
        </tr>
    </tbody>
</table>


## Checksum

The final four (4) bytes (index 1162-1165) contain
the [checksum](/argdocs/misc/checksum/) for the file.
