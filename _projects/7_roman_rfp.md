---
layout: page
title: Roman WFI Reference File Pipeline
description: Automated calibration reference files for Roman's Wide Field Instrument
img: assets/img/proj_roman_rfp.jpg
importance: 1
category: mission
---

Roman's Wide Field Instrument has 18 near-infrared detectors, each needing its own calibration reference files (darks, flats, read noise, linearity and more) generated quickly and consistently enough to keep up with Roman's data volume. I lead development of the **Reference File Pipeline (RFP)**, a modular, configuration- and database-driven system that creates, validates, tracks and delivers these files to STScI's Calibration Reference Data System (CRDS).

{% include figure.liquid loading="eager" path="assets/img/proj_roman_rfp.jpg" title="18 WFI detectors (schematic)" class="img-fluid rounded z-depth-1" %}

- A standardized, object-oriented architecture shared by every reference file type
- Real-time, multi-stage quality control and automated CRDS delivery with full provenance
- Integration with the Roman Data Monitoring Tool (RDMT), so trends in delivered products feed back into improved new versions
- CI/CD, unit and regression testing, and automated documentation

**Code:** [spacetelescope/roman-wfi-reference-pipeline](https://github.com/spacetelescope/roman-wfi-reference-pipeline)
**Reports:** Roman-STScI-000811 (2026); Roman-STScI-000678 (2024)
