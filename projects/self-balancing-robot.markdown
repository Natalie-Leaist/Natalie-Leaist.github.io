---
layout: single
title: Self Balancing Robot
permalink: /docs/projects/self-balancing-robot/
sidebar:
  nav: "docs"
classes: wide
---

I designed and built a self-balancing robot to gain experience with control systems, sensors, and embedded programming. The robot has two wheels, and balances similar to a segway. The system was built with an Arduino, MPU6050 IMU, DRV8825 stepper motor drivers, and NEMA-17 stepper motors, all powererd by a LiPo battery. 

The MPU6050 IMU provided raw linear acceleration and angular velocity data over I2C to the Arduino. I implemented a complementary filter to combine these two signals into a stable estimate of the robot's pitch angle. This angle was then fed into a PID controller. The PID controller calculates the difference between measured tilt and the desired position, and then outputs the desired speed of the motor in steps per second. 

The most difficult and time-consuming part of the project was tuning the PID controller and getting the motors to respond the way I wanted. The torque of the motors drops off at higher speeds, so sometimes the robot couldn't catch itself. I eventually learned to call the motor control function as often as possible, even during sensor reads, and to insert small delays when switching direction to keep things stable. After many trials and adjustments, the robot was able to balance.

In the future, I would like to expand the project by adding a remote control, allowing me to adjust the robot’s speed and motion while it balances.

## Skills
- C++ programming on Arduino UNO
- PID control implementation and tuning
- Sensor data processing (accelerometer + gyroscope, complementary filter)
- Stepper motor control using DRV8825 drivers, NEMA-17 stepper motors, and AccelStepper library

