---
layout: post
title: Internship 2024 | CFD Analysis of Thermal Stratification and HVAC Systems | Indian Institute of Technology, Bombay
description:
 Developed and validated 3D steady, incompressible turbulent RANS CFD models to characterize jet-driven mixing, buoyancy-driven stratification, and ventilation effectiveness in enclosed spaces, with HVAC-oriented post-processing (temperature gradients, velocity fields, residence time).

Implemented an Impinging Jet Ventilation (IJV) benchmark: created a full-scale office-room geometry in ANSYS SpaceClaim (room: 4.5 × 9 × 3.9 m; dual square inlets: 0.3 × 0.3 m positioned 0.3 m above floor; ceiling outlet: 0.3 × 0.3 m) and included internal heat-source blocks representing occupants/equipment to capture realistic buoyancy effects.

Solved coupled continuity + Navier–Stokes + energy equations with buoyancy using the Boussinesq approximation (reference temperature ~26 °C), applying RNG k–ε turbulence with standard wall functions, SIMPLE pressure–velocity coupling, and second-order upwind spatial discretization to preserve jet momentum and thermal plume behavior.

Enforced near-wall modeling fidelity via y⁺ targeting (~90–180) and a mesh strategy suitable for indoor jet flows (tetrahedral core + localized refinement near inlets/outlets/walls/heat sources; controlled growth rate / expansion ratio) to reduce numerical diffusion in high-gradient regions.

Quantified thermal stratification using ΔTₐ(z) (vertical temperature difference referenced to a near-floor plane) and validated flow physics by comparing velocity contour planes and jet development characteristics (attachment, entrainment, decay) against benchmark trends.

Wall-Mounted Split AC Jet Optimization (Vane-Angle / Throw / Mixing)

Modeled a wall-mounted split AC discharge to study how vane angle governs jet trajectory, throw length, recirculation zones, and mixing effectiveness in the occupied zone.

Built parametric geometry in SpaceClaim and simulated flow/thermal fields in Fluent, extracting XZ-plane velocity contours, jet centerline decay, and velocity profiles to quantify distribution uniformity and infer implications on comfort and energy performance.

Used a benchmark-aligned turbulence/wall-treatment setup (e.g., Realizable k–ε + enhanced wall treatment where appropriate) and compared plane-wise velocity components to reference trends to ensure predictive accuracy.

Fan-Driven Mixing + Air Residence Time + Grid Independence

Simulated fan-induced recirculation in an enclosed space and performed a grid independence study across multiple mesh densities (e.g., ~0.45M / 0.86M / 2.4M cells), demonstrating convergence of velocity profiles and contour features (recirculation strength, dead-zone persistence).

Computed Air Residence Time (ART) fields to locate stagnation regions and evaluate ventilation effectiveness; interpreted ART relative to the ACH timescale (ART ≈ ACH timescale → well-mixed, ART ≫ ACH timescale → trapped/recirculating zones).

Linked CFD findings to reduced-order IAQ assumptions via the well-mixed/CSTR framework and a mixing factor (K) concept, using CFD to quantify deviations from ideal mixing in practical indoor airflow scenarios.
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
---

