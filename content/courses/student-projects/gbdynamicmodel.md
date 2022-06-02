---
title: Development of a dynamic equivalent model of the Great Britain electric transmission system
linktitle: GB test system
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

Modern [Smart Grids](https://en.wikipedia.org/wiki/Smart_grid) rely on advanced computational tools to analyse the security of the system and provide valuable information to the network operators. Thus, it is necessary to develop appropriate dynamic models of the electricity grids to be used in the computations. The luck of accurate and validated dynamic models can endanger the security of the system.

## Objectives

In this project, you have to develop a dynamic model of the GB to be used with the dynamic simulator RAMSES[^RAMSES]. The model will be based on the preliminary work in [^Imperial].

## Deliverables

- A complete literature review including a comparison between different existing power system dynamic models.
- A dynamic model of the GB system suitable for simulations with RAMSES[^RAMSES].
- An analysis of the system behaviour (transient behaviour to disturbances, load variation, etc.)
- All the code developed should be documented and published on [GitHub](https://github.com/) under an MIT License[^GitHubLIC].

## Student profile

- Good analytical skills (eigenanalysis, linear algebra, system modelling, etc.).
- Good programming skills (Python or willingness to learn fast).
- Background in electric power systems (minimum [Power Systems I]({{< ref "/courses/een320/_index.md">}})).

[^kundur]: Kundur, P., Balu, N. J., & Lauby, M. G. (1994). Power system stability and control. New York: McGraw-Hill.
[^RAMSES]: [RAMSES: RApid Multithreaded Simulation of Electric power Systems](http://www.montefiore.ulg.ac.be/~vct/software.html)
[^Imperial]: [A Test System Model for Stability Studies of UK Power Grid](https://spiral.imperial.ac.uk/bitstream/10044/1/15446/2/KunjumuhammedEtAlTestSystemStabilityStudies_IEEEPowerTech2013_AuthorFinalVersion.pdf)
[^GitHubLIC]: [GitHub: Licensing a repository](https://help.github.com/articles/licensing-a-repository/)

Before asking any questions, please check the [FAQ]({{< relref "faq.md" >}}).
