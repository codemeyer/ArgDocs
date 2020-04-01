---
title: "ArgDocs: F1GP Checksum"
---

# F1GP Checksum

The checksum consists of two parts that are two bytes each.

To calculate the first part, add up the sum of all bytes in the file
(excluding the final four checksum bytes)
and then only take the least significant 16 bits (i.e. two bytes)

The second part is calculated by stepping through each byte in the file (excluding the final four checksum bytes), continuously left-rotating the second part by three and adding the current byte value. 

* [Example in C](http://www.waa63.ch/racesim/TEIC/primer/checksum.c)
* [Example in C#](https://github.com/codemeyer/ArgData/blob/master/Source/ArgData/ChecksumCalculator.cs)

But the easiest way to update the checksum after you have edited a file is to use
a purpose-built tool, such as [ArgSum](https://github.com/codemeyer/ArgSum).
