---
title: "ArgDocs: F1GP Track File Format - Horizon"
---

## Horizon (Track File Format)

The first 4,096 bytes represent the horizon image, as a 512 x 8 bitmap.
This means that the first 512 bytes represent the first horizontal line of the image,
the next 512 bytes are the second line, etc.

Each byte indicates the color in the [palette](/argdocs/misc/palette/).

[Back to F1GP Track File Format](/argdocs/file-formats/track/)
