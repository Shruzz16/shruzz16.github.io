---
layout: post
title: >-
  Internship 2024 | CFD Analysis of Thermal Stratification and HVAC Systems | Indian Institute of Technology, Bombay
description: >-
  CFD internship: validated buoyant indoor jet ventilation and HVAC air-distribution models in ANSYS Fluent/SpaceClaim;
  quantified stratification, mixing, and air residence time with mesh-independence verification.
skills:
  - CFD & Thermal Systems Analysis
  - HVAC System Design & Simulation
  - ANSYS Fluent & SpaceClaim
  - Turbulence Modeling & Validation
  - Energy Efficiency Optimization
main-image: /Velocity contour_roon.png
images:
  - /ART_room.png
  - /Room_view.png
  - /Velocity Contour.png
  - /Velocity contour_roon.png
  - /grid_independency.png
  - /AC.png
  - /AC_room.png
---

## Overview

### Key technical contributions
- Developed and validated **3D steady, incompressible turbulent RANS** CFD models to characterize **jet-driven mixing**, **buoyancy-driven stratification**, and **ventilation effectiveness** using HVAC post-processing (**temperature gradients, velocity fields, air residence time**).
- Implemented an **Impinging Jet Ventilation (IJV)** benchmark in **ANSYS SpaceClaim**: office-room geometry **4.5 × 9 × 3.9 m**; dual **0.3 × 0.3 m** inlets at **0.3 m** above floor; ceiling outlet **0.3 × 0.3 m**; included internal heat-source blocks (occupants/equipment) to capture buoyancy.
- Solved coupled **continuity + Navier–Stokes + energy** with buoyancy using **Boussinesq** (Tref ≈ **26 °C**), **RNG k–ε** + standard wall functions, **SIMPLE** pressure–velocity coupling, and **2nd-order upwind** discretization.
- Ensured near-wall fidelity via **y⁺ targeting (~90–180)** and a refined tetrahedral mesh strategy (local refinement near **inlets/outlets/walls/heat sources**; controlled growth rate) to reduce numerical diffusion.
- Quantified stratification via **ΔTₐ(z)** and validated flow physics using **velocity contour comparisons** and jet development metrics (**attachment, entrainment, decay**).

### Wall-mounted split AC jet optimization (vane angle / throw / mixing)
- Modeled a wall-mounted split AC discharge to study vane-angle impacts on **jet trajectory**, **throw length**, **recirculation zones**, and **occupied-zone mixing**.
- Built parametric geometry in **SpaceClaim** and simulated flow/thermal fields in **Fluent**, extracting **XZ-plane velocity contours**, **jet centerline decay**, and **velocity profiles** to quantify distribution uniformity and infer comfort/energy implications.
- Used a benchmark-aligned turbulence/wall-treatment setup (e.g., **Realizable k–ε** with enhanced wall treatment where appropriate) and compared plane-wise velocity components against reference trends.

### Fan-driven mixing + air residence time + grid independence
- Simulated fan-induced recirculation and performed a **grid-independence study** (~**0.45M / 0.86M / 2.4M** cells), demonstrating convergence of velocity profiles and contour features (**recirculation strength**, **dead-zone persistence**).
- Computed **Air Residence Time (ART)** fields to locate stagnation regions and evaluate ventilation effectiveness; interpreted ART relative to **ACH** timescale (ART ≈ ACH → well-mixed; ART ≫ ACH → trapped/recirculating).
- Linked CFD results to reduced-order IAQ assumptions via the **well-mixed/CSTR** framework and a **mixing factor (K)** concept to quantify deviations from ideal mixing.
