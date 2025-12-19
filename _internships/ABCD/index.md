---
layout: post
title: >-
  Internship 2025 | 2-Cylinder VIVACE Converter | OpenFOAM URANS (S-A) CFD + ANSYS Transient Structural Fatigue | Vortex Hydro Energy, Michigan, USA
description: >-
  Simulated flow-induced oscillations of a 2-cylinder VIVACE converter using OpenFOAM (URANS + Spalart–Allmaras) with
  force/time-history post-processing (lift/drag, displacement) and transferred hydrodynamic loads into ANSYS Transient
  Structural for time-domain stress and stress-life fatigue assessment.
skills:
  - OpenFOAM (URANS) & Turbulence Modeling (Spalart–Allmaras)
  - Flow-Induced Oscillations (VIV / Galloping) Modeling
  - Hydrodynamic Load Extraction (Lift/Drag)
  - ANSYS Transient Structural (Newmark) & Fatigue (Stress-Life)
  - CAD/FEA Workflow Integration
main-image: /assets/images/internships/iitk_vivace_2cyl/main.png
images:
  - /assets/images/internships/iitk_vivace_2cyl/domain_mesh.png
  - /assets/images/internships/iitk_vivace_2cyl/lift_drag.png
  - /assets/images/internships/iitk_vivace_2cyl/displacement.png
  - /assets/images/internships/iitk_vivace_2cyl/vonmises.png
  - /assets/images/internships/iitk_vivace_2cyl/fatigue_life.png
---

## Overview

### Animation 1 — OpenFOAM wake visualization (baseline)
<video controls autoplay loop muted playsinline style="max-width:100%; height:auto; border-radius:12px;">
  <source src="{{ '/assets/videos/internships/ABCD/vortex_shedding.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Animation 2 — OpenFOAM wake visualization (k=600 case)
<video controls autoplay loop muted playsinline style="max-width:100%; height:auto; border-radius:12px;">
  <source src="{{ '/assets/videos/internships/ABCD/k%20600%20,%20v%200.2.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>


### Key technical contributions
- Executed **URANS CFD simulations in OpenFOAM** to resolve unsteady separation, wake dynamics, and vortex shedding relevant to **flow-induced oscillations (FIO)** of a **2-cylinder VIVACE** configuration.
- Modeled **2 rigid cylinders in tandem** with **single-DOF transverse oscillation**, capturing coupled fluid forcing (lift/drag) and structural response (displacement/velocity) in time.
- Completed a parametric study at **flow speed U = 2 m/s** with:
  - **Damping ratio ζ = 0.22, 0.24, 0.26, 0.28**
  - **Spring stiffness k = 200, 400, 600, 800**
- Extracted **time histories of lift and drag** and prepared load inputs suitable for downstream structural dynamics and fatigue evaluation.
- Mapped the CFD-derived hydrodynamic loads into **ANSYS Transient Structural** to compute **time-domain Von-Mises stress** and perform **stress-life fatigue** assessment under cyclic loading.

---

## OpenFOAM CFD Model (URANS + Spalart–Allmaras)

### Governing equations + turbulence closure
- Solved the **incompressible URANS** equations using a **finite-volume discretization** with the **Spalart–Allmaras (S-A)** one-equation turbulence model to represent turbulent eddy viscosity for separated cylinder wakes.
- Used a segregated pressure–velocity solution strategy (PISO-type workflow) with **second-order spatial discretization** and **second-order temporal integration** to preserve vortex shedding physics and force phase fidelity.

### Fluid–structure coupling (single-DOF oscillator)
- Represented each cylinder as a **mass–spring–damper oscillator** constrained to **transverse (cross-flow) motion**, with the **instantaneous fluid force** providing the excitation term.
- Tracked response metrics used for FIO characterization:
  - **y/D** (normalized displacement)
  - **ẏ** (transverse velocity)
  - **Lift/Drag time histories** and cycle-to-cycle force consistency after transient startup

### Mesh strategy + numerical credibility
- Used a **boundary-layer resolving mesh** around the cylinder(s) to maintain near-wall resolution consistent with S-A modeling needs.
- Referenced a **grid sensitivity approach** (coarse/medium/fine) to ensure force statistics and wake structures were not mesh-dependent before final runs.

---

## Hydrodynamic Force Extraction & Post-Processing

### Lift/drag computation
- Computed **lift (Fy)** and **drag (Fx)** from **pressure integration** over the cylinder surface(s) using ParaView/ParaFoam post-processing workflows.
- Generated force time-series suitable for:
  - identifying steady-state oscillatory regimes,
  - detecting lock-in / amplitude jumps,
  - exporting time-dependent loads into structural simulation.

---

## ANSYS Transient Structural + Fatigue (Load Transfer Workflow)

### Transient structural setup
- Applied external loading components representing:
  - **hydrodynamic lift/drag** (time-dependent, per cylinder),
  - **gravity**,
  - **hydrostatic pressure** (as applicable to the test depth / operating condition).
- Solved the time-domain structural response using a **Newmark-type integration** workflow to obtain stress histories consistent with cyclic FIO forcing.

### Stress + fatigue assessment
- Evaluated **Von-Mises stress** to identify stress concentration zones and peak dynamic stress intervals.
- Performed **stress-life (S–N) fatigue** using a **zero-based loading** interpretation to estimate durability under repeated oscillatory cycles driven by FIO forcing.
