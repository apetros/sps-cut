---
title: Security assessment of Smart Grids using High-Performance Computing
linktitle: DSA
date: '2024-04-24'
type: book
draft: false
weight: 30
---

## Background

Modern [Smart Grids](https://en.wikipedia.org/wiki/Smart_grid) rely on advanced computational tools to provide valuable information to the network operators. One of the most important tools used to ensure the security of Smart Grids are [transient stability simulations](https://en.wikipedia.org/wiki/Power_system_simulation#Transient_stability_simulation). They analyse the behaviour of Smart Grid models in time after a disturbance has occurred (loss of generation, lightning hitting a line, etc.). 

To ensure the reliability of electricity grids, these are designed with [N+1 redundancy](https://en.wikipedia.org/wiki/N%2B1_redundancy), meaning that they can lose any one component and the system should survive and remain within acceptable operating limits. To ensure this feature, system operators routinely perform a so-called N-1 security assessment: they simulate the loss of any one single component in the Smart Grid and check that all of them lead to a secure operation.

As this procedure is extremely time consuming, cluster computing is frequently used by executing the different simulations in parallel and aggregating their results.

## Objectives

In this project, you have to develop a security assessment platform that exploits parallel computing on the university cluster computer to check N-1 conditions in a realistic Smart Grid. You will use the dynamic simulator PyRAMSES[^PyRAMSES] to perform the actual simulations and get the results through a Python-based interface. The platform should be implemented in Python.

{{< figure src="../img/HPC_decorative_photos.png" title="The ARC HPC systems [Source: ARC]" >}}

## Deliverables

- A complete literature review including a comparison between different methods currently used for N-1 security assessment in Smart Grids.
- An N-1 security platform implemented in Python. It should receive a list of contingencies to be analysed and the security constraints to be satisfied and provide a detailed result.
- Interface to cloud services to submit and analyse the tasks (exporting to Dropbox, mobile notifications, etc.).

## Student profile

- Good analytical skills.
- Good programming skills (Python -- or willingness to learn fast).
- Knowledge in Linux is desirable (or willingness to learn fast).
- Good background in electric power systems (minimum [Power Systems I]({{< ref "/courses/een320/_index.md">}})).

[^PyRAMSES]: [PyRAMSES: Python-based RApid Multithreaded Simulation of Electric power Systems](https://pyramses.paristidou.info/)

Before asking any questions, please check the [FAQ]({{< relref "faq.md" >}}).