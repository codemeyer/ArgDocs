---
title: "ArgDocs: F1GP Track Section Commands"
aliases:
    - "/track-data/track-commands/"
---

# Track Section Commands

Track section commands are applied to track sections and pit lane sections, and alter
various properties of the section.

These are the various commands that appear for track sections.

<!-- TODO: table with links to unique pages -->

<a href="#command-80">0x80: Object placement</a><br>
<a href="#command-81">0x81: Display distance forwards</a><br>
<a href="#command-82">0x82: Display distance backwards</a><br>
<a href="#command-83">0x83: Disable drawing of background picture/horizon</a><br>
<a href="#command-84">0x84: Enable drawing of background picture/horizon</a><br>
<a href="#command-85">0x85: Track width change</a><br>
<a href="#command-86">0x86: Connect start of pit lane to track</a><br>
<a href="#command-87">0x87: Connect end of pit lane to track</a><br>
<a href="#command-88">0x88: Pit parking zone marking left-hand pit lane</a><br>
<a href="#command-89">0x89: Pit parking zone marking for right-hand pit lane</a><br>
<a href="#command-8A">0x8A: Track markings</a><br>
<a href="#command-8B">0x8B: Starting grid markings</a><br>
<a href="#command-8C">0x8C: Changes unknown element on the left?</a><br>
<a href="#command-8D">0x8D: Changes unknown element on the right?</a><br>
<a href="#command-8E">0x8E: Left kerb starts</a><br>
<a href="#command-8F">0x8F: Right kerb starts</a><br>
<a href="#command-90">0x90: Reverse object placement</a><br>
<a href="#command-91">0x91: Unknown Monaco command</a><br>
<a href="#command-92">0x92: Sector in which unknown action 1 is taken?</a><br>
<a href="#command-93">0x93: Sector in which unknown action 2 is taken?</a><br>
<a href="#command-94">0x94: Computer car coaching left</a><br>
<a href="#command-95">0x95: Computer car coaching right</a><br>
<a href="#command-96">0x96: Pit lane start</a><br>
<a href="#command-97">0x97: Pit lane end</a><br>
<a href="#command-98">0x98: Left fence height change</a><br>
<a href="#command-99">0x99: Right fence height change</a><br>
<a href="#command-9A">0x9A: Custom fence height</a><br>
<a href="#command-9B">0x9B: Unknown pit lane marker</a><br>
<a href="#command-9C">0x9C: Unknown pit lane marker 2</a><br>
<a href="#command-9D">0x9D: Unknown pit lane marker 3</a><br>
<a href="#command-9E">0x9E: Unknown pit lane marker 4</a><br>
<a href="#command-9F">0x9F: Pit lane fences start</a><br>
<a href="#command-A0">0xA0: Pit lane fences end</a><br>
<a href="#command-A1">0xA1: Pit lane entry, join right lane fences</a><br>
<a href="#command-A2">0xA2: Pit lane entry, join left lane fences</a><br>
<a href="#command-A3">0xA3: Pit lane exit, join right lane fences</a><br>
<a href="#command-A4">0xA4: Pit lane exit, join left lane fences</a><br>
<a href="#command-A5">0xA5: Change the sign of the first two sector arguments</a><br>
<a href="#command-A6">0xA6: Set unknown section flags 1</a><br>
<a href="#command-A7">0xA7: Set unknown section flags 2</a><br>
<a href="#command-A8">0xA8: Section that triggers the chequered flag</a><br>
<a href="#command-A9">0xA9: Pit lane view distance</a><br>
<a href="#command-AA">0xAA: Computer cars pit lane modifier?</a><br>
<a href="#command-AB">0xAB: Unknown, maybe unused</a><br>
<a href="#command-AB">0xAC: Palette change</a><br>


<h2 id="command-80">0x80: Object placement</h2>

Places a track-side object.


### Arguments

<table class="table table-bordered table-striped table--small">
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
            <td>Distance from start of sector</td>
            <td></td>
        </tr>
        <tr>
            <td>1</td>
            <td>Object description offset</td>
            <td></td>
        </tr>
    </tbody>
</table>

The "Object description offset" refers to the offset of the
[Object settings](/argdocs/file-formats/track/object-settings/) instance.
Since each object setting takes 16 bytes, the offset value is the zero-based
index of the object multiplied by 16.

<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">153</td>
                <td class="text-right">76</td>
                <td class="text-right">107</td>
                <td class="text-right">157</td>
                <td class="text-right">102</td>
                <td class="text-right">134</td>
                <td class="text-right">90</td>
                <td class="text-right">66</td>
                <td class="text-right">172</td>
                <td class="text-right">105</td>
                <td class="text-right">174</td>
                <td class="text-right">167</td>
                <td class="text-right">84</td>
                <td class="text-right">123</td>
                <td class="text-right">93</td>
                <td class="text-right">148</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">3</td>
                    <td class="text-right">6</td>
                    <td class="text-right">4</td>
                    <td class="text-right">19</td>
                    <td class="text-right">6</td>
                    <td class="text-right">6</td>
                    <td class="text-right">5</td>
                    <td class="text-right">8</td>
                    <td class="text-right">7</td>
                    <td class="text-right">6</td>
                    <td class="text-right">2</td>
                    <td class="text-right">4</td>
                    <td class="text-right">5</td>
                    <td class="text-right">5</td>
                    <td class="text-right">5</td>
                    <td class="text-right">7</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-81">0x81: Display distance forwards</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0 to 150</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Draw distance?</td>
            <td>87 to 248</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">8</td>
                <td class="text-right">10</td>
                <td class="text-right">9</td>
                <td class="text-right">3</td>
                <td class="text-right">9</td>
                <td class="text-right">10</td>
                <td class="text-right">11</td>
                <td class="text-right">14</td>
                <td class="text-right">17</td>
                <td class="text-right">6</td>
                <td class="text-right">13</td>
                <td class="text-right">22</td>
                <td class="text-right">8</td>
                <td class="text-right">7</td>
                <td class="text-right">10</td>
                <td class="text-right">11</td>
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
    </details>
</p>
<br />
<h2 id="command-82">0x82: Display distance backwards</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0 to 250</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Draw distance?</td>
            <td>72 to 249</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">4</td>
                <td class="text-right">8</td>
                <td class="text-right">5</td>
                <td class="text-right">2</td>
                <td class="text-right">6</td>
                <td class="text-right">6</td>
                <td class="text-right">4</td>
                <td class="text-right">8</td>
                <td class="text-right">18</td>
                <td class="text-right">6</td>
                <td class="text-right">10</td>
                <td class="text-right">14</td>
                <td class="text-right">3</td>
                <td class="text-right">5</td>
                <td class="text-right">6</td>
                <td class="text-right">5</td>
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
    </details>
</p>
<br />
<h2 id="command-83">0x83: Disable drawing of background picture/horizon</h2>

This command only appears in Monaco, where it disables the drawing of the horizon
shortly after leaving the Grand Hotel hairpin, so that you only see the ocean
when driving through Portier.

<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>3 in only usage</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-84">0x84: Enable drawing of background picture/horizon</h2>

This command only appears in Monaco, where it re-enables the drawing of the horizon
after driving through Portier.


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>3 in only usage</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-85">0x85: Track width change</h2>

<p>Always from center?</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Distance from start of sector?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Transition length</td>
            <td>4 to 74</td>
        </tr>
        <tr>
            <td>2</td>
            <td>New width</td>
            <td>960 to 1920</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-86">0x86: Connect start of pit lane to track</h2>

<p>Defines where the pit lane starts. Only occurs once per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-87">0x87: Connect end of pit lane to track</h2>

<p>Defines where the pit lane ends. Only occurs once per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-88">0x88: Pit parking zone marking left-hand pit lane</h2>

<p>Only used on tracks where the pit lane is to the left of the track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Length of zone marking?</td>
            <td>Always 18</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-89">0x89: Pit parking zone marking for right-hand pit lane</h2>

<p>Only used on tracks where the pit lane is to the right of the track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Length of zone marking?</td>
            <td>Always 18</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-8A">0x8A: Track markings</h2>

<p>GP2: 'Track Markings Type A'</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0 to 108</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>-16376, 3, 8456, 8968 or 14088</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Length of track markings?</td>
            <td>1 to 13</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Unknown</td>
            <td>-1960 to 2000</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Unknown</td>
            <td>-880, -200, 0 or 880</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Unknown</td>
            <td>257, 513, 771 or 1281</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">32</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">2</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
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
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-8B">0x8B: Starting grid markings</h2>

<p>GP2 'Track Markings Type B'</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>1 to 93</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>-16381, 8456, 9480 or 14088</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Width of grid markings? Length of grid slots?</td>
            <td>1, 9 or 13</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Unknown</td>
            <td>-1960 to 2000</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Unknown</td>
            <td>-880, 0 or 880</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Unknown</td>
            <td>257, 513, 771 or 1281</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
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
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-8C">0x8C: Changes unknown element on the left?</h2>

<p>Never occurs in any of the default tracks.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td></td>
        </tr>
        <tr>
            <td>1</td>
            <td>Length?</td>
            <td></td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
    </details>
</p>
<br />
<h2 id="command-8D">0x8D: Changes unknown element on the right?</h2>

<p>Never occurs in any of the default tracks.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td></td>
        </tr>
        <tr>
            <td>1</td>
            <td>Length?</td>
            <td></td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
    </details>
</p>
<br />
<h2 id="command-8E">0x8E: Left kerb starts</h2>

<p>Used when the start of the kerb shouldn't occur at the start of the section.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Offset into sector</td>
            <td>0, 1, 3, 4, 6 or 29</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Length</td>
            <td>4 to 30</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">4</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">5</td>
                <td class="text-right">7</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">10</td>
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
    </details>
</p>
<br />
<h2 id="command-8F">0x8F: Right kerb starts</h2>

<p>Used when the start of the kerb shouldn't occur at the start of the section.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Offset into sector</td>
            <td>0, 1, 3, 4, 6 or 29</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Length</td>
            <td>4 to 30</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">6</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">5</td>
                <td class="text-right">4</td>
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
    </details>
</p>
<br />
<h2 id="command-90">0x90: Reverse object placement</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0 to 242</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>10 to 150</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">4</td>
                <td class="text-right">15</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">51</td>
                <td class="text-right">0</td>
                <td class="text-right">21</td>
                <td class="text-right">6</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
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
    </details>
</p>
<br />
<h2 id="command-91">0x91: Unknown Monaco command</h2>

<p>Only occurs once, in Monaco</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>Always 10</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-92">0x92: Sector in which unknown action 1 is taken?</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0 to 137</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>7 to 55</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">5</td>
                <td class="text-right">5</td>
                <td class="text-right">6</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">3</td>
                <td class="text-right">4</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">1</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-93">0x93: Sector in which unknown action 2 is taken?</h2>

<p>Never used in any of the default tracks.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td></td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td></td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
    </details>
</p>
<br />
<h2 id="command-94">0x94: Computer car coaching left</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Coaching factor</td>
            <td>1 to 16</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">3</td>
                <td class="text-right">4</td>
                <td class="text-right">0</td>
                <td class="text-right">31</td>
                <td class="text-right">4</td>
                <td class="text-right">4</td>
                <td class="text-right">4</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">2</td>
                <td class="text-right">8</td>
                <td class="text-right">6</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">2</td>
                    <td class="text-right">4</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">4</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-95">0x95: Computer car coaching right</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Coaching factor</td>
            <td>1 to 16</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">3</td>
                <td class="text-right">2</td>
                <td class="text-right">5</td>
                <td class="text-right">17</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">3</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">6</td>
                <td class="text-right">0</td>
                <td class="text-right">7</td>
                <td class="text-right">0</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">2</td>
                    <td class="text-right">4</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">4</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-96">0x96: Pit lane start</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0, 2 or 4</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-97">0x97: Pit lane end</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-98">0x98: Left fence height change</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Height modification</td>
            <td>1 to 8</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">4</td>
                <td class="text-right">0</td>
                <td class="text-right">7</td>
                <td class="text-right">7</td>
                <td class="text-right">4</td>
                <td class="text-right">3</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">1</td>
                    <td class="text-right">3</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">2</td>
                    <td class="text-right">1</td>
                    <td class="text-right">2</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-99">0x99: Right fence height change</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Height modification</td>
            <td>1 to 7</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">2</td>
                <td class="text-right">4</td>
                <td class="text-right">5</td>
                <td class="text-right">13</td>
                <td class="text-right">0</td>
                <td class="text-right">4</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
                <td class="text-right">0</td>
                <td class="text-right">3</td>
                <td class="text-right">3</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">2</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">2</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
                    <td class="text-right">3</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-9A">0x9A: Custom fence height</h2>

<p>Only used in Monaco and Barcelona.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Height identifier</td>
            <td>3, 5, 7 or 8 (but can probably by 1 to 8)</td>
        </tr>
        <tr>
            <td>1</td>
            <td>New height value to be used when previous param used in 0x98,0x99</td>
            <td>256, 384, 1280 or 3200</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">3</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
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
    </details>
</p>
<br />
<h2 id="command-9B">0x9B: Unknown pit lane marker</h2>

<p>Always occurs <em>once</em> per track, in the first section of the pit lane.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>4, 5, 6 or 7</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-9C">0x9C: Unknown pit lane marker 2</h2>

<p>Always occurs <em>once</em> per track, in one of the early pit lane sections.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-9D">0x9D: Unknown pit lane marker 3</h2>

<p>Always occurs <em>once</em> per track, in one of the later pit lane sections.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-9E">0x9E: Unknown pit lane marker 4</h2>

<p>Always occurs <em>once</em> per track, in one of the later pit lane sections, slightly later than command 0x9D.<br/><br />Pit lane end length?</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>3 to 17</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-9F">0x9F: Pit lane fences start</h2>

<p>Always occurs <em>once</em>, in the pit lane.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-A0">0xA0: Pit lane fences end</h2>

<p>Always occurs <em>once</em>, in the pit lane.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-A1">0xA1: Pit lane entry, join right lane fences</h2>

<p>Always occurs <em>once</em> per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-A2">0xA2: Pit lane entry, join left lane fences</h2>

<p>Always occurs <em>once</em> per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-A3">0xA3: Pit lane exit, join right lane fences</h2>

<p>Always occurs <em>once</em> per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-A4">0xA4: Pit lane exit, join left lane fences</h2>

<p>Always occurs <em>once</em> per track, except at Phoenix, for some reason.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-A5">0xA5: Change the sign of the first two sector arguments</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">16</td>
                <td class="text-right">6</td>
                <td class="text-right">7</td>
                <td class="text-right">8</td>
                <td class="text-right">10</td>
                <td class="text-right">2</td>
                <td class="text-right">11</td>
                <td class="text-right">3</td>
                <td class="text-right">6</td>
                <td class="text-right">9</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-A6">0xA6: Set unknown section flags 1</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0, 2 or 5</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>1 to 56</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Unknown</td>
            <td>1 to 14</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">4</td>
                <td class="text-right">1</td>
                <td class="text-right">4</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-A7">0xA7: Set unknown section flags 2</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>0 or 5</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>2 to 82</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Unknown</td>
            <td>1 to 13</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">2</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">3</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
            </tr>
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">2</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-A8">0xA8: Section that triggers the chequered flag</h2>

<p>Defines the track section that triggers the chequered flag man to be visiblewhen driving into it on the final lap.<br /><br />Always occurs just <em>once</em> per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-A9">0xA9: Pit lane view distance</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Distance in which the pitlane can be seen? (default=60?)</td>
            <td>0, 1, 3, 4, 6 or 29</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
            <tr>
                <td>Pit Lane</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">1</td>
                    <td class="text-right">1</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
                    <td class="text-right">0</td>
            </tr>
            </tbody>
        </table>
    </details>
</p>
<br />
<h2 id="command-AA">0xAA: Computer cars pit lane modifier?</h2>

<p></p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown/unused?</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Length for computer cars to angle towards pitlane (backwards)?</td>
            <td>0 to 70</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Length for computer cars to angle out of pits?</td>
            <td>0, 7 or 60</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Computer car pit lane speed</td>
            <td>6656, 11264 or 12800</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">0</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-AB">0xAB: Unknown, maybe unused</h2>

<p>Occurs once per track.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Unknown</td>
            <td>Always 44</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Unknown</td>
            <td>18 to 208</td>
        </tr>
    </tbody>
</table>


<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
                <td class="text-right">1</td>
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
    </details>
</p>
<br />
<h2 id="command-AB">0xAC: Palette change</h2>

<p>The command is used to make minor changes to how the asphalt (gray) and grass (green) look for each track. For example, the asphalt in Mexico is a brighter gray, whilst the asphalt in France is much darker.<br /><br />This command occurs once or twice per track, always in the first section. The tracks where it occurs once are Phoenix and Monaco, which do not have any grass to change the color of.</p>


<h3>Arguments</h3>

<table class="table table-bordered table-striped table--small">
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
            <td>Unknown</td>
            <td>Always 0</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Palette index</td>
            <td>18 (grass) or 26 (asphalt)</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Red color value</td>
            <td>14 to 36</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Green color value</td>
            <td>23 to 42</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Blue color value</td>
            <td>4 to 35</td>
        </tr>
    </tbody>
</table>

<p>
    Changing the color of palette index 26 alters the grey asphalt color. Palette index 18 alters the green grass. Changing any other palette index does not seem to have any effect.<br /><br />Interestingly, changing the green color also affect the color of the in-game messages such as the "Riding with" text.
</p>

<p>
    <details>
        <summary>Occurrences by track</summary>
        
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
    </details>
</p>
