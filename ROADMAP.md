# Open Hair Stack — Technical Architecture & Strategic Roadmap

> **The North Star:** Building an open, reproducible, sub-millimeter stereotaxic robotic platform capable of autonomous hair follicle harvesting, 3D trajectory planning, and high-density implantation of autologous grafts and bio-engineered follicle organoids.

[![Status: Active](https://img.shields.io/badge/Status-Active%20Roadmap-blue?style=flat-square)](https://github.com/openhairstack)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

---

## Executive Architecture Overview

```
                                  ┌────────────────────────────────────────┐
                                  │           THE NORTH STAR GOAL          │
                                  │  Autonomous Stereotaxic Hair Robotics  │
                                  │   & Bio-Cloned Organoid Implantation   │
                                  └───────────────────▲────────────────────┘
                                                      │
                                                      │
                         ┌────────────────────────────┴────────────────────────────┐
                         │                                                         │
       ┌─────────────────┴─────────────────┐                     ┌─────────────────┴─────────────────┐
       │             PHASE 3               │                     │             PHASE 4               │
       │     Open Hardware & Robotics      │                     │     Autonomous Implantation       │
       │  • 6-DoF Micro-Manipulator        │                     │  • Micro-Graft Sorter & Inserter  │
       │  • Sub-mm Oscillating Punch       │                     │  • Closed-Loop Depth Limiter      │
       │  • Force-Torque Dermal Sensing    │                     │  • Follicle Organoid Bio-Docking  │
       │  • ROS 2 Real-Time Control Loop   │                     │  • Sub-100µm Dermal Stereotaxy    │
       └─────────────────▲─────────────────┘                     └─────────────────▲─────────────────┘
                         │                                                         │
                         └────────────────────────────┬────────────────────────────┘
                                                      │
                         ┌────────────────────────────┴────────────────────────────┐
                         │                                                         │
       ┌─────────────────┴─────────────────┐                     ┌─────────────────┴─────────────────┐
       │             PHASE 1               │                     │             PHASE 2               │
       │   Foundation CV & Data Commons    │                     │  Stereotaxic Depth & Planning     │
       │  • 2D Follicle Detection (v0.1)   │                     │  • Dual-Camera Stereoscopic Vision│
       │  • Multi-Class Bundle Taxonomy    │                     │  • Subcutaneous Exit Angle Vector │
       │  • Fitzpatrick I–VI Dataset Scale │                     │  • Optical Coherence Tomography   │
       │  • Client-Side WASM / WebGPU Demo │                     │  • Safe Donor Area (SDA) Mapping  │
       └───────────────────────────────────┘                     └───────────────────────────────────┘
```

---

## Phase 1: Foundation Computer Vision & Dataset Commons (Current — 2026 Q4)

### Status: v0.1 Baseline Live
* **Delivered:**
  * Automated dataset validation harness checking coordinate normalization, class labels, and split leakage (`data-pipeline`).
  * Standardized follicular unit taxonomy: `fu1` (1-hair), `fu2` (2-hair), `fu3` (3-hair), `fu4` (4-hair), `fu5` (5+-hair).
  * Ultralytics YOLO11n fine-tuning pipeline automated via Google Colab with published weights on Hugging Face (`openhairstack/follicle-fu-v0.1`).
  * 100% client-side WebAssembly analyzer running locally in the browser with zero server telemetry (`openhairstack/scalp-analyzer`).
  * Baseline evaluation floor: 24.9% recall on dominant 2-hair units (`fu2`).
* **Active Milestones:**
  * **Dataset Scaling:** Expand from 688 images to 5,000+ public CC-BY trichoscopy micrographs.
  * **Demographic Diversity:** Rigorous stratification across Fitzpatrick skin phototypes I–VI and hair curl patterns 1A through 4C (tight coily hair with acute subcutaneous curvature).
  * **Class Imbalance Correction:** Implement Focal Loss and class-balanced cross-entropy to boost recall on single-hair (`fu1`) and high-count (`fu3–fu5`) bundles.
  * **WebGPU Real-Time Inference:** Upgrade `scalp-analyzer-web` to support WebGPU execution, delivering 60 FPS live camera tracking.

---

## Phase 2: Stereotaxic Depth Sensing & Micro-Planning (2027)

### Technical Challenge
In biological scalp tissue, hair shafts emerge from the skin at acute surface angles (typically 30° to 60°) and curve subcutaneously toward the follicular bulb at depths of 3.5 mm to 5.0 mm. Standard 2D top-down bounding boxes only locate the surface pore (ostium), which is insufficient for physical robotic harvesting without severe transection.

### Key Milestones:
1. **3D Hair Shaft Exit Vector Regression:**
   * Extend the neural detection architecture to output 6-DoF pose vectors:
     $$\mathbf{v} = (x, y, z, \theta_{\text{azimuth}}, \phi_{\text{elevation}}, \kappa_{\text{curvature}})$$
   * Predict subcutaneous trajectory using directional reflectance under cross-polarized illumination.
2. **Stereoscopic Trichoscopy Calibration:**
   * Calibrated dual-camera sensor heads providing sub-millimeter epipolar geometry and depth disparity mapping.
3. **Subsurface Imaging Integration (OCT & Ultrasound):**
   * Interface high-frequency ultrasound (HFUS, 50–70 MHz) and Optical Coherence Tomography (OCT) datasets to validate non-invasive subcutaneous bulb localization.
4. **Algorithmic Safe Donor Area (SDA) Mapping:**
   * Automated contouring of occipital and parietal safe zones to calculate maximum lifetime harvest capacity without creating donor thinning or cosmetic moth-eaten appearance.

---

## Phase 3: Open Hardware & Micro-Actuation Rig (2027–2028)

### Technical Challenge
Commercial systems like ARTAS cost upwards of $200,000 and rely on locked industrial robot arms. Open Hair Stack will specify an open, reproducible, desktop-scale stereotaxic actuation rig under the CERN-OHL-P open hardware license.

### Key Milestones:
1. **5-DoF to 6-DoF Micro-Manipulator Kinematics:**
   * Low-inertia, high-rigidity Cartesian or delta-kinematic micro-robotic head with closed-loop optical linear encoders (< 20 µm positional repeatability).
2. **High-Speed Oscillating / Rotational Punch:**
   * Modular 0.8 mm – 0.9 mm inner-diameter trumpet punches actuated at 2,000 to 5,000 RPM using brushless DC micro-motors to cleanly incise stratum corneum without shear-induced follicle transection.
3. **Dynamic Force-Torque Dermal Sensing:**
   * Sub-millinewton multi-axis piezoelectric load cells positioned directly behind the needle punch.
   * Detecting the distinct force inflection point as the punch passes from dense reticular dermis into compliant subcutaneous adipose tissue, triggering immediate micro-retraction within 5 milliseconds.
4. **Deterministic Real-Time Middleware:**
   * Robot Operating System 2 (ROS 2) integration using C++20 nodes and CycloneDDS zero-copy intra-process transport, guaranteeing deterministic 1,000 Hz control loops.

---

## Phase 4: Autonomous Implantation & Bio-Cloning Integration (North Star)

### Technical Challenge
The ultimate frontier of trichology is not merely redistributing existing donor follicles (which is zero-sum and constrained by finite donor supply), but the **multiplication and de-novo implantation of cultured hair follicle organoids**. Once biotech labs (e.g. Tsuji Lab/RIKEN, Stemson Therapeutics, dNovo) produce millions of in-vitro cultured dermal papilla spheroids and follicle primordia, human manual surgery becomes physically impossible due to shear volume and micro-scale fragility.

### Key Milestones:
1. **Automated Micro-Graft Sorter & Implantation Mechanism:**
   * Pneumatic micro-handling cartridges loading, sorting, and delivering single-hair and multi-hair units into recipient micro-incisions at clinical aesthetic densities (30–45 FU/cm²).
2. **Bio-Docking Interface for Follicle Germs (HFGs):**
   * Specialized micro-cannula tooling designed for gentle, non-traumatic stereotaxic delivery of laboratory-cultured follicle organoids into the sub-epidermal junction.
3. **Neural-Chip Level Stereotaxic Depth Control:**
   * Sub-100-micron depth targeting ensuring cultured grafts are placed precisely adjacent to the dermal vascular plexus for immediate re-vascularization and nutrient perfusion, with zero crush injury.

---

## How to Contribute to the Roadmap

We invite researchers, roboticists, dermatologists, and software engineers to collaborate:
* **Computer Vision Engineers:** Contribute to Phase 1 loss weighting and Phase 2 exit angle vector heads in [`follicle-detect`](https://github.com/openhairstack/follicle-detect).
* **Trichologists & Clinicians:** Donate de-identified, CC-BY dermatoscope images and validate annotation guidelines in [`data-pipeline`](https://github.com/openhairstack/data-pipeline).
* **Roboticists & Hardware Designers:** Join Phase 3 RFC discussions in [`governance/rfcs`](https://github.com/openhairstack/governance/tree/main/rfcs).
* **Autonomous AI Agents:** Follow the machine runbooks in [`.github/SKILL.md`](https://github.com/openhairstack/.github/blob/main/SKILL.md).
