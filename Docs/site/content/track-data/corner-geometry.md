---
title: "ArgDocs: Track Corner Geometry"
---

# Track Corner Geometry

The two values in a [track section](/argdocs/file-formats/track/track-sections/) that describe a corner in an F1GP track
are the _curvature_ and the _length_.

The _curvature_ value defines how tight a corner is.

The allowed _curvature_ value for a corner goes from -32,768 to 32,768, where a positive value indicates a right-hand
corner, and a negative value indicates a left-hand turn. A value of 0 thus means that the section is a straight.

The curvature value is converted to indicate the length of the radius of an imagined circle on the inside of the corner,
like this:

<img src="/argdocs/images/track/geometry-radius.png" alt="Corner geometry: Radius" class="img-fluid" />

In these two examples, the first corner has a smaller _curvature_ value for the individual corner sections,
and is therefore not as tight as the following corner, which has a larger _curvature_ value.

The radius for an imagined circle on the inside of the corner is calculated according to the following formula:

1 / (_curvature_ * 2 * 𝜋 / 65536)

Examples of calculated radius values:

<table class="table table-bordered table-striped table--tiny">
    <thead>
        <tr>
            <th>Curvature</th>
            <th>Radius (calculated)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>10,430.378350470453</td>
        </tr>
        <tr>
            <td>256</td>
            <td>40.743665431525208</td>
        </tr>
        <tr>
            <td>512</td>
            <td>20.371832715762604</td>
        </tr>
        <tr>
            <td>1024</td>
            <td>10.185916357881302</td>
        </tr>
        <tr>
            <td>2048</td>
            <td>5.0929581789406511</td>
        </tr>
        <tr>
            <td>2731</td>
            <td>3.8192524168694444</td>
        </tr>
        <tr>
            <td>4096</td>
            <td>2.5464790894703255</td>
        </tr>
        <tr>
            <td>8192</td>
            <td>1.2732395447351628</td>
        </tr>        
        <tr>
            <td>16,384</td>
            <td>0.63661977236758138</td>
        </tr>
        <tr>
            <td>32,768</td>
            <td>0.31830988618379069</td>
        </tr>
    </tbody>
</table>

So as you can see, the larger the curvature value, the smaller the radius.


### Example: 90&deg; corners

To create a 90&deg; corner, the _curvature_ multiplied by the _length_ must be approximately 16,384.

In the first example, we have a 90&deg; corner with three sections.

<img src="/argdocs/images/track/geometry-90-1.png" alt="90 degree corner" class="img-fluid" />

In this case, the _curvature_ value for each section is 910, and the _length_ of each section is 6.

This gives us the following calculation: 910 x 6 x 3 = 16,380.

In the next example, we have another 90&deg; corner with three sections, but the corner is noticably tighter.

<img src="/argdocs/images/track/geometry-90-2.png" alt="Tighter 90 degree corner" class="img-fluid" />

The _curvature_ value for these sections is larger than the previous one, 2,730, but the _length_ is lower, at 2 each.

This gives us the following calculation: 2,730 x 2 x 3 = 16,380.

So, as you can see, the total value for each corner is the same but by adjusting the _curvature_ and _length_ values
differently, the corners are tighter or wider.
