---
title: "ArgDocs: F1GP Track Section Commands"
aliases:
    - "/track-data/track-commands/"
---

# Track Section Commands

Track section commands are applied to [track sections](/argdocs/file-formats/track/track-sections/)
and pit lane sections, and alter various properties of the section.

These are the various commands that can appear for a track or pit lane section.


<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="column-10">Cmd</th>
            <th>Description</th>
            <th class="column-10 text-right"><abbr title="Number of arguments">Arg#</abbr></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x80/">0x80</a>
            </td>
            <td>Object placement</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x81/">0x81</a>
            </td>
            <td>Display distance forwards</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x82/">0x82</a>
            </td>
            <td>Display distance backwards</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x83/">0x83</a>
            </td>
            <td>Disable drawing of horizon</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x84/">0x84</a>
            </td>
            <td>Enable drawing of horizon</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x85/">0x85</a>
            </td>
            <td>Track width change</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x86/">0x86</a>
            </td>
            <td>Connect start of pit lane to track</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x87/">0x87</a>
            </td>
            <td>Connect end of pit lane to track</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x88/">0x88</a>
            </td>
            <td>Pit lane garages, left-hand side</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x89/">0x89</a>
            </td>
            <td>Pit lane garages, right-hand side</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x8A/">0x8A</a>
            </td>
            <td>Track Markings Type A</td>
            <td class="text-right">6</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x8B/">0x8B</a>
            </td>
            <td>Track Markings Type B</td>
            <td class="text-right">6</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x8C/">0x8C</a>
            </td>
            <td>Changes unknown element on the left?</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x8D/">0x8D</a>
            </td>
            <td>Changes unknown element on the right?</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x8E/">0x8E</a>
            </td>
            <td>Left kerb starts</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x8F/">0x8F</a>
            </td>
            <td>Right kerb starts</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x90/">0x90</a>
            </td>
            <td>Reverse object placement</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x91/">0x91</a>
            </td>
            <td>Unknown Monaco command</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x92/">0x92</a>
            </td>
            <td>Unknown Action 1</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x93/">0x93</a>
            </td>
            <td>Unknown Action 2</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x94/">0x94</a>
            </td>
            <td>Computer car coaching, left</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x95/">0x95</a>
            </td>
            <td>Computer car coaching, right</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x96/">0x96</a>
            </td>
            <td>Pit lane start</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x97/">0x97</a>
            </td>
            <td>Pit lane end</td>
            <td class="text-right">1</td>
        </tr>        
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x98/">0x98</a>
            </td>
            <td>Left fence height change</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x99/">0x99</a>
            </td>
            <td>Right fence height change</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x9A/">0x9A</a>
            </td>
            <td>Custom fence height</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x9B/">0x9B</a>
            </td>
            <td>Unknown pit lane marker 1</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x9C/">0x9C</a>
            </td>
            <td>Unknown pit lane marker 2</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x9D/">0x9D</a>
            </td>
            <td>Unknown pit lane marker 3</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x9E/">0x9E</a>
            </td>
            <td>Unknown pit lane marker 4</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0x9F/">0x9F</a>
            </td>
            <td>Pit lane fences start</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA0/">0xA0</a>
            </td>
            <td>Pit lane fences end</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA1/">0xA1</a>
            </td>
            <td>Pit lane entry, join right lane fences</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA2/">0xA2</a>
            </td>
            <td>Pit lane entry, join left lane fences</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA3/">0xA3</a>
            </td>
            <td>Pit lane exit, join right lane fences</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA4/">0xA4</a>
            </td>
            <td>Pit lane exit, join left lane fences</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA5/">0xA5</a>
            </td>
            <td>Change sign of first two sector arguments</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA6/">0xA6</a>
            </td>
            <td>Set unknown section flags 1</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA7/">0xA7</a>
            </td>
            <td>Set unknown section flags 2</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA8/">0xA8</a>
            </td>
            <td>Section that triggers the chequered flag</td>
            <td class="text-right">1</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xA9/">0xA9</a>
            </td>
            <td>Pit lane view distance</td>
            <td class="text-right">2</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xAA/">0xAA</a>
            </td>
            <td>Computer cars pit lane modifier?</td>
            <td class="text-right">4</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xAB/">0xAB</a>
            </td>
            <td>Unknown, maybe unused</td>
            <td class="text-right">3</td>
        </tr>
        <tr>
            <td>
                <a href="/argdocs/track-data/track-section-commands/0xAC/">0xAC</a>
            </td>
            <td>Palette change</td>
            <td class="text-right">5</td>
        </tr>
    </tbody>
</table>
