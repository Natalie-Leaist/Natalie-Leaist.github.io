---
layout: single
title: Small Projects
permalink: /docs/projects/small-projects/
sidebar:
  nav: "docs"
classes: wide

gallery:
  - url: /images/misc_images/holder.jpg
    image_path: /images/misc_images/holder.jpg
  - url: /images/misc_images/collapsed_holder.jpg
    image_path: /images/misc_images/collapsed_holder.jpg

author_profile: true
---

## Simon Game

{% include figure image_path="/images/misc_images/simon_game.jpg" %}

As a final project for my Introduction to C Programming Course (APSC 160), I was tasked with making a replication of The Simon Game using Arduino. Here’s how the Simon Game works:
- The game device has four coloured buttons: red, green, blue, yellow
- At the start, the game plays a single tone while lighting up one button
- The player must then press that same button
- On the next round, the game repeats the first light and sound, then adds a new one to the sequence
- The player now has to press both buttons in the right order
- Each round, the sequence is lengthened by one step
- If the player successfully repeats a sequence of length five, then they win!

The code handles the full game loop, including sequence generation, LED flashing, button input detection, and sequence comparison.

You can view the project on TinkerCad [here.](https://www.tinkercad.com/things/jeuRpwNNCBP-simongame?sharecode=AK7lE3eDWVR4nnuOETv-xQTbmmfy_daz_ArlXevUN18)

Link to the code on github [here.](https://github.com/Natalie-Leaist/small-arduino-projects/blob/main/simon_game.ino)

## Semi-Autonomous Claw

{% include figure image_path="/images/misc_images/claw.jpg" %}

As a project in my Introduction to Engineering Course (APSC 100), we were tasked with working in groups of 4 to create a semi-autonoumous robotic claw to locate, grasp and transport small objects. I worked on both the software and mechanical design. On the software side, I programmed the arduino to sense the ground (using an ultrasonic sensor) and open/close the claw by controlling a servo motor. 

On the mechanical side, I helped design and build the claw mechanism. We focused on maximizing the grip strength by ensuring that most of the force from the servo motor was translated into clamping. For the materials, we were limited to using essentially sheet metal, elastic bands, tape and glue. For the sheet metal, we were also constrained to cutting and bending it using hand tools. 

Overall, working on this project taught me skills in rapid prototyping, testing, and iteration in a team environment. 

Link to the code on github [here.](https://github.com/Natalie-Leaist/small-arduino-projects/blob/main/APSC100_claw.ino)

## Machined Cell Phone Holder

In the UBC PHAS Machine Shop training course, I gained hands on experience with manual machining techniques including milling, using a lathe, drilling, tapping, finishing, and measuring. In addition, I also learned to use a waterjet cutter. As a project for the course, I created a collapsible cell phone holder from stock brass and aluminum. 

{% include gallery %}



