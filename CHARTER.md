# Charter

**Version 0.1 — for community review**

## Vision

A world where hair restoration technology is transparent, measured, and accessible — where the robotics and AI behind it are a shared public good rather than a locked cabinet.

## Mission

Build the open-source stack for AI-assisted hair restoration: open datasets, benchmarked follicle-detection models, reproducible evaluation, runnable demos, and — over time — open hardware and planning software for graft placement.

## Why this project exists

1. **The robots are real and the software is closed.** Robotic follicular unit extraction (FUE) is commercially deployed (ARTAS, HAIRO). You cannot read the detection code, inspect the planning algorithm, retrain on your own data, or replicate the results.
2. **The science exists but is not integrated.** Follicle detection research (YOLO-OHFD, Hair-YOLO, the Fudan/Huashan dataset, ICANN 2023) and partially licensed datasets exist, but they are scattered, unreproduced, and mostly abandonware. No open benchmark, no model zoo, no community.
3. **Transparency is achievable here.** Unlike most surgical robotics, hair restoration is cosmetic, high-volume, and image-driven — the ideal beachhead for open surgical-AI practices.

## Scope

**In scope (now):** follicular-unit detection models, open dataset infrastructure and licensing hygiene, benchmark and evaluation harnesses, the public scalp-analyzer demo, educational content, graft-planning simulation.

**In scope (later, community-dependent):** donor-site mapping and allocation planning, robotic control interfaces, simulation environments for extraction/implantation, open hardware (needle mechanisms, stereo vision rigs) via partner labs.

**Out of scope (permanently):** clinical diagnosis or medical advice; patient-specific treatment; claims of safety or efficacy for any therapy; cell culture, cloning, or regenerative-medicine protocols (other communities, other regulatory regimes); anything that requires patient data without informed consent and IRB oversight.

## Principles

1. **Reproducible or it didn't happen.** Every model ships with its data, training config, and eval script.
2. **License hygiene is a feature.** Every contributed asset has a known license. CC-BY 4.0 or more permissive for data; Apache 2.0 for code; CERN-OHL for hardware.
3. **Honest metrics over hype.** We publish losses alongside wins. v0.1 is a baseline, not a breakthrough.
4. **Safety first.** Research and education only. No clinical use, no patient-doctor-patient channeling.
5. **Credit follows contribution.** Authorship, model cards, and READMEs name contributors. Bounties are paid where money exists.

## Ownership and structure

This is an open-source project, not a company. No token, no DAO, no commercial arm at this stage. If a commercial entity ever arises, its obligations to this project are contractual and the license grants remain perpetual.

Decision-making, roles, and the maintainer ladder: see `GOVERNANCE.md`.

## Amendment

Charter changes require: a written proposal (PR), 7-day comment period, and 2/3 approval of the Maintainer Council. Emergency safety actions may be taken immediately by any two-core members and announced retroactively.
