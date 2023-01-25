---
title: Mini project
linktitle: Mini project
date: '2021-01-01'
type: book
weight: 20
math: true
draft: true
---

## Overview

This project is designed to train the students into using computational tools to apply the knowledge gained in the course. It is split into three parts:

1. Power flow modeling and analysis.
2. Short circuit analysis.
3. Protection design.

At the end of the project, the students will need to submit a report and a Jupyter Notebook file with the implementation. The report can be embedded in the Jupyter notebook, if you want, or submitted as two separate files.

{{% callout note  %}}
The report is individual for each student.
{{% /callout %}}

### Delivery

- Moodle
- Deadline: TBD

### Preliminaries

- The project should be completed with the Python-based tool [Pandapower](https://pandapower.org). The full documentation is found [here](https://pandapower.readthedocs.io/en/v2.4.0/).
- You can find [a short introduction](http://www.pandapower.org/start/#a-short-introduction-), several [interactive tutorials](http://www.pandapower.org/start/#interactive-tutorials-), and some [YouTube tutorial videos](https://www.youtube.com/c/pandapowerorg/videos?view_as=subscriber).
- Our lab's server is located at [this address](https://sps.cut.ac.cy/jhub) and each student has an individual account with all the necessary software pre-installed. 
- Your username is your email (without the @edu.cut.ac.cy). The password is the one you use the *first time you log in*.

{{% callout warning  %}}
The server is not backed up, so you should make sure you download your work on your computer after each session.
{{% /callout %}}


## Part 1: Power flow modeling and analysis

In this part, you need to model and analyze the following system in Pandapower.

{{< figure src="diagram.png" title="Test-system one-line diagram" numbered="true" >}}

### System parameters

- **External Grid**: Maximum short-circuit power 100 MVA, minimum short-circuit capacity 80 MVA, maximum R/X ratio 0.35, and minimum short-circuit ratio is 0.20
- **T1**: Pandapower standard type[^1] transformer *25 MVA 110/20 kV*
- **T2, T3, T4**: Pandapower standard type transformer *0.4 MVA 20/0.4 kV*
- **Line B2-B3**: Pandapower standard type line *NA2XS2Y 1x95 RM/25 12/20 kV*, 5 km length
- **Line B2-B4**: Pandapower standard type line *NA2XS2Y 1x95 RM/25 12/20 kV*, 6 km length
- **Line B2-B5**: Pandapower standard type line *NA2XS2Y 1x95 RM/25 12/20 kV*, 7 km length
- **Line B2-B6**: Pandapower standard type line *NA2XS2Y 1x95 RM/25 12/20 kV*, 6 km length
- **Motor M3**: 10 MVA rated motor, operated at 3 MW active and 1 MVAr reactive power consumption. Ratio of nominal current to short circuit current is 1.2 and R/X ratio is 7. You can use the [sgen model](https://pandapower.readthedocs.io/en/v2.0.0/elements/sgen.html) with type "motor".
- **LV lines**: All low-voltage lines are Pandapower standard type line *48-AL1/8-ST1A 0.4* with 100m length.
- **LV loads**: All low-voltage loads (households) have a consumption of 2.2 kW at a power factor 0.95 inductive.


[^1]: Pandapower standard type components are available [here](https://pandapower.readthedocs.io/en/v2.4.0/std_types.html)

{{% callout note  %}}
In a real system there would be multiple feeders connected to each MV-LV transformer.
{{% /callout %}}

### Tasks

1. Model the test system in Pandapower[^2].
   - What is the type of the 20 kV lines used? What information can you find from manufacturers? Is this typical for MV systems?
   - What is the type of the 400 V lines used? What information can you find from manufacturers? Is this typical for LV systems?
   - Is this a radial or meshed system? Is this typical for distribution networks? Why?
2. Run a power flow and display all the bus voltages, line currents, and transformer loadings.
   - Are there any violations of voltage[^3], line, or transformers?
   - Create and display a [colormap](https://pandapower.readthedocs.io/en/v2.0.0/plotting/matplotlib/create_colormaps.html) of the buses showing blue for all voltages below 0.95, green for voltages between 0.95 and 1.05, and red for all voltages above 1.05 pu.
3. Consider that the power consumption of every household is increased to 4 kW at 0.95 power factor and solve the power flow.
   - Are there any violations of voltage, line, or transformers?
   - Create and display a [colormap](https://pandapower.readthedocs.io/en/v2.0.0/plotting/matplotlib/create_colormaps.html) of the buses showing blue for all voltages below 0.95, green for voltages between 0.95 and 1.05, and red for all voltages above 1.05 pu.
4. If we consider that each house will purchase an electric vehicle with a 7 kW charger (in addition to their normal 2 kW with PF=0.95 load) and they want to charge at the same time.
   - Is the system able to withstand this load?
   - If no, propose some solutions to alleviate the problem.


[^2]: Follow the [example shown in class](https://github.com/panda-power/pandapower/blob/master/tutorials/minimal_example.ipynb) and the [simple network tutorial](https://github.com/e2nIEE/pandapower/blob/master/tutorials/create_simple.ipynb)
[^3]: Assume a 5% deviation to be acceptable.

## Part 2: Short circuit analysis

The utility company needs to design the protections for the MV-LV system of the previous part. Before starting this part, read the [documentation](https://pandapower.readthedocs.io/en/v2.4.0/shortcircuit.html) and [tutorial](https://github.com/e2nIEE/pandapower/blob/master/tutorials/shortcircuit.ipynb).

### Tasks

1. Compute the maximum three-phase short-circuit currents for a solid fault ($Z_F = 0\ \Omega$).
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each bus.
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each line.
   - What is the difference between the three values of current computed at each node or line?
   - Which standard is used to compute the short-circuit currents? Briefly explain the methodology based on the documentation, the slides of the course, and material you find online.
2. Deactivate the contribution of the large motor[^4] and recompute the maximum three-phase short-circuit currents for a solid fault ($Z_F = 0\ \Omega$).
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each bus.
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each line.
   - Compare to the values of Task 1 and explain the difference.
3. Compute the maximum three-phase short-circuit currents with fault impedance $Z_F = 1+j1.5\ \Omega$.
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each bus.
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each line.
   - Compare to the values of Task 1 and explain the difference.
4. Compute the maximum two-phase short-circuit currents for a solid fault ($Z_F = 0\ \Omega$).
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each bus.
   - Present the initial symmetrical short-circuit current, the short-circuit current peak, and the equivalent thermal short-circuit current at each line.
   - Compare to the values of Task 1 and explain the difference.

[^4]: This can be done by executing the command `net.sgen.in_service = False` before computing the short-circuit currents. Don't forget to reset back to `net.sgen.in_service = True` before moving to the next task.

## Part 3: Protection design

Consider the two breakers shown in this figure:

{{< figure src="diagram2.png" title="Test-system one-line diagram" numbered="true" >}}

- Assume the maximum load over the operating life of the radial system is the one analyzed in Part 1-Task 4.
- Assume the maximum fault current at each bus is the one computed in Part 2-Task 1.
- Assume the minimum fault current at each bus is the one computed in Part 2-Task 4.
- Assume a  0.3 second coordination time interval.

| Breaker | breaker activation time | CT Ratio|Type|
|---------|-------------------------|---------|---|
|BrA|5 cycles |4:1|IEC 60255, SI|
|BrB|5 cycles |37:1|IEC 60255, SI|

### Tasks

1. Select current settings (CSs) and Time Multiplier Setting (TMS) to protect the system from faults.
   - Which fault current value did you use for the calculations? (initial symmetrical short-circuit current, short-circuit current peak, or equivalent thermal short-circuit current)
   - Give the total activation time for each breaker.
2. For the values computed in the previous task, verify coordination for minimum fault currents. That means, verify that with the minimum fault currents, the coordination time interval and sequence of activation is still obeyed.