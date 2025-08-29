---
layout: single
title: Small Projects
permalink: /docs/projects/small-projects/
sidebar:
  nav: "docs"

classes: wide
---

## Simon Game
{% include figure image_path="/images/misc_images/simon_game.jpg" %}

As a final project for my introduction to C programming course (APSC 160), I was tasked with making a replication of The Simon Game using Arduino. Here's how the Simon Game works:
- The game device has four coloured buttons: red, green, blue, yellow
- At the start, the game plays a single tone while lighting up one button
- The player must then press that same button
- On the next round, the game repeats the first light and sound, then adds a new one to the sequence
- The player now has to press both buttons in the right order
- Each round, the sequence is lengthened by one step
- If the player successfully repeats a sequence of length five, then they win!

The code handles the full game loop, including sequence generation, LED flashing, button input detection, and sequence comparison. A complementary set of helper functions manage pin setup, button-to-LED mapping, LED flashing, and input checking.

You can view the project on TinkerCad [here](https://www.tinkercad.com/things/jeuRpwNNCBP-simongame?sharecode=AK7lE3eDWVR4nnuOETv-xQTbmmfy_daz_ArlXevUN18).


## Semi-Autonomous Claw

## Machined Cell Phone Holder

