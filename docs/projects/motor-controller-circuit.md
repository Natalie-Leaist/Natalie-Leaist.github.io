---
layout: single
title: Motor Controller Circuit
permalink: /docs/projects/motor-controller-circuit/
sidebar:
  nav: "docs"
classes: wide
author_profile: true
mathjax: true
---

{% include figure image_path="/images/motor_controller_images/schematic.png" %}
{% include figure image_path="/images/motor_controller_images/breadboard.png" %}

In Fall 2025, I took ENPH 259, an electronics lab focused on hands-on circuit design and analysis. Throughout the term, we built a variety of circuits, including a servo motor controller, a DC-DC boost converter, and digital logic circuits. The course provided extensive practical experience with op-amps, transistors, diodes, filters, and logic gates. I learned a lot in this class, and I had a pretty great time. I am very grateful to the teaching team. 

For the final project of the course, I built a closed-loop servo motor controller that combines digital logic, analog signal processing, and feedback control. The schematic for this system was designed by the ENPH 259 teaching team. My role was to build, analyze, and troubleshoot the complete circuit, and to develop a detailed understanding of how each subsystem contributes to the overall feedback loop. In the future, I would like to redesign and implement a version of this controller on a PCB.

The motor controller contains several subcircuits:

**Latch + Delay + Reset Pulse Generator**

This subcircuit generates three important signals. The latch signal follows the signal from the 5Hz square wave. When the latch signal is high, it tells a flip-flop in another part of the circuit to save the number of counted rotations.

The delay is introduced by the resistor and capacitor between U1F and U1B. The capacitor (C2) cannot change voltage instantly, and instead must charge/discharge before allowing U1B to reach it's threshhold voltage. At every 5Hz rising edge, three things must happen: the current counter value must be stored, the counter value must be reset to 0, and counting must begin again from 0. If the system attempts to store the current counting value at the same time the counter value is reset to 0, this creates a race condition. By introducing a short delay (approximately 10 us), the counter value is reliably stored before a reset occurs. 

The reset signal provides a narrow pulse that resets the value of the counter to 0. It works because when the input switches, the voltage across C3 cannot instantly change, so the voltage on both plates jumps up, creating a spike/pulse. However, R5 proceeds to then pull the right side of the capacitor to ground, and thus a voltage develops across it, and the input of U1C is low. This means the output of U1E is also low. Since the C3 has a low capacitance (47 pF), the time of the pulse is very short (approximately 500 ns).

**Counter**

The counter is created by connecting two 4-bit counters to create an 8-bit counter (0-255). Clock pulses from the motor go into the clock signal of the first counter (U2A), meaning that each pulse increments the counter by 1. The reset pulse immediately resets the counter.

**D-Latch**

The D-Latch stores the counter value when it receives the rising edge of the latch signal, every 200ms. This occurs before the reset signal clears the counter. The D-latch stores this 8-bit number until it senses the rising edge of the next latch signal. 

**8-bit DAC**

The D-Latch outputs an 8-bit digital number to the DAC, which converts it to a proportional analog voltage from 0 - 5V. The DAC is a simple R-2R ladder. 

A unity gain buffer is used on the output of the DAC to isolate the DAC from the PI controller. The R-2R ladder has a finite output impedance, and if connected directly to the PI controller, the controller's input impedance could load the ladder, causing the DAC voltage to shift. An op-amp has very high input impedance (draws almost no current), and a very low output impedance. 

**Error Signal Amplifier**

The error-signal amplifier functions as a PI controller by comparing the DAC output to the potentiometer setpoint and driving the motor until the two match. The op-amp continuously forcing V+ to be equal to V-, so any difference between the measured speed (converted to a voltage by the DAC) and the desired speed immediately produces a correction at the output. The resistor between creates the proportional response, if the motor is running too fast or too slow, the voltage difference produces an immediate change in output in the correct direction. The capacitor provides the integral response by accumulating error over time; as long as the motor speed differs from the setpoint, the capacitor charges or discharges, causing the op-amp output to increase/decrease until the error is eliminated. Together, these two feedback paths ensure that the motor eventually settles at the correct speed, and can respond to changes in desired speed.

**Power Stage**

This stage takes the signal from the PI controller, and uses is as the base current to control a BJT. The collector/emitter current drives the motor. 

Since motors are inductive, they can create large voltage spikes when current is changed suddenly. The diode (D1) provides a path for current when the transistor turns off, preventing these large voltage spikes.

**Phototransistor PCB + Clock**

The motor has a disk with 10 holes that passes between an infrared LED and a phototransistor. Each time a hole allows light through, the phototransistor switches states, producing a voltage pulse. Since there are 10 holes, each full revolution generates 10 pulses, creating a clock signal proportional to motor speed. This clock signal is fed back into the beginning of the circuit, effectively closing the loop.






