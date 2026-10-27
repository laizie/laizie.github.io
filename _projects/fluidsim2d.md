---
layout: page
title: FluidSim2d
caption: Real-time 2D FLIP fluid simulation for a round pocket watch — in development
description: >
  A real-time FLIP (Fluid-Implicit-Particle) fluid simulation built to run on a 2-inch round
  pocket watch. Prototyped in the browser with JavaScript, with the physics being ported to
  C++ on a Waveshare RA4M1-Zero driving a round display on a custom PCB.
date: 2026-06-20
image:
  path: /assets/img/logo.png
  alt: FluidSim2d
links:
  - title: GitHub
    url: https://github.com/laizie/FluidSim2d
---

**Jun 2026 – Present &nbsp;·&nbsp; WIP**

<p style="text-align:center;">
  <img src="/assets/img/projects/fluidsim2d.gif" alt="FluidSim2d sloshing around the round display"
       style="width:480px;max-width:100%;height:auto;border-radius:10px;
              border:1px solid #d0d5dd;box-shadow:0 8px 24px rgba(0,0,0,.14);" />
</p>

FluidSim2d is a real-time **FLIP fluid simulation** I'm building to run on a 2-inch round pocket watch. The water sloshes around the circular display based on how the watch is tilted. I'm prototyping the physics in the browser first, then porting it to C++ to run on a Waveshare RA4M1-Zero Mini driving a round display on a custom PCB.

The idea comes from [mitxela's fluid pendant](https://mitxela.com/projects/fluid-pendant).

## How it works

It's a [FLIP](https://en.wikipedia.org/wiki/Fluid_implicit_particle) (Fluid-Implicit-Particle) solver:

- **Forces + advection** - gravity follows the direction the watch is tilted; particles move and bounce off the circular wall
- **Push-apart** - a light pass so particles don't stack on top of each other
- **P2G** - splat particle velocities onto a staggered grid and mark each cell as fluid, air, or wall
- **Pressure solve** - adjust the grid until every fluid cell has as much flow out as in, so the water can't be squashed. This is what makes it slosh and curl up the walls instead of piling up like sand
- **G2P** - read velocities back to the particles with the FLIP/PIC blend

A neighbour grid keeps the particle-pair checks cheap, and each frame runs in substeps so hard tilts stay stable.

## Tech

- **JavaScript** - the solver and rendering harness, running live in the browser for fast iteration
- **HTML5 Canvas** - visualizing the simulation at real pocket-watch size
- **C++** - porting the physics to run on-device (in progress)
- **Waveshare RA4M1-Zero Mini** - target microcontroller (Renesas RA4M1: 48 MHz Arm Cortex-M4 with FPU, 32 KB RAM)
- **MPU6050** - accelerometer whose gravity vector drives the simulation
- **KiCad** - custom round PCB

## Status

Actively in development. The browser solver now has a full pressure solve, so the water sloshes and levels like a liquid instead of sliding as a lump. An earlier version of the solver is already ported to C++; next is porting the new one to the RA4M1, where 32 KB of RAM keeps the grid around 16×16. The custom PCB is designed in KiCad, and I'm waiting on the parts to arrive to build it.
