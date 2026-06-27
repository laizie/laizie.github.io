---
layout: page
title: FluidSim2d
caption: Real-time 2D FLIP fluid simulation for a round LED pocket watch — in development
description: >
  A real-time FLIP (Fluid-Implicit-Particle) fluid simulation built to run on a 2-inch round
  LED pocket watch. Prototyped in the browser with JavaScript, with physics designed to port
  cleanly to C++ on an ESP32 driving a circular addressable-LED matrix.
date: 2026-06-20
image:
  path: /assets/img/logo.png
  alt: FluidSim2d
links:
  - title: GitHub
    url: https://github.com/laizie/FluidSim2d
---

**Jun 2026 – Present &nbsp;·&nbsp; WIP**

FluidSim2d is a real-time **FLIP fluid simulation** I'm building to run on a 2-inch round LED pocket watch. The water sloshes around the circular display based on how the watch is tilted. I'm prototyping the physics in the browser first, then porting it to C++ to run on an ESP32-C3 Super Mini driving a circular addressable-LED matrix.

The idea comes from [mitxela's fluid pendant](https://mitxela.com/projects/fluid-pendant).

## How it works

It's a [FLIP](https://en.wikipedia.org/wiki/Fluid_implicit_particle) (Fluid-Implicit-Particle) solver:

- **P2G / G2P** - splat particle velocities onto a grid and read them back with the FLIP/PIC blend
- **Forces** - gravity follows the direction the watch is tilted
- **Advection** - move the particles and bounce them off the circular wall
- **Push-apart + cohesion** - keep particles from overlapping, and let droplets ball up and break off for a surface-tension feel

## Tech

- **JavaScript** - the solver and rendering harness, running live in the browser for fast iteration
- **HTML5 Canvas** - visualizing the simulation at real pocket-watch size
- **C++** - porting the physics to run on-device (in progress)
- **ESP32** - target microcontroller (hardware FPU, dual-core)
- **KiCad** - custom round PCB for the addressable-LED matrix

## Status

Actively in development. The browser prototype handles gravity, FLIP transfers, incompressibility, cohesion, and tilt-driven gravity. The C++ has been completed, now I am waiting on parts to arrive and to get it on an actual screen prototype.
