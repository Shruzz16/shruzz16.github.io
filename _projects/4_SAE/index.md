---
layout: post
title: TEAM PHOENIX RACING (FBEV 2023) | Suspension & Steering System Design
description: >-
  Suspension, steering, and wheel-end design for a Formula Student EV using a kinematics-first workflow (bump/roll/steer),
  followed by force-based sizing and ANSYS verification. Includes steering geometry for turning-radius targets, bump-steer
  reduction via tie-rod/A-arm alignment, and manufacturable hardware concepts for wishbones, tie rods, rocker, upright,
  hub/spindle, and bearing strategy.
skills:
  - "Suspension Kinematics (Bump/Roll/Steer, Camber/Toe Behavior)"
  - "Steering Geometry (Ackermann, Turning Radius, Rack Travel, SAL)"
  - "SolidWorks (2D Steering + 3D Integration)"
  - "Lotus Shark (Hardpoint Iteration + Kinematic Plots)"
  - "Optimum Kinematics (Cross-Verification + Combined Conditions)"
  - "MATLAB (Force/Moment Sizing, Buckling Checks)"
  - "ANSYS (Stress/FOS Validation, Topology Optimization)"
  - "DFM for Student Racecar Hardware (Tube Links, Rod Ends, CNC/VMC Parts)"
main-image: 4.jpeg
images:
  - 1.jpeg
  - 2.jpeg
  - 3.jpeg
  - 4.jpeg
  - 5.jpeg
  - 6.jpeg
    
---

## Overview
Designed and packaged the **front suspension + steering + wheel-end** for **Team Phoenix Racing (FBEV 2023)**. The workflow started with
**tire selection and kinematic targets**, then iterated hardpoints to stabilize **camber/toe behavior** across **bump and roll**, followed by
a steering layout that met turning-radius requirements and minimized **bump steer**. Final concepts were translated into **manufacturable
hardware** and verified using **force-based sizing** and **ANSYS simulation**, including **topology optimization** where weight could be removed
without sacrificing strength.

---

## What I completed

### 1) System targets and constraints
- Set handling-driven targets focused on **stable camber/toe trends** across bump and roll and maintaining a **consistent contact patch**.
- Prioritized **predictable steering feel** and avoided geometry choices that bias the car toward **understeer**.
- Built in **adjustability** (static angles and alignment) through upright/link architecture and rod-end based links.
- Packaged the system around realistic manufacturing and service constraints for a student-built EV.

---

### 2) Tire selection and rationale
- Selected **13-inch tires** for better **cornering stiffness** compared to 10-inch options and improved space for packaging brakes and suspension.
- Final tire selection: **Hoosier 20.5 × 7.0–R13 (A2500 / R25B, Bias/Cross Ply)**.

---

### 3) Suspension kinematics workflow (Lotus Shark + verification)
- Iterated suspension hardpoints in **Lotus Shark** to stabilize kinematic behavior and avoid undesirable camber/toe trends.
- Evaluated suspension response in **bump** and **roll**, then refined geometry until trends were acceptable.
- Cross-checked geometry and plots using **Optimum Kinematics**, including cases that capture combined effects more clearly.

---

### 4) Steering geometry and packaging (2D → 3D integration)
- Designed steering around a target **turning radius of 2700 mm** with a feasible **wheelbase assumption of 1550 mm**.
- Built a **2D steering layout in SolidWorks** to define feasible steering arm geometry and rack travel needs.
- Converted the steering system into full **3D integration** with suspension geometry for packaging and interference realism.
- Reduced bump steer by aligning the tie-rod axis to meet the intersection of extended **upper and lower A-arm lines**.
- Tuned rack placement, steering arm length, and rack travel to balance steering response and packaging constraints.
- Integrated steering column and universal joints terminating at the rack while maintaining driver-oriented packaging.

---

## Hardware design and verification

### Wishbones
- Tube-based wishbones designed around **vendor-available tube sizes** for practical sourcing and manufacturing.
- Used **MATLAB force and moment outputs** to size members conservatively and avoid buckling/overstress.
- Used threaded tube ends + rod-end bearings for alignment adjustability and repeatable assembly.
- Verified critical load cases in **ANSYS**, including combined bending/tension and bracket-driven local effects.

### Tie rods
- Tube + rod-end architecture sized from geometry and loading outputs.
- Verified stresses and safety margins in **ANSYS**.

### Rocker
- Designed for **VMC machinability** with bearing provisions and practical thickness regions.
- Verified strength in **ANSYS** and applied **topology optimization** to reduce mass while preserving load paths.

### Upright / wheel-end (hub, spindle, bearings, brake packaging)
- Developed a compact wheel-end concept that maintains static geometry targets and supports brake and joint packaging.
- Bearing strategy used **back-to-back taper roller bearings** to handle combined radial + axial loads and reduce play.
- Included simulation checks for shear, compression, and bending, followed by **topology optimization** where appropriate.

---

## Materials (highlights)
- Rack: EN24
- Pinion: 20MnCr5
- Rack & pinion casing: Al 6061-T6
- Steering column + universal joints: AISI 1040
- A-arms: AISI 4340 (normalized)
- Pushrod: AISI 4130 (normalized)
- Hub/spindle integrated: EN24
- Knuckle: Al 6061

---

## Report
Design report PDF: [EA05_CGMR_SnS_Design_Report_FBEV_2023.pdf](/assets/projects/SAE_FBEV_2023/EA05_CGMR_SnS_Design_Report_FBEV_2023.pdf)
