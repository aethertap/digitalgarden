---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/physics/arduino-photogate/","tags":["gardenEntry"]}
---


# Photogate speed measurement project

Goals:
- Design a mechanical structure for holding electronic components
- Define parameters for velocity measurement
- build phototransistor beam-break circuit, one-shot with manual reset (or delay by configurable time)

Simplest setup: 
- One bright LED
- One phototransistor
- Deep light-tube on both
- LED always on
- arduino samples resistance on phototransistor. 10k resistor, transistor in voltage divider configuration with pin at measurement point.