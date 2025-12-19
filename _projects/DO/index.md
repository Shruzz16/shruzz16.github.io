---
layout: post
title: >-
  Optimization of a Passenger Vehicle Suspension System for Performance and Cost | MATLAB (ode45 + fmincon) + GA | Tesla Model 3–Based Model
description: >-
  Built a coupled, system-level optimization model for a passenger-vehicle suspension to maximize a weighted performance score
  balancing ride comfort, handling, and spring material cost. Implemented a 3-subsystem workflow (quarter-car dynamics, double-wishbone
  camber/geometry, and coil-spring cost/geometry) with shared coupling variables and solved using MATLAB fmincon + GA, including
  constraint and parameter sensitivity analyses.
skills:
  - Vehicle Dynamics (Quarter-Car Model)
  - Suspension Optimization (System-Level Coupling)
  - MATLAB (ode45, fmincon, Genetic Algorithm)
  - Handling Metrics (Camber Gain / Roll)
  - Coil Spring Design & Cost Optimization
main-image: /DO_PORTFOLIO.png
images:
  - /1.jpeg
  - /2.jpeg
  - /3.jpeg
    
---

## Overview
Developed and optimized a **passenger vehicle suspension system** to **minimize cost while maximizing ride comfort and handling**.
The model was parameterized using a **Tesla Model 3–based** reference vehicle and organized into **three coupled subsystems**:
1) spring–damper tuning (comfort/ride),  
2) suspension geometry (camber/handling),  
3) coil spring material/cost optimization.

---

## System model and coupling
### Subsystems
- **Subsystem 1 (Ride comfort / dynamics):** quarter-car model with sprung/unsprung masses, suspension stiffness **ks** and damping **cs**, and a road disturbance modeled as a **pothole pulse**.
- **Subsystem 2 (Handling / geometry):** double-wishbone style camber model with roll-center effects; computes geometry-dependent quantities and spring–damper attachment points.
- **Subsystem 3 (Cost / spring design):** coil-spring sizing (wire diameter **d**, mean diameter **D**) to minimize spring material cost while meeting stiffness and manufacturability/buckling constraints.

### Key coupling variables
- **Track width (Tf)** and **static camber (γstatic)** from Subsystem 2 affect Subsystem 1 and 3 through kinematics/packaging.
- **Spring–damper angle (θ)** and **spring length (ls)** come from geometry and feed into dynamics and spring sizing.
- **Spring stiffness (ks)** from Subsystem 1 feeds Subsystem 3 as the required stiffness target.

---

## Mathematical formulation (high-level)
### Subsystem 1: Quarter-car dynamics + comfort objective
- Solved coupled ODEs for **sprung/unsprung motion** with an angled spring–damper factor **cos(θ)**.
- Road input modeled as an **inverted rectangular pulse** (pothole depth **dp**, width **wp**, vehicle speed **v**).
- Comfort objective combines:
  - **peak body acceleration** (max |ẍs|),
  - plus an integrated oscillation term over a time window.

### Subsystem 2: Camber/handling objective
- Modeled camber behavior under roll using roll-center-dependent **camber gain** and a max roll angle constraint.
- Objective minimizes outward camber/tire wear proxies using squared camber terms at max roll.

### Subsystem 3: Spring cost objective
- Coil spring relations used to link **ks** to geometry (d, D, pitch, coil count).
- Cost modeled proportional to spring mass using steel density and $/kg cost.

---

## Constraints (feasibility + safety)
Applied negative-null inequality constraints spanning:
- bottoming-out clearance,
- damping ratio bounds (ζ lower/upper),
- camber stability and variation limits,
- coil interference and buckling constraints,
- design variable bounds for ks, cs, Tf, γstatic, d, D, pitch.

---

## Optimization approach (MATLAB)
- **System-level optimization:** MATLAB **fmincon** maximized a **normalized weighted score** combining the three subsystem objectives.
- **Time-domain evaluation:** Subsystem 1 dynamics solved using **ode45** each iteration to compute the comfort metric.
- **Geometry optimization:** Subsystem 2 used a **Genetic Algorithm (GA)** to minimize the camber objective and output geometry/attachment points.
- **Sequential coupling:** coupling variables passed between subsystems during the system-level loop to preserve interdependence.

---

## Results summary
- System-level optimization produced stable optima across multiple runs with minor variation due to time discretization sensitivity in the peak-acceleration metric.
- The solution was bounded by active constraints on:
  - **minimum wire diameter (dmin)** and
  - **maximum mean coil diameter (Dmax)** at the optimum.
- Reality-check comparison indicated optimized **ks** fell within typical sedan stiffness ranges, while optimized damping leaned higher to suppress sustained vibrations.

---

## Sensitivity analysis (post-optimality)
### Active constraint sensitivity
- System output showed high sensitivity to the **lower bound of wire diameter d**, indicating thin wire rapidly degrades feasibility/performance.
- Sensitivity to mean coil diameter **D** bounds was comparatively smaller, with limited benefit from relaxing constraints.

### Parameter sensitivity
- **Pothole depth (dp)** had the strongest negative influence on the objective (deeper pothole → worse comfort metric).
- **Pothole width (wp)** had minimal effect relative to depth.
- **Roll center height (hrc)** showed moderate influence via camber/handling behavior.

---

## Outcome
Delivered a complete, coupled suspension optimization framework that:
1) integrates **ride + handling + cost** into a single system metric,  
2) respects feasibility constraints and design bounds, and  
3) supports decision-making using **constraint/parameter sensitivities** to identify what truly drives performance and cost.
