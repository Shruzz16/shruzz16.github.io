---
layout: post
title: >-
  Graduate Student Researcher | MEMS Scanning Mirror Co-Design & Nonlinear Electrostatic Modeling | Vibration & Acoustics Laboratory: Microsystems | University of Michigan
description: >-
  Ongoing MEMS research on resonant scanning mirrors: COMSOL modal + electrostatic analysis validated via DAQ-based experimental
  modal testing. Building a co-design pipeline spanning MEMS CAD (AutoCAD/SOLIDWORKS) and Altium PCB layout for robust
  electromechanical integration. Current focus: nonlinear electrostatic actuation modeling of comb-drive fingers with
  geometry-aware capacitance extraction and deforming-domain coupling.
skills:
  - COMSOL Multiphysics (Modal, Electrostatics, Deformed Mesh/ALE, Electromechanics)
  - MEMS Scanning Mirrors (Resonant Structures)
  - Experimental Modal Testing (DAQ, Excitation, Multi-sensor FRFs)
  - CAD Co-Design (AutoCAD / SOLIDWORKS) + PCB (Altium)
  - Capacitance / Field Extraction (Terminal, Capacitance Matrix)
main-image: /EigenF.jpeg
images:
  - /EigenF.jpeg
  - /1.png
  - /2.png
  - /3.png
  - /Ctrend.jpeg
---

## Overview (Ongoing)
I am working as a **Graduate Student Researcher in the Vibration & Acoustics Laboratory: Microsystems**, focused on **MEMS scanning mirror** research. My current emphasis is **nonlinear analysis** of electrostatically actuated MEMS mirrors, combining simulation-driven design with experimental validation.

---

## What I’ve completed so far

### 1) COMSOL modal analysis → experimental validation
- Built a **COMSOL modal model** of the MEMS scanning mirror to identify resonant frequencies and mode shapes relevant to scanning performance and structural integrity.
- Performed **experimental modal testing** using a **DAQ-based setup** with controlled excitation and multi-sensor measurements.
- Extracted and compared **resonant frequencies, damping estimates, and mode shapes** (via FRF peak identification and mode-shape interpretation) to validate the simulation model and establish a trustworthy baseline for further nonlinear work.

---

## Co-design workflow (MEMS chip + PCB + packaging)
- Driving an **electromechanical co-design** workflow by coordinating:
  - **MEMS chip CAD** in **AutoCAD/SOLIDWORKS** (geometry, mounting features, keep-out regions),
  - with **Altium PCB layout** (footprint alignment, electrode routing, connector placement),
- Ensuring **mechanical stability** and packaging compatibility: alignment tolerance, mounting constraints, and robust electrical/mechanical integration for lab testing and future revisions.

---

## Electrostatic modeling of comb-drive fingers (2D capacitive model)
Built a **2D electrostatic model** of comb-drive finger electrodes to extract:
- **Capacitance**
- **Electric field distribution**
- **Potential distribution**

### Key modeling upgrades implemented (best practices)
Based on COMSOL electrostatics best practices, the model is being refined to ensure capacitance changes correctly with geometry/motion:

- **Realistic exterior domain:** ensured the capacitor geometry does not act as the outer boundary of the model by adding an enclosing exterior domain so the **electric field can develop naturally** around the structure. For large/unbounded environments, the approach supports **Infinite Element Domains**.
- **Correct dielectric physics:** ensured dielectric properties are not ignored by default “free space” assumptions by adding **Charge Conservation in Solids** when dielectric material properties differ from air/vacuum.
- **Deforming-domain electrostatics:** for moving comb fingers, shifted toward a **Deformed Mesh / ALE approach** so the electrostatics solution is evaluated on the **deformed geometry** without unnecessary solid-mechanics solves or repeated remeshing.
  - When full coupling is required, the workflow supports COMSOL’s **Electromechanics, Solid** multiphysics coupling.

### Capacitance extraction strategy
- Used **Terminal** to compute **Maxwell capacitance** directly for two-conductor extraction.
- For multi-conductor extensions, structured the workflow to support **capacitance matrix** extraction using a **Stationary Source Sweep** study when needed.
- Debugged “capacitance not changing” failure modes by verifying the full chain:
  - motion → mesh deformation → electrostatics solution on deformed domain → capacitance post-processing.

---

## Current work (Nonlinear MEMS mirror analysis)
- Extending the validated baseline model into **nonlinear electrostatic actuation regimes**, where electrostatic forces and geometry-dependent capacitance can introduce:
  - nonlinear stiffness / softening effects,
  - amplitude-dependent resonance shifts,
  - stability limits (pull-in / snap-through risk depending on actuation mode and geometry).
- The goal is a simulation + test pipeline that can predict **frequency response changes under bias**, and guide geometry/electrode updates for stable, high-Q scanning behavior.

---

