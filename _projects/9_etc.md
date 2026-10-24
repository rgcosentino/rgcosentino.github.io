---
layout: page
title: Calibration-driven Exposure Time Calculator
description: Feeding Roman's ETC directly from calibration reference files
img: assets/img/proj_etc.jpg
importance: 3
category: mission
---

The Exposure Time Calculator previously relied on hand-populated configuration files, which isn't feasible for 18 detectors with distinct characteristics. I led development of CRDS-compatible ETC reference files that the RFP populates automatically from the latest read noise, dark and flat calibrations, so the ETC stays in step with each calibration update.

{% include figure.liquid loading="eager" path="assets/img/proj_etc.jpg" title="Signal-to-noise curves (schematic)" class="img-fluid rounded z-depth-1" %}
