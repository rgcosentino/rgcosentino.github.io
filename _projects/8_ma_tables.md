---
layout: page
title: Multi-Accumulation Tables
description: Programmatic generation of Roman's exposure definitions
img: assets/img/proj_matable.jpg
importance: 2
category: mission
---

The Multi-Accumulation (MA) Table defines how every WFI exposure is executed: its structure, timing, data volume and readout strategy. Roman groups reads into non-evenly spaced "resultants" to achieve high dynamic range and better cosmic-ray rejection, which makes building the table by hand impractical.

{% include figure.liquid loading="eager" path="assets/img/proj_matable.jpg" title="Non-uniform resultant sampling (schematic)" class="img-fluid rounded z-depth-1" %}

I started the fully programmatic code base that now generates this nearly 10,000-line XML file. The project has since moved to its own repository within the Roman Telescope Branch, with checksum validation and differencing.
