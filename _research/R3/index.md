---
layout: post
title: >-
  Automotive Body-in-White (BIW) Structural Redesign | Baseline Stamped vs STAF Tube-Formed Architecture | CAE Validation (CATIA V5, HyperMesh, LS-DYNA)
description: >-
  I maintain a baseline BIW model with stamped sheet-metal
  members and develop a second concept where selected stamped parts are replaced with STAF tube-formed structural members.
  Current work focuses on CAD assembly refinement, tube-to-sheet joint/interface design, CAE-ready cleanup, and simulation
  workflows in HyperMesh/LS-DYNA to quantify stiffness/strength gains, mass reduction potential, and cost-effective,
  manufacturable trade-offs.
skills:
  - BIW CAD Assembly (CATIA V5)
  - Tube-Formed Structural Design (STAF Concepts)
  - Joint & Interface Design (Tube-to-Sheet, Datums, Tolerances)
  - CAE Preprocessing (HyperMesh: Mesh, Contacts, Connections)
  - Structural Simulation Support (LS-DYNA)
  - Design Iteration from CAE Feedback (Performance vs Weight vs Cost)
---

## Overview (Comparative Study)
I am working on a **comparative BIW structural redesign + validation** effort where I maintain:
- a **baseline BIW model** built primarily from **stamped sheet-metal members**, and
- a redesigned concept where selected stamped members are replaced with **STAF tube-formed structural components**.

The goal is to run consistent structural evaluations on both architectures and clearly show **why the STAF concept improves stiffness/strength while enabling weight reduction and cost-effective manufacturability**.

---

## Why this matters (what STAF improves)
- A **stamped-only BIW** can be efficient, but stiffness targets often drive added reinforcements, thicker gauges, or complex stampings.
- **STAF tube-formed members** support:
  - higher **bending/torsional stiffness per unit mass**
  - stronger **load-path continuity** using closed-section members
  - potential **part consolidation** and simpler structural members in targeted regions
  - a practical route to **lightweight + cost-effective** upgrades when joints are designed for manufacturability

---

## What I’m building (two comparable models)
- **Baseline model:** BIW CAD assembly using stamped members only (reference architecture).
- **STAF concept model:** the same BIW packaging and assembly intent, with selected members replaced by **tube-formed structural members**.
- I keep the comparison fair by aligning:
  - interfaces and packaging constraints
  - load introduction locations and constraints
  - connection intent and boundary condition philosophy across both builds

---

## What I’m doing right now (CAD → CAE → iterate)
- **CAD assembly refinement in CATIA V5:** I update and maintain BIW structures while preserving interfaces, mating intent, and packaging constraints.
- **Tube-to-sheet joint and interface design:** I define datums, mating features, clearances/tolerances, and transition concepts to maintain **load transfer continuity** and integration feasibility.
- **Geometry cleanup for CAE readiness:** I defeature/simplify assemblies to reduce meshing artifacts while preserving the structural behavior that matters.
- **HyperMesh preprocessing:** I create simulation-ready models (mesh strategy, connections/contacts, model checks) for consistent correlation between concepts.
- **LS-DYNA structural evaluation support:** I run/assist stiffness and strength-focused evaluations and iterate member/joint concepts based on CAE outcomes.

---

## Testing & comparison (what I evaluate)
To demonstrate “why STAF is better,” I compare both architectures using consistent checks focused on:
- **stiffness response** (global and local deflections under representative load cases)
- **strength trends** (stress/strain hotspots, load-path behavior, joint sensitivity)
- **mass impact** (where tube substitution enables meaningful weight reduction)
- **manufacturability & cost logic** (tube feasibility, joint complexity, potential reduction in stamping complexity/part count)

---

## What I bring (my value-add)
- I connect **CAD design intent ↔ CAE correctness**: I design parts/joints that are **manufacturable**, but also **simulation-ready** and testable.
- I own the full loop: **CAD update → defeature → mesh/connection setup → interpret results → redesign**.
- I produce decision-ready outputs: **trade studies, BOM updates, and clear documentation** so the design direction is easy to justify and communicate.

---


