---
title: Protection analysis in low-inertia Distribution Grids with Renewables
linktitle: DN Protection
date: '2024-04-24'
type: book
draft: false
weight: 60
---

## Background and Objectives

Distributed Energy Resources (DERs), such as photovoltaics and wind-turbines, are connected in low-voltage Distribution Networks (DNs) are protected by unit protection mechanisms, such as ROCOF protection, over-/under-frequency protection, etc., to avoid damage to the units and the system. Modern power systems face an increasing penetration of inverter-interfaced DERs and loads, thus reducing the amount of conventional generators (steam, gas, etc.) connected to the grid and providing inertia.

In this project, you have to analyse the impact of increased DER penetration and decreased inertia to the protections of DERs. You will develop a dynamic model of the Cyprus DN, incorporating increasing number of PVs with standard unit protection. Then, a sensitivity analysis will be performed to identify the penetration limits and the optimal setpoints of the protection parameters. You will use the dynamic simulator PyRAMSES[^PyRAMSES] to perform the actual simulations and get the results through a Python-based interface.

This project requires excellent *programming* and *analytical* skills. It is in collaboration with [EAC](http:/www.eac.com.cy).

## Deliverables

- A complete literature review for sensitivity analysis of RES penetration to DER protection.
- Model a positive sequence dynamic model of a Cyprus DNs with PV generation.
- Analyse the dynamic performance and protection violations of the system through scenario-based analysis.
- Provide recomendations concerning the parameter estimation of protection devices.

## Student profile

- Good analytical skills (eigenanalysis, linear algebra, system modelling, etc.).
- Good programming skills (Python or willingness to learn fast).
- Background in electric power systems (minimum [Power Systems I]({{< ref "/courses/een320/_index.md">}})).

[^PyRAMSES]: [PyRAMSES: Python-based RApid Multithreaded Simulation of Electric power Systems](https://pyramses.paristidou.info/)

Before asking any questions, please check the [FAQ]({{< relref "faq.md" >}}).
