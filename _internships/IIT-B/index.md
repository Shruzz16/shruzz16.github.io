---
layout: post
title: "Internship 2024 | CFD Analysis of Thermal Stratification and HVAC Systems | Indian Institute of Technology, Bombay"
description: |-
  Key technical contributions:
  - Developed and validated 3D steady, incompressible turbulent RANS CFD models to characterize jet-driven mixing, buoyancy-driven stratification, and ventilation effectiveness in enclosed spaces using HVAC-oriented post-processing (temperature gradients, velocity fields, air residence time).
  - Implemented an Impinging Jet Ventilation (IJV) benchmark by creating a full-scale office-room geometry in ANSYS SpaceClaim (4.5 × 9 × 3.9 m; dual 0.3 × 0.3 m inlets at 0.3 m above floor; 0.3 × 0.3 m ceiling outlet) and adding internal heat-source blocks representing occupants/equipment to capture buoyancy effects.
  - Solved coupled continuity + Navier–Stokes + energy equations with buoyancy using the Boussinesq approximation (Tref ≈ 26 °C), applying RNG k–ε turbulence with standard wall functions, SIMPLE pressure–velocity coupling, and second-order upwind discretization to preserve jet momentum and thermal plume behavior.
  - Ensured near-wall fidelity via y⁺ targeting (~90–180) and a refined tetrahedral mesh strategy (local refinement near inlets/outlets/walls/heat sources; controlled growth rate) to reduce numerical diffusion in high-gradient regions.
  - Quantified stratification using ΔTₐ(z) (vertical temperature difference referenced to a near-floor plane) and validated flow physics via velocity contour comparisons and jet development metrics (attachment, entrainment, decay).

  Wall-mounted split AC jet optimization:
  - Modeled a wall-mounted split AC discharge to study vane-angle impacts on jet trajectory, throw length, recirculation zones, and occupied-zone mixing effectiveness.
  - Built parametric geometry in SpaceClaim and simulated flow/thermal fields in Fluent, extracting XZ-plane velocity contours, jet centerline decay, and velocity profiles to quantify distribution uniformity and infer comfort/energy implications.
  - Used a benchmark-aligned turbulence/wall-treatment setup (e.g., Realizable k–ε with enhanced wall treatment where appropriate) and compared plane-wise velocity components against reference trends for predictive accuracy.

  Fan-driven mixing + air residence time + grid independence:
  - Simulated fan-induced recirculation in an enclosed space and completed a grid-independence study across multiple mesh densities (~0.45M / 0.86M / 2.4M cells), demonstrating convergence of velocity profiles and contour features (recirculation strength, dead-zone persistence).
  - Computed Air Residence Time (ART) fields to locate stagnation regions and evaluate ventilation effectiveness; interpreted ART relative to the ACH timescale (ART ≈ ACH timescale → well-mixed, ART ≫ ACH timescale → trapped/recirculating zones).
  - Linked CFD findings to reduced-order IAQ assumptions via the well-mixed/CSTR framework and a mixing factor (K) concept, using CFD to quantify deviations from ideal mixing in practical indoor airflow scenarios.
skills:
  - "CFD & Thermal Systems Analysis"
  - "HVAC System Design & Simulation"
  - "ANSYS Fluent & SpaceClaim"
  - "Turbulence Modeling & Validation"
  - "Energy Efficiency Optimization"
main-image: "/Velocity contour_roon.png"
images:
  - "/ART_room.png"
  - "/Room_view.png"
  - "/Velocity Contour.png"
  - "/Velocity contour_roon.png"
  - "/grid_independency.png"
---
