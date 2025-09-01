---
layout: single
title: CGEM Accelerometer System
permalink: /docs/projects/cgem-accelerometer-system/
sidebar:
  nav: "docs"
classes: wide
author_profile: true
---

{% include figure image_path="/images/cgem_images/accelerometer_system.jpg" %}

## About CGEM
During summer 2025 I worked as a research intern in UBC's Experimental Cosmology Group, led by Dr. Mark Halpern and Dr. Gary Hinshaw. I worked on the Canadian Galactic Emmision Mapper (CGEM), which is a telescope that will be used to help detect gravitational waves from the early universe. CGEM is a collaboration with UBC, NASA Goddard, and DRAO. The telescope is located at the DRAO in Penticton, BC.

## The Accelerometer System
To monitor and characterize mechanical vibrations in the telescope structure, as well as measure the inclination of the telescope dish, the experiment will use high-precision accelerometers mounted directly on the telescope. 

My project was to develop the embedded system that reads these accelerometers at a high frequency (currently approximately 830 times per second). At the core of the system is an AD7177-2 24-bit analog-to-digital converter (ADC) connected to ADXL354 accelerometer sensors. The ADC continuously streams digitized acceleration measurements to an STM32 microcontroller, which timestamps and packages the data before transmitting it over Ethernet to a host computer.

Beyond this accelerometer application, the system I developed is a versatile data acquisition system. It will likely be adapted for other applications in CGEM, such as temperature sensing.

[Link to the github repo.](https://github.com/cgem-experiment/Accelerometers)

## My Contributions
- Designed and implemented firmware on an STM32 microcontroller to interface with an analog digital converter (AD7177-2) over SPI
- Configured the ADC for multi-channel continuous conversion and integrated DMA for efficient data transfer
- Used FreeRTOS and interrupts to schedule acquisition, timestamping, and Ethernet transmission tasks
- Implemented UDP networking via LwIP to send data to a host computer at ~830 Hz per channel
- Performed FFTs on collected data to verify sensor performance and identify aliasing/grounding issues
- Developed calibration methods for offset and gain calibration of measured values
- Documented the system in detail with LaTeX reports and schematics

## Skills & Tools
- **Programming Languages:** C, Python
- **Embedded Systems:** STM32, STM32CubeIDE, analog digital converters (AD7177-2), sensors (ADXL354 accelerometer), FreeRTOS, debugging
- **Data Analysis and Signal Processing:** Jupyter notebooks, numpy, matplotlib, sensor calibration, noise characterization
- **Electrical:** oscilloscope, multimeter, function generator, soldering
- **Networking:** UDP, LwIP (Ethernet stack)
- **Other Tools:** Git, Github, LaTeX, Linux

{% include figure image_path="/images/cgem_images/accel_schematic.png"
   alt="Accelerometer System Diagram"
   caption="Block diagram of the CGEM accelerometer data acquisition system" %}



