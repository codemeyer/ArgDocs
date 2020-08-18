---
title: "ArgDocs: F1GP Track File Format - Computer Car Setup and Behavior"
---

# Computer Car Setup and Behavior (Track File Format)

Contains the [default computer car setup](/argdocs/track-data/default-setups/),
and various computer car behavior.

Always 38 bytes.

<table class="table table-bordered table-striped table--medium">
    <thead>
        <tr>
            <th class="text-right">Index</th>
            <th>Type</th>
            <th>Description</th>
            <th>Comment</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="text-right">$CCS</td>
            <td>byte</td>
            <td>Front wing</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+1</td>
            <td>byte</td>
            <td>Rear wing</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+2</td>
            <td>byte</td>
            <td>1st Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+3</td>
            <td>byte</td>
            <td>2nd Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+4</td>
            <td>byte</td>
            <td>3rd Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+5</td>
            <td>byte</td>
            <td>4th Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+6</td>
            <td>byte</td>
            <td>5th Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+7</td>
            <td>byte</td>
            <td>6th Gear Ratio</td>
            <td>Subtract 151 to get actual value</td>
        </tr>
        <tr>
            <td class="text-right">+8</td>
            <td>byte</td>
            <td>Tyre Compound</td>
            <td>52=A, 55=D, actual compound used may vary</td>
        </tr>
        <tr>
            <td class="text-right">+9</td>
            <td>byte</td>
            <td>Brake Balance</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+10</td>
            <td>short</td>
            <td>Grip Factor</td>
            <td>Multiplies driver corner speed factor</td>
        </tr>
        <tr>
            <td class="text-right">+12</td>
            <td>short</td>
            <td>CC non-race late braking factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+14</td>
            <td>short</td>
            <td>CC race late braking factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+16</td>
            <td>short</td>
            <td>Time factor non-race</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+18</td>
            <td>short</td>
            <td>Acceleration</td>
            <td>16384 everywhere except Mexico, where it's 13017</td>
        </tr>
        <tr>
            <td class="text-right">+20</td>
            <td>short</td>
            <td>Air Resistance</td>
            <td>16384 everywhere except Mexico, where it's 13017</td>
        </tr>
        <tr>
            <td class="text-right">+22</td>
            <td>short</td>
            <td>Tyre wear qualifying</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+24</td>
            <td>short</td>
            <td>Tyre wear non-qualifying</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+26</td>
            <td>short</td>
            <td>Fuel load</td>
            <td>100% race, measured in pounds (lbs). Fuel is consumed linearly with the distance covered. Shorter races decrease the fuel load.</td>
        </tr>
        <tr>
            <td class="text-right">+28</td>
            <td>short</td>
            <td>Time factor race</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+30</td>
            <td>short</td>
            <td>CC power factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+32</td>
            <td>short</td>
            <td>CC wet race late braking factor</td>
            <td></td>
        </tr>
        <tr>
            <td class="text-right">+34</td>
            <td>short</td>
            <td>Unknown</td>
            <td>Some track distance in feet</td>
        </tr>
        <tr>
            <td class="text-right">+36</td>
            <td>short</td>
            <td>Default pit lane view distance</td>
            <td></td>
        </tr>
    </tbody>
</table>


[Back to F1GP Track File Format](/argdocs/file-formats/track/)
