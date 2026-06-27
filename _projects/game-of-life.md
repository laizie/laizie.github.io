---
layout: page
title: Conway's Game of Life
caption: Conway's Game of Life in Java — a learning project for Swing GUIs and OOP
description: >
  Conway's Game of Life implemented in Java with a Swing GUI. Built as a learning project
  to get hands-on with Java windowing and object-oriented design.
date: 2026-01-07
image:
  path: /assets/img/logo.png
  alt: Conway's Game of Life
links:
  - title: GitHub
    url: https://github.com/laizie/laizie-GameOfLife
---

**Jan 2026 &nbsp;·&nbsp; Completed**

This was one of my first personal projects, something that I did not think was too difficult but still allow me to learn new things in the java area. However, I was mistaken, this was actually quite a challenge as I had to fully learn Java Swing to even get started it felt like. But eventually, I figured it out and made it happen.

A Java implementation of [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), the classic cellular automaton where simple birth-and-death rules produce surprisingly complex patterns. I built it to get hands on with Java GUI and windows (Swing) and to practice structuring a program with object-oriented design.

## What it does

- Simulates Conway's Game of Life on a grid, evolving the cells generation by generation
- Renders the live grid in a Swing window and steps the simulation on a timer
- Keyboard controls for interacting with the simulation

## Tech

- **Java** — core language
- **Swing / AWT** — `JFrame`, `Timer`, and key handling for the windowed GUI
- **OOP** — split into `Game`, `Grid`, and `Controller` classes to keep state, rules, and input separate

## What I learned

This was a focused exercise in two things I wanted to get more comfortable with: building a real windowed GUI in Java with Swing, and structuring code cleanly with object-oriented design rather than cramming everything into one file. Splitting the simulation into a grid model, a game loop, and a controller made the rules easy to reason about and the input easy to extend.
