---
layout: page
title: Day Counter Picture Frame
caption: Custom Arduino device that counts elapsed days — built and housed in a 3D-printed enclosure
description: >
  A custom-built picture frame that tracks and displays the number of days elapsed since
  a start date. Features a 3D-printed enclosure, dual seven-segment displays, real-time clock
  module, and persistent memory so it never loses count.
date: 2025-11-01
image:
  path: /assets/img/logo.png
  alt: Day Counter Picture Frame
links:
  - title: GitHub
    url: https://github.com/laizie/Digital-Day-Counter-Picture-Frame
---

**Nov 2025 – Feb 2026**

A hardware + software project combining embedded programming, real-time clocking, and physical design. I designed the enclosure from scratch in Onshape, 3D-printed it, and programmed the Arduino to reliably track days across power cycles.

## Hardware

- **Arduino Nano** — microcontroller brain
- **Dual 4-digit seven-segment displays** — shows the day count
- **DS3231 Real-Time Clock module** — keeps accurate time even when powered off
- **Custom 3D-printed enclosure** — designed in Onshape to fit all components cleanly

## Software

- **Arduino IDE / C++** — firmware for the Nano
- Programmed the RTC to trigger daily updates at midnight
- Implemented EEPROM data persistence so the count survives power loss and resumes immediately on boot

## What I learned

This was my first embedded hardware project from end to end, designing the physical housing, wiring components, and writing firmware that had to be reliable 24/7. Getting the persistence logic right (so it didn't reset on power loss) required carefully understanding the RTC and EEPROM together.
