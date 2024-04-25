---
title: Development of a low-cost MicroPMU (µPMU)
linktitle: MicroPMU
date: '2021-01-01'
type: book
weight: 20
draft: true
---

## Background

Future [Smart Grids](https://en.wikipedia.org/wiki/Smart_grid) will strongly rely on remote sensing and Information Communication Technologies (ICT) for their day to day operation. Through a complex and highly sophisticated layer of sensing and ICT technologies, Smart Grids can increase their on-line system awareness allowing them to operate more securely and reliably, while at the same time safely increasing the penetration of sustainable energy sources and reducing carbon emission.

One of the most advanced and accurate tools available today are synchrophasor technologies that use monitoring devices called Phasor Measurement Units (PMUs)[^PMU1]. These units can be installed in remote locations to measure the instantaneous voltage, current, and frequency, and provide valuable information to the system operator about the status of the system in that area (see Fig. 1 from ref [^PMU5]). Through a combination of advanced sensing, local processing, and ICT technologies, these units can deliver the required performance (accuracy and speed) to develop a truly Smart Grid.

{{< figure src="../img/Synchrophasor.png" title="Synchrophasor wide-area monitoring and detection framework" >}}

Unfortunately, the high cost of PMUs has limited their use only in the high-voltage (transmission) networks, leaving the low-voltage (distribution) networks lacking proper sensing tools. As low-voltage networks will be hosting the majority of new renewable energy sources and electric vehicles, there is a need to increase the sensing capabilities of these systems. Thus, low-cost alternatives to the PMU are currently being developed, the microPMUs (µPMUs)[^PMU2][^PMU3][^PMU4]. These are devices with lower capabilities but still very powerful sensing capabilities, at a significantly smaller price and size, targeting low-voltage grids.

## Objectives

In this project, you have to develop a low-cost µPMU. This will involve understanding the critical functionality of µPMUs in the future sustainable energy systems, designing a complete µPMU based on the methodology of [^Digikey], sourcing the appropriate material, and building a complete low-voltage prototype.

{{< figure src="../img/mPMU-schem.jpg" title="Simplified Phasor Measurement Unit block diagram" >}}

## Deliverables

- A complete literature and market review including a comparison between different existing µPMU technologies.
- A complete design of an affordable µPMU.
- A working prototype of a µPMU.
- An online cloud platform to receive and display the µPMU data.

## Student profile

- Good programming skills (microcontrollers).
- Good electronics design background.
- Good signals processing and filtering background.
- Good background in electric power systems (minimum [Power Systems I]({{< ref "/courses/een320/_index.md">}})).

[^PMU1]: [Synchrophasor Technologies and their Deployment in the Recovery Act Smart Grid Programs](https://www.smartgrid.gov/files/Synchrophasor_Report_08_09_2013_DOE_2_version_0.pdf)
[^PMU2]: [Micro-synchrophasors (µPMUs) for Distribution Systems](http://www.arpae-summit.com/paperclip/exhibitor_docs/15AE/CIEE-UC_Berkeley_Power_Standards_Lab_419.pdf)
[^PMU3]: [Micro-Synchrophasors for Power Distribution Monitoring, a Technology Review](https://arxiv.org/ftp/arxiv/papers/1605/1605.02813.pdf)
[^PMU4]: [Synchrophasors for Distribution, Microgrids: PQube 3 MicroPMU Data Sheet](http://www.powersensorsltd.com/Download/MicroPMU%20Data%20Sheet%20Rev1_3.pdf)
[^PMU5]: Yuanjun Guo, Kang Li, Zhile Yang, Jing Deng, David M. Laverty, [A novel radial basis function neural network principal component analysis scheme for PMU-based wide-area power system monitoring](https://doi.org/10.1016/j.epsr.2015.06.002), In Electric Power Systems Research, Volume 127, 2015, Pages 197-205, ISSN 0378-7796
[^Digikey]: [Low-Cost Microcontroller-Based Phasor Measurement Units Improve Smart Grid Reliability](https://www.digikey.com/en/articles/techzone/2014/jan/low-cost-microcontroller-based-phasor-measurement-units-improve-smart-grid-reliability)

Before asking any questions, please check the [FAQ]({{< relref "faq.md" >}}).
