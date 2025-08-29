---
layout: single
title: CGEM Accelerometer System
permalink: /projects/cgem-accelerometer-system/
---

## About CGEM
During summer 2025 I worked as a research intern in UBC's Experimental Cosmology Group, lead by Dr. Mark Halpern and Dr. Gary Hinshaw. I worked on the Canadian Galactic Emmision Mapper (CGEM), which is a telescope that will be used to help detect gravitational waves from the early universe. CGEM is a collaboration with UBC, NASA Goddard, and DRAO. The telescope is located at the DRAO in Penticton, BC.

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
- **Electrical:** oscilloscope, multimeter, soldering
- **Networking:** UDP, LwIP (Ethernet stack)
- **Other Tools:** Git, Github, LaTeX, Linux

{% include figure image_path="/images/accel_schematic.png"
   alt="Accelerometer System Diagram"
   caption="Block diagram of the CGEM accelerometer data acquisition system" %}



