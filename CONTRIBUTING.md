# Contributing to Open Hair Stack

> Open Hair Stack welcomes contributions from human researchers, clinicians, engineers, and autonomous AI coding agents (Claude Code, Cursor, Windsurf, Devin, Antigravity).

[![Developer Certificate of Origin](https://img.shields.io/badge/DCO-Signed--off--by-blue.svg?style=flat-square)](https://developercertificate.org/)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=flat-square)](https://opensource.org/licenses/Apache-2.0)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

---

## 1. Quick Start for Autonomous AI Agents

If you are pointing an AI coding agent at this repository, pass the skill specification file directly to your agent:

```bash
# Agent initialization instruction:
# Point your agent at the Open Hair Stack skill specification:
.github/SKILL.md
```
The skill file provides automated machine-readable runbooks for:
* Running dataset schema and integrity validation (`data-pipeline/scripts/validate_dataset.py`).
* Training YOLO11 detection models and evaluating against baseline benchmark floors (`follicle-detect/train.py`).
* Exporting simplified ONNX graphs for client-side WebAssembly execution.
* Testing and validating the browser interface (`scalp-analyzer-web`).

---

## 2. Ground Rules & Ethics

1. **Permissive Open Licenses:**
   * All code is contributed under **Apache 2.0**.
   * All datasets, models, and documentation are contributed under **CC BY 4.0**.
   * Hardware kinematics and CAD files are contributed under **CERN-OHL-P v2**.
   * We use the [Developer Certificate of Origin (DCO)](https://developercertificate.org) — sign all commits with `git commit -s`.
2. **Absolute Patient Privacy:**
   * **Never commit patient-identifiable imagery, faces, or medical record numbers (MRNs).**
   * All clinical imagery must be tightly cropped dermatoscope or trichoscope micrographs with documented CC-BY provenance or explicit written patient consent.
3. **Research Software Boundaries:**
   * Open Hair Stack is experimental research and educational software. It does not provide medical diagnoses, treatment planning, or clinical claims.
4. **Reproducibility Mandate:**
   * If you submit a model or dataset change, include full training configuration, dataset checksums, and validation evaluation metrics.

---

## 3. Contribution Pathways

### Pathway A: Trichoscopy Data & Annotation (No Coding Required)
We urgently need diverse trichoscopy data to expand our dataset from 688 images to 5,000+:
* **Skin Tone Diversity:** Micrographs representing Fitzpatrick skin phototypes IV, V, and VI.
* **Hair Texture Diversity:** Curly and coily hair types (3A through 4C) where subcutaneous follicle curvature is pronounced.
* **How to contribute:**
  1. Review [`data-pipeline/ANNOTATION_GUIDE.md`](https://github.com/openhairstack/data-pipeline/blob/main/ANNOTATION_GUIDE.md).
  2. Use open annotation tools (e.g., CVAT, Label Studio, Roboflow).
  3. Run the validator: `python scripts/validate_dataset.py --input <your_dataset_path>`.
  4. Open a PR with your annotation dataset and license provenance.

### Pathway B: Computer Vision & Model Architecture
* **Class Imbalance Loss:** Implement Focal Loss or class-weighted cross-entropy in YOLO heads to boost recall on single-hair (`fu1`) and 3+-hair (`fu3–fu5`) bundles.
* **3D Exit Vector Regression:** Help develop detection heads that predict hair shaft angle and subcutaneous emergence trajectory (`[cx, cy, w, h, roll, pitch, yaw]`).
* **WebGPU Acceleration:** Implement WebGPU execution in `scalp-analyzer-web/app.js` for 60 FPS live camera tracking.
* **How to contribute:** Pick an issue in [`follicle-detect/issues`](https://github.com/openhairstack/follicle-detect/issues).

### Pathway C: Robotics, Kinematics & Embedded Hardware
* **Micro-Manipulator Design:** Draft 5-DoF Cartesian or delta-kinematic micro-actuation rigs capable of sub-100-micron positioning.
* **Force-Torque Signal Processing:** Develop algorithms to process load cell signals detecting the dermis-to-adipose tissue transition.
* **ROS 2 Integration:** Write deterministic C++20 ROS 2 nodes for visual servoing and motion compensation.
* **How to contribute:** Review [`governance/ROADMAP.md`](ROADMAP.md) and join Phase 3 discussions in [`governance/rfcs`](https://github.com/openhairstack/governance/tree/main/rfcs).

### Pathway D: Literature & Research Library
* Help maintain our comprehensive research bibliography in [`.github/AWESOME.md`](https://github.com/openhairstack/.github/blob/main/AWESOME.md) by submitting relevant papers, commercial benchmarks, and regenerative medicine breakthroughs.

---

## 4. Development Environment Setup (Python 3.10+)

```bash
# Clone the target repository
git clone https://github.com/openhairstack/<repo-name>.git
cd <repo-name>

# Create isolated environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

## 5. Pull Request Verification Checklist

Before submitting a Pull Request, verify:
- [ ] Commits are signed off (`git commit -s -m "..."`).
- [ ] Code adheres to style guidelines (`ruff check`, `black --check`).
- [ ] Automated tests and integrity scripts pass.
- [ ] No patient-identifiable information, API secrets, or large binary files (> 100MB) are included.
- [ ] Any new data includes license provenance documented in `DATASETS.md`.

---

## 6. Questions & Technical Inquiries

* **Project Lead:** Salik Shah
* **Direct Contact:** DM [@salik on X](https://x.com/salik) (fastest for technical discussions, research collaborations, and press).
* **Discussions:** [GitHub Discussions](https://github.com/orgs/openhairstack/discussions).
