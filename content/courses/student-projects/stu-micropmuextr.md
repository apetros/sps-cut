---
title: Comparison of different phasor extraction techniques in MicroPMUs (µPMUs)
linktitle: 
toc: true
type: docs
date: "2022-02-05T00:00:00Z"
draft: true
menu:
  student-projects:
    parent: Overview
    weight: 11

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 11
---


## Background

Future [Smart Grids](https://en.wikipedia.org/wiki/Smart_grid) will strongly rely on remote sensing and Information Communication Technologies (ICT) for their day to day operation. Through a complex and highly sophisticated layer of sensing and ICT technologies, Smart Grids can increase their on-line system awareness allowing them to operate more securely and reliably, while at the same time safely increasing the penetration of sustainable energy sources and reducing carbon emission.

One of the most advanced and accurate tools available today are synchrophasor technologies that use monitoring devices called Phasor Measurement Units (PMUs)[^PMU1]. These units can be installed in remote locations to measure the instantaneous voltage, current, and frequency, and provide valuable information to the system operator about the status of the system in that area. Through a combination of advanced sensing, local processing, and ICT technologies, these units can deliver the required performance (accuracy and speed) to develop a truly Smart Grid.

{{< figure src="/img/projects/Synchrophasor.png" title="Synchrophasor wide-area monitoring and detection framework" attr="[source]" attrlink="https://doi.org/10.1016/j.epsr.2015.06.002">}}

Unfortunately, the high cost of PMUs has limited their use only in the high-voltage (transmission) networks, leaving the low-voltage (distribution) networks lacking proper sensing tools. As low-voltage networks will be hosting the majority of new renewable energy sources and electric vehicles, there is a need to increase the sensing capabilities of these systems. Thus, low-cost alternatives to the PMU are currently being developed, the microPMUs (µPMUs)[^PMU2][^PMU3][^PMU4]. These are devices with lower capabilities but still very powerful sensing capabilities, at a significantly smaller price and size, targeting low-voltage grids.

## Objectives

In this project, you have to investigate different phasor extraction techniques used in µPMUs. You will need to implement several techniques on a low-cost microprocessor and compare their performance and computational requirements.

{{< figure src="/img/projects/mPMU-schem.jpg" title="Simplified Phasor Measurement Unit block diagram" attr="[source]" attrlink="https://www.digikey.com/en/articles/techzone/2014/jan/low-cost-microcontroller-based-phasor-measurement-units-improve-smart-grid-reliability">}}

## Deliverables

- A complete literature and market review including a comparison between different existing µPMU phasor extraction techniques.
- Implementation of at least two different phasor extraction techniques on a low-cost microprocessor of your choice.
- All the code developed should be documented and published on [GitHub](https://github.com/) under an MIT License[^GitHubLIC]. The final code (along with all other supplementary files) should be published on [Zenodo](http://www.zenodo.org/) and the DOI included in the final report[^ZenDOI].

[^PMU1]: [Synchrophasor Technologies and their Deployment in the Recovery Act Smart Grid Programs](https://www.smartgrid.gov/files/Synchrophasor_Report_08_09_2013_DOE_2_version_0.pdf)
[^PMU2]: [Micro-synchrophasors (µPMUs) for Distribution Systems](http://www.arpae-summit.com/paperclip/exhibitor_docs/15AE/CIEE-UC_Berkeley_Power_Standards_Lab_419.pdf)
[^PMU3]: [Micro-Synchrophasors for Power Distribution Monitoring, a Technology Review](https://arxiv.org/ftp/arxiv/papers/1605/1605.02813.pdf)
[^PMU4]: [Synchrophasors for Distribution, Microgrids: PQube 3 MicroPMU Data Sheet](http://www.powersensorsltd.com/Download/MicroPMU%20Data%20Sheet%20Rev1_3.pdf)
[^GitHubLIC]: [GitHub: Licensing a repository](https://help.github.com/articles/licensing-a-repository/)
[^ZenDOI]: [Zenodo help](http://help.zenodo.org/)

Please, before asking any questions, please check the [FAQ]({{< ref "stu-faq.md" >}}).
