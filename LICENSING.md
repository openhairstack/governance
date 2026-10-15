# Licensing

## Our choice

| Asset type | License | Why |
|---|---|---|
| Source code (all repos) | **Apache 2.0** | Permissive, patent grant, standard for scientific software |
| Documentation, guides, educational content | **CC BY 4.0** | Attribution-preserving, reuse-friendly |
| Datasets created by this project | **CC BY 4.0** | The license hygiene standard the field lacks |
| Model weights trained by this project | **Apache 2.0** | Treated as software artifacts we publish |
| Hardware (future) | **CERN-OHL-2** | Mature OSHW license with strong reciprocity variants |

## The rule

Everything merged into these repos must be compatible with the above. If you pull from a source with a stricter license, document it in the affected repo's README and do not merge it until the provenance is clean.

## Third-party picture (known, tracked)

- **Ultralytics YOLO** — the training/inference library we build on — is **AGPL-3.0**. Using it as a tool is fine; our training scripts, configs, and our weights are our own. If you derive code from Ultralytics' source, your derived code becomes AGPL. Prefer calling it as a library.
- **Pretrained backbone weights** (`yolo11n.pt` etc.) are AGPL-3.0 when downloaded from Ultralytics. Our published *fine-tuned* weights are Apache 2.0; the training run provenance is documented in the model card.
- **Roboflow datasets we use today** are **CC BY 4.0** (see `data-pipeline/DATASETS.md` — each entry lists its license and the attribution required).
- **YOLO-OHFD** (prior open work): license unclear/absent; we treat it as prior art only and reimplement from the open-access paper.
- **Fudan hair follicle dataset** (ICANN 2023): research-use, request-based. Referenced for benchmarking, not redistributed.

## What we do NOT do

No Contributor License Agreement friction: we use the Developer Certificate of Origin (commit sign-off), which keeps the project's rights simple and permissive. Contributors keep their copyright.

## Clinical/regulatory note

Apache 2.0 includes an "as is" warranty disclaimer. Additionally: this software is not a medical device, is not FDA/CE cleared, and must not be used for diagnosis or clinical decision-making. That is a licensing-and-safety boundary, not just a legal one.
