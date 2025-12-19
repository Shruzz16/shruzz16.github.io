---
layout: post
title: >-
Design & Analysis of a MEMS Electro-Thermal Micro-Actuator (Microgripper) | University of Michigan
description: >-
  Designed and analyzed a polysilicon electro-thermal microgripper based on a U-shaped hot/cold arm architecture. Built a
  defensible electro-thermal-mechanical workflow combining closed-form scaling laws (displacement, temperature, resistance,
  gripping force) with fully coupled COMSOL multiphysics simulations, and evaluated design modifications (cold-arm width,
  perforations, updated geometry) against displacement/temperature/response-time targets.
skills:
  - MEMS Electro-Thermal Actuators
  - Multiphysics Modeling (COMSOL)
  - Reduced-Order Analytical Modeling (Thermal/Structural/Electrical)
  - Microfabrication Process Planning (SOI / MUMPs-style flow)
  - Design Iteration & Validation
main-image: /assets/images/projects/mems_microgripper/main.png
images:
  - /Fab_steps.jpeg
  - /1-D thermal model image.jpeg
  - /1.5Thermal contour.png
  - /disp.png
  - /new_model_disp.jpeg
  - /tip_disp_2.jpeg
    
---


Designed and analyzed a **MEMS electro-thermal microactuator / microgripper** that generates **in-plane jaw motion** via
**differential Joule heating** in asymmetric polysilicon beams: a narrow **hot arm** (high resistance/current density) and a wider
**cold arm** (heat-sinking, higher stiffness). The goal was to connect first-principles models to measurable performance:
**tip displacement, maximum temperature, gripping force, electrical resistance, and time response**, then validate with
fully coupled multiphysics FEM.

---

## Device concept (hot/cold arm electro-thermal actuation)
- Architecture: **U-shaped hot/cold arm pair**, mechanically joined at the distal end and **anchored at the base** (three-anchor
  configuration used to drive controlled aperture change).
- Working principle: applied terminal voltage drives current through the arms → **Joule heating** concentrated in the hot arm →
  constrained differential thermal expansion → **lateral bending** and controllable jaw opening/closing.

---

## Fabrication plan (single-mask SOI/MUMPs-style flow)
- Proposed a **single-mask** structural definition with an SOI/MUMPs-like sequence:
  - Deposit sacrificial **SiO₂**
  - Deposit ~**2 µm polysilicon** structural layer (doped for conductivity)
  - Lithography + etch to define beams/pads
  - Timed HF release of sacrificial oxide to **free the arms** while keeping **pads anchored**
- Included a mask-level layout suitable for the hot/cold arm geometry and anchor pads.

---

## Reduced-order analytical modeling (electro-thermal-mechanical)
### Tip displacement scaling (voltage-driven)
- Derived a compact displacement relationship from:
  - hot-arm thermal elongation: ΔL ∝ α L ΔT
  - Joule heating: I²R, voltage-driven I = V / Rtot
  - frame compliance mapping mismatch expansion into lateral tip deflection
- Produced a quadratic displacement fit for the validated geometry (widened cold arm case):
  - **wt(V) ≈ 0.043 V² [µm]**
  - Example: **wt(7 V) ≈ 2.1 µm**

### Thermal modeling of hot arm (1D vs 1.5D fin model)
- **1D axial conduction model** (baseline estimate of Tmax)
- **1.5D fin-based model** including lateral convection along the beam perimeter (more realistic for MEMS-scale heat loss)
- At **7 V**:
  - 1D model: **Tmax ≈ 640 °C**
  - 1.5D model: **Tmax ≈ 762 °C**
  - FEM peak temperature reported ~**O(800 °C)**

### Electrical resistance model + validation
- Modeled arm resistances using R = ρe L / (tW) and series combination:
  - hot arm Rh and cold arm Rc → **Rtot ≈ 1.44 kΩ**
- Compared against a reported experimental range (~1.34–1.38 kΩ) with ~**5%** difference (reasonable under constant-ρ assumptions).

---

## COMSOL multiphysics simulation (fully coupled FEM)
- Built a fully coupled COMSOL workflow using:
  - **Electric Currents**
  - **Heat Transfer in Solids**
  - **Solid Mechanics**
  - Couplings: **Joule heating + thermal expansion**
- Extracted full-field outputs:
  - **tip displacement** (deformed shape / displacement distribution)
  - **temperature distribution** (peak and spatial profile along hot arm)
- Verified that the FEM trend matches the quadratic displacement behavior predicted analytically.

---

## Performance metrics derived from mechanics
### Gripping force estimate (flexure stiffness method)
- Modeled the compliant jaw/flexure using Euler–Bernoulli beam theory and inverted the deflection relation to map jaw displacement to gripping force:
  - F related to EI, geometry (L, a), and measured displacement d
- Used representative flexure parameters (e.g., L, a, w, t) to compute an expected micro-newton-scale gripping force range.

### Target object radius (aperture model)
- Linked jaw opening to displacement wt(V) and initial gap G0:
  - **G(V) = G0 + wt(V)**
  - **Rtarget = G(V)** for cylindrical objects

---

## Design modifications and sensitivity studies
### Cold-arm width increase
- Evaluated widened cold-arm configuration to tune stiffness/thermal balance while preserving actuation efficiency and stability.

### Perforations in the hot arm
- Quantified trade-offs using a simple gain model:
  - Reduced stiffness can increase displacement response
  - Increased exposed area / modified resistance can reduce temperature rise
- Reported trends:
  - Displacement gain factor **~1.4×** (perforated vs non-perforated)
  - Temperature rise reduced to **~0.72×** of baseline (same applied voltage)

### Time response (first-order thermal dynamics)
- Modeled displacement response as a first-order thermal system:
  - w(t;V) = wss(V) (1 − exp(−t/τ))
- Representative time constants:
  - non-perforated: **τ ~ 0.4 ms**
  - perforated: **τ ~ 0.3 ms**

---

## Outcome
Delivered a complete, repeatable MEMS actuator workflow:
1) derive reduced-order models for **displacement + temperature + resistance**,  
2) validate/extend via **fully coupled COMSOL**,  
3) tune performance with geometry edits (**cold-arm width, perforations, modified layout**) while monitoring **thermal limits, displacement, force, and dynamics**.
---

