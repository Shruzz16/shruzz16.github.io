---
layout: project
title: "TEAM PHOENIX RACING (FBEV 2023) | Suspension & Steering 
thumbnail: /assets/projects/SAE_FBEV_2023/thumb.png
---

## Project Overview
Designed and optimized the suspension, steering, and wheel assembly for a Formula Student–type EV. The work followed a kinematics-first workflow (bump, roll, steer, and combined conditions) and translated into manufacturable hardware validated through force calculations and ANSYS simulation, including topology optimization for weight reduction.

## Skills Used
• Lotus Shark (suspension kinematics)  
• Optimum Kinematics (verification checks)  
• SolidWorks (2D steering + full 3D integration)  
• MATLAB (force and moment calculations, sizing)  
• ANSYS (stress/FOS checks, topology optimization)  
• DFM mindset (tube-based links, CNC/VMC machinability)  
• Material selection and justification for steering, suspension, uprights

## Design Report
• PDF: [EA05_CGMR_SnS_Design_Report_FBEV_2023.pdf](/assets/projects/SAE_FBEV_2023/EA05_CGMR_SnS_Design_Report_FBEV_2023.pdf)

## What I worked on
Built an end-to-end pipeline from performance targets and geometry assumptions → kinematic iteration → steering development to meet turning-radius needs → full 3D integration → force-based sizing → FEA validation + topology optimization → final upright + hub/spindle + bearing packaging.

## Key Work Completed

### 1) Objectives and design targets
• Better driving stability across bump, roll, steer, and combined conditions  
• Maintain maximum contact patch and predictable camber/toe behavior  
• Higher cornering performance and reduced understeer tendencies  
• Allow static angle adjustability through upright and link design  
• Driver-focused constraints like ergonomics, weight, and safety

### 2) Tire selection and rationale
• Selected 13-inch tires for higher cornering stiffness and better packaging space  
• Final tire selection: Hoosier 20.5 × 7.0–R13 (A2500 / R25B, Bias/Cross Ply)

### 3) Suspension kinematics workflow
• Iterated hardpoints in Lotus Shark to stabilize kinematic curves  
• Evaluated toe/camber response in bump and roll, refined until behavior was acceptable  
• Cross-checked and validated geometry in Optimum Kinematics

### 4) Steering design and packaging
• Designed for target turning radius of 2700 mm with wheelbase assumption of 1550 mm  
• Built 2D steering geometry in SolidWorks, then integrated into full 3D steering + suspension model  
• Reduced bump steer by aligning tie-rod axis with the intersection of extended A-arm lines  
• Tuned rack placement, rack travel, steering arm length, and packaging constraints

### 5) Hardware design + verification (MATLAB + ANSYS)
Wishbones  
• Tube-based wishbones sized using MATLAB force outputs  
• Threaded tube ends with rod-end bearings for adjustability  
• ANSYS checks under combined loading envelopes

Tie rods  
• Tube + rod-end bearing assemblies sized from geometry and loading  
• ANSYS validation for stress/FOS

Rocker  
• VMC-machinable geometry with bearing provisions  
• ANSYS stress/FOS checks + topology optimization

Upright / knuckle + wheel assembly  
• Upright designed to preserve static angles and ensure brake and link packaging  
• Hub/spindle + bearing strategy designed for combined radial/axial loads  
• ANSYS checks for shear, compression, and bending + topology optimization

## Material selection (highlights)
• Rack: EN24  
• Pinion: 20MnCr5  
• Rack casing: Al 6061-T6  
• Steering column + U-joints: AISI 1040  
• A-arms: AISI 4340 (normalized)  
• Pushrod: AISI 4130 (normalized)  
• Hub/spindle: EN24  
• Knuckle: Al 6061

