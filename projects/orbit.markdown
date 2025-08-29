---
layout: single
title: UBC Orbit Satellite Design Team
permalink: /docs/projects/orbit/
sidebar:
  nav: "docs"

header:
  overlay_image: /images/headers/earth_orbit_2.jpg
  caption: "Image credit: rawpixel (CC BY)"

classes: wide
---

# UBC Orbit

I am a member of UBC Orbit, the University of British Columbia's Satellite Design Team. We are currently working on ALEASAT, a CubeSat that will be used by amateur radio operators to request images of Earth to assist with disaster relief. ALEASAT is supported by the European Space Agency's Fly Your Satellite! Program.

## Firmware
From September 2024 - May 2025, I worked as a firmware developer on the command and data handling subteam. My main accomplishment was implementing a command to measure the CPU usage of tasks in a real-time operating system (FreeRTOS).

## Attitude and Orbit Control Systems
I am currently (as of May 2025) a member of the Attitude and Orbit Control Systems (AOCS) subteam. I am working on a team of five to design and build a Helmholtz cage to simulate the magnetic field of low Earth orbit (LEO).

### Helmholtz Cage
A Helmholtz coil is a pair of identical coils, aligned along the same axis, separated by a distance equal to the coil radius, and carrying equal currents in the same direction. This creates an extremely uniform magnetic field in a region midway between the two coils in the axis perpendicular to the two coils. Using three Helmholtz coils, oriented along the x, y, and z axes, we can generate a uniform magnetic field in any direction, and cancel the Earth's field entirely. 

So far, my work on this project has focused on reviewing prior literature and developing models in MATLAB/Simulink to design the cage and predict field uniformity. I look forward to moving from modelling into physical design, construction, and testing as the project progresses.

## Skills & Tools
- **Programming Languages:** C, Python, MATLAB
- **Embedded Systems:** TMS570 Microcontroller, FreeRTOS, I2C
- **Other Tools:** Git, GitLab, Simulink, Linux (WSL)






