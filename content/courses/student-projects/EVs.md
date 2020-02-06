---
title: Impact of Electric Vehicles on a Distribution Grid
linktitle: Electric Vehicles
toc: true
type: docs
date: "2020-02-05T00:00:00Z"
draft: false
menu:
  student-projects:
    parent: Overview
    weight: 13

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 13
---

## Background

Electrification of transportation[^EV] is one of the main drivers for carbon reduction in modern societies. Most countries today are providing incentives for the replacement of conventional ICE cars with electric or hybrid ones.

These cars will be hosted in the existing Distribution Networks (DNs) and might cause severe issues related to congestion and power quality. If these problems are not analysed and addressed, the penetration of EVs will be hindered and delayed.

{{< youtube 2kILi7VrYLE >}}

## Objectives

In this project, you have to analyse the impact of EVs as passive resources on a Cypriot distribution network[^R1]. This will involve understanding the structure of DNs and their limitations, modeling of different power components, and analysing power quality issues. Moreover, you will need to extract the EV driving patterns and charging scenarios relevant to the cypriot DNs and analyse the impact of different combinations through a stochastic method to account for uncertainty. Some references are [^P1] and [^P2].

This project requires excellent *programming* and *analytical* skills. It is in collaboration with [EAC](http:/www.eac.com.cy).

## Deliverables

- A complete literature review for methodologies to assess the impact of passive EVs to DNs.
- Model a representative Cypriot DN system in Matlab or Python.
- Develop a feeder load modeling estimation algorithm.
- Develop a method to assess impact of EVs on the power quality of DNs.
- All the code developed should be documented and published on [GitHub](https://github.com/) under an MIT License[^GitHubLIC].

[^EV]: [Global EV Outlook 2019](https://www.iea.org/reports/global-ev-outlook-2019)
[^R1]: [A review of computer tools for modeling electric vehicle energy requirements and their impact on power distribution networks](https://www.sciencedirect.com/science/article/pii/S0306261916304275)
[^P1]: [Stochastic Analyses of Electric Vehicle Charging Impacts on Distribution Network](https://ieeexplore.ieee.org/document/6678651)
[^P2]: [Optimal Use of Existing Distribution Feeders to Accommodate Transportation Electrification](https://ieeexplore.ieee.org/document/7047852)
[^GitHubLIC]: [GitHub: Licensing a repository](https://help.github.com/articles/licensing-a-repository/)

Please, before asking any questions, please check the [FAQ]({{< relref "faq.md" >}}).