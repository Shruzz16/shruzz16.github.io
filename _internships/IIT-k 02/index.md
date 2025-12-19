---
layout: post
title: >-
  Internship 2023 | Design & Development of an LED–Halogen Hybrid Solar Simulator (SURGE) | Indian Institue of Technology, Kanpur
description: >-
  Designed and prototyped a compact LED–halogen hybrid solar simulator for long-duration indoor testing of solar-energy devices,
  aligned to terrestrial solar-simulator evaluation metrics (spectral match, spatial non-uniformity, temporal instability) using AM1.5
  reference spectrum guidance.
skills:
  - Solar Simulator Design
  - Opto-Mechanical Design
  - Thermal Management
  - Irradiance Uniformity & Stability
  - SolidWorks CAD
main-image: /whole_model.jpeg
images:
  - /upper part.jpeg
  - /whole_model.jpeg
  - /proto_1.jpg
  - /proto_2.jpg
  - /1 spectral.jpeg
  - /2 spatial .jpeg
  - /3 temporal.jpeg

---

## Overview

### Objective
- Developed a **cost-effective, compact hybrid solar simulator** for controlled, repeatable lab testing of solar-energy devices, targeting performance criteria typically assessed for terrestrial simulation:
  - **Spectral match**
  - **Spatial non-uniformity (SNU)**
  - **Temporal instability (TI)**

### System architecture and opto-mechanical design
- Designed a compact enclosure based on a **hexagonal prismatic structure** to increase illuminated area and support **concentrated solar power (CSP)-style focusing**.
- Implemented a **multi-source hybrid emitter**:
  - **High-power white LED module** to strengthen deficient spectral bands and improve controllability.
  - **Dichroic halogen lamp** to provide broad continuous spectral content closer to sunlight-like emission.
- Integrated optical and thermal subsystems for beam conditioning and stability:
  - **Collimating optics** (collimating lens) to reduce divergence and improve usable irradiance on the test plane.
  - **ND filtering** (neutral-density attenuation) to tune intensity and assist spectral shaping / balancing.
  - **Thermal heat-sink based LED cooling** to control substrate temperature and reduce drift-driven temporal instability.
  - **Truncated cone / reflective-face concentrator** guided by **flow-line geometry** to direct and focus light toward the target plane.

### Key design parameters and hardware specification
- **Target/illumination region:** focused illumination on an area on the order of **~10 × 10 cm²** for device-level testing.
- **LED module (white, high power):**
  - Power rating: **100 W**
  - CCT: **6000–6500 K**
  - Forward voltage: **30–34 V**
  - Forward current: **~3 A**
- **Dichroic halogen lamp:**
  - Rating: **12 V, 50 W**
  - Broad visible spectrum emission (≈ 400–700 nm), with “cool beam” characteristic to manage forward heat load.
- CAD-driven integration: developed the full mechanical model in **SolidWorks**, including emitter placement on prismatic faces and packaging for optics + thermal hardware.

### Performance evaluation methodology
- Benchmarked simulator output against the **AM1.5 reference spectrum** concept and terrestrial simulator criteria:
  - **Spectral distribution comparison** across configurations (LED-only, halogen-only, LED–halogen hybrid, LED+ND, hybrid+ND).
  - **Temporal instability assessment** emphasizing LED substrate temperature dependence and thermal-management impact.
  - **Spatial non-uniformity mapping** on the test plane and iteration on source placement/beam conditioning to flatten irradiance gradients.

### Outcomes
- Delivered a **functioning prototype** demonstrating feasibility of a compact, low-cost hybrid architecture with improved controllability.
  
