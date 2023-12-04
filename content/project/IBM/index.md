---
title: IBM
summary: Numerical simulation of digital controllers
tags:
- Current projects
- digital controllers
- events
date: "2023-01-29T00:00:00Z"

profile: false  # Show author profile?

# Optional external URL for project (replaces project detail page).
external_link: 

image:
  caption: IBM
  focal_point: Time steps
---

## Summary

The interpolation-based method (IBM) provides an accurate and computationally fast method to integrate the digital controllers in large time steps over multiple time events without reducing the time step. This is made possible by interpolating the state variables of the system at each digital controller sampling time and including the controller output in the DAEs model. In this way, the outputs of the controllers are estimated and corrected at each Newton iteration.
