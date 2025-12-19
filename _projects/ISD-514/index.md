---
layout: post
title: >-
  Driver Safety Optimization for an Obese Female Occupant in Toyota RAV4 | GHBMC + LS-DYNA DOE (Taguchi L21) | University of Michigan
description: >-
  Optimized restraint-system and vehicle interior safety parameters for a demographically vulnerable obese female driver
  (GHBMC, frontal crash) using LS-DYNA simulations and a Taguchi L21 DOE. Debugged baseline solver instability, computed
  injury metrics (HIC15, chest deflection, femur forces, neck loads) and minimized the combined P-Joint injury metric.
skills:
  - LS-DYNA Crash Simulation
  - Human Body Modeling (GHBMC)
  - Restraint System Tuning (Belt / Airbag / Steering Column)
  - Design of Experiments (Taguchi L21)
  - Injury Metrics & P-Joint Optimization
main-image: /ISD-514.png
images:
  - /1.jpeg
  - /2.jpeg
  - /3.jpeg
  - /4.jpeg
---

## Overview
Performed a crash-safety design study for a **Toyota RAV4 driver occupant** using the **GHBMC human body model** representing an **obese female (age 60, height 151.4 cm, BMI 41.5)** under **frontal crash** conditions. The objective was to **reduce overall injury risk** by minimizing **P-Joint**, computed from key injury metrics (HIC15, chest deflection, femur forces, neck tension/compression).

---

## Baseline setup + numerical debugging
- Established a baseline driver setup and extracted baseline injury metrics (e.g., **HIC15**, **chest deflection**, **left/right femur forces**, **neck loads**, **P-Joint**).
- Resolved early simulation failures driven by:
  - **belt–dummy intersection** leading to instability/termination,
  - **excessive nodal deformation** (notably abdominal region).
- Improved numerical stability by **reducing the timestep**, enabling the simulation to complete and produce consistent kinematics and injury outputs.

---

## DOE optimization (Taguchi L21)
- Executed a **Taguchi L21 orthogonal array DOE** to identify the most influential restraint/vehicle parameters and systematically reduce P-Joint.
- Varied key parameters across levels (example categories):
  - **seatbelt load limiters** (BELTLL1, BELTLL2),
  - **steering column force/stroke characteristics** (e.g., STWCOMP / STWSTRK),
  - **airbag-related tuning** (e.g., KABI, DABTL), and later **DABVD** during refinement.
- After screening **21 runs**, selected **10 promising configurations** (lowest P-Joint region), introduced **DABVD**, and re-ran additional simulations.
- For failed configurations, applied controlled parameter edits and re-ran as “(A)” cases to recover stable results.

---

## Injury metrics + P-Joint evaluation
- Computed outputs from LS-DYNA post-processing for each run:
  - **HIC15** from head acceleration history,
  - **chest deflection** from sternum–T8 relative motion at peak compression,
  - **left/right femur forces** from element outputs,
  - **upper neck tension/compression**.
- Combined metrics into **P-Joint** to rank designs and select the optimum configuration.
- Applied **injury risk scaling** based on **U.S. NCAP injury risk curves**, reporting scaled comparisons (e.g., baseline vs optimized HIC/chest injury risk percentages).

---

## Results (baseline vs optimized)
- Baseline example metrics: **HIC15 ≈ 291.4**, **chest deflection ≈ 47.1 mm**, **P-Joint ≈ 0.266**.
- Best optimized design achieved **P-Joint ≈ 0.183** with improved injury metrics (e.g., **HIC15 ≈ 200.5**, **chest deflection ≈ 40.93 mm**), and reduced scaled injury-risk measures.
- Key physical interpretation from the best solutions:
  - Increasing **airbag vent diameter** reduced effective airbag stiffness → improved cushioning and **lower head/chest loading**.
  - Increasing **steering column stroke/space** improved occupant clearance → reduced head/chest injury measures and overall P-Joint.

---

## Outcome
Delivered a repeatable crash-optimization workflow:
1) stable baseline setup + debugging,  
2) **Taguchi DOE** for parameter sensitivity and fast screening,  
3) refinement iterations for failure recovery,  
4) selection of a best-case configuration achieving a **clear reduction in P-Joint** and improved injury metrics.
