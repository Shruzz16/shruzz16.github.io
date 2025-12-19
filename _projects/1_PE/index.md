---
layout: post
title: >-
  EECS 418 Final Project 2025 | Current-Mode Buck LED Driver (Stop/Start Voltage Stabilizer Concept) | University of Michigan
description: >-
  Designed, built, and tested a 200 kHz+ current-mode buck LED driver (24–32 V input, 1 A constant-current output) with a
  comparator-based PWM stage, current-sense feedback, and PCB implementation. Verified operation using bench instrumentation
  (DMM, oscilloscope, bench supply), with soldering/rework and testpoint-driven bring-up.
skills:
  - Power Electronics (Buck Converter)
  - Current-Mode Control (Average Current)
  - PCB Design (Altium)
  - Hardware Bring-up & Debug (DMM/Oscilloscope)
  - Inductor Winding & Magnetics
main-image: /01.jpeg
images:
  - /01.jpeg
  - /02.jpeg
  - /03.jpeg
  - /04.jpeg
  - 
---

## Overview
Built a **DC–DC buck-based “voltage stabilizer module” style LED current driver** motivated by vehicle stop/start warm-crank voltage dip behavior. Target specs included **24–32 V input**, **1 A regulated LED current**, **fsw ≥ 200 kHz**, and ripple-driven design constraints on inductor/output filtering.

---

## System architecture (hardware implementation)
- Implemented an **average-current regulation loop**: **0.1 Ω current-sense resistor → LM358 error amplifier (non-inverting) → PWM comparator with hysteresis → high-side gate driver** controlling the buck switch.
- Power stage integration: **switch + diode + inductor + output capacitor** feeding a high-power LED load; designed to operate in **CCM** under nominal operating conditions.

---

## Power stage sizing + component realization
- Selected **L and C** to control ripple and enforce stable current regulation (inductor ripple and output ripple verified against switching-frequency operation).
- Built/validated magnetics as a practical deliverable (inductor winding + integration into the PCB test workflow).

---

## PCB build, soldering, and bring-up workflow
- Produced schematic + PCB layout in **Altium**, including **conservative power trace sizing**, **grounding strategy**, and **dedicated test pads** to enable repeatable measurements and debugging.
- Assembled the board via **through-hole soldering**, plus iterative rework/repair practices typical for power electronics prototypes (component swaps, re-soldering, shorts/continuity checks).

---

## Measurement & validation (bench instrumentation)
Used standard lab instrumentation to validate function at the block and system level:
- **Bench DC supply** for controlled input sweeps and safe bring-up (current-limited startup).
- **Digital multimeter (DMM)** for continuity checks, node DC verification (reference, sense voltages), and quick fault isolation.
- **Oscilloscope** for switching-domain verification and waveform capture:
  - **Vout ripple** (at representative input voltages),
  - **Inductor current waveform** (ripple shape / CCM behavior),
  - **LED current waveform** and transient behavior,
  - Step/perturbation observations for practical stability confirmation.

---

## Results (what to show on the page)
- Include **schematic**, **PCB layout**, and **measured scope captures** (Vout ripple / IL / ILED), plus an efficiency trend plot.
