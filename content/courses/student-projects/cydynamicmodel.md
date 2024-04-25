---
title: Dynamic security of the Cyprus low-inertia transmission system
linktitle: CY Low Inertia
date: '2024-04-24'
type: book
draft: false
weight: 40
---

## Background

The high penetration of RES in Modern [Smart Grids](https://en.wikipedia.org/wiki/Smart_grid) leads to the decommissioning of synchronous generators that traditionally provided the necessary support to ensure the security and stability of power systems. Thus, the resulting power systems exhibit a wide range of security and stability problems, labeled as "low-inertia" problems [^lowinertia]. It is imperative to analyze these problems, using dynamic system models and future energy scenarios, and to develop solutions that will mitigate the impact.

## Objectives

In this project, you have to translate the dynamic model of the Cyprus into the dynamic simulator PyRAMSES[^PyRAMSES]. Following, an analysis will be performed using different future energy scenarios and solutions will be provided to enhance the stability of the Cyprus system.

## Deliverables

- A complete literature review on the problems of future low-inertia grids, like the Cyprus system[^lowinertia].
- A Python-based translator from DigSilent PowerFactory format to PyRAMSES[^PyRAMSES]. This translator will be used to generate the Cyprus dynamic system in PyRAMSES format.
- An analysis of the system behaviour (transient behaviour to disturbances, load variation, etc.)
- Proposed solutions based on storage or artificial inertia.

## Student profile

- Good analytical skills.
- Good programming skills (Python or willingness to learn fast).
- Background in electric power systems (minimum [Power Systems I]({{< ref "/courses/een320/_index.md">}})).

[^lowinertia]: Milano, F., Dörfler, F., Hug, G., Hill, D. J., & Verbič, G. (2018, June). [Foundations and challenges of low-inertia systems](https://people.ee.ethz.ch/~floriand/docs/Articles/PSCC_2018_Survey.pdf). In 2018 power systems computation conference (PSCC) (pp. 1-25). IEEE.
[^PyRAMSES]: [RAMSES: RApid Multithreaded Simulation of Electric power Systems](http://pyramses.sps-lab.org)

Before asking any questions, please check the [FAQ]({{< relref "faq.md" >}}).
