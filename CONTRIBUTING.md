# Contributing to Open Hair Stack

Thanks for showing up. This project only works if the first 20 contributors have a good experience — here's how to make that likely.

## Ground rules

1. **Licensing.** Code is Apache 2.0, docs and data CC BY 4.0, hardware CERN-OHL. By contributing you agree your work is licensed the same way. We use the [Developer Certificate of Origin](https://developercertificate.org) — sign your commits (`git commit -s`).
2. **No patient data.** Ever. Do not upload photos, scans, or records of identifiable patients. The demo uses public datasets and consented/synthetic imagery only.
3. **No medical claims.** See the Charter. We publish research software.
4. **Everything reproducible.** If you add a model, ship the dataset pointer, config, and eval result. If you fix something, include the test or the manual repro steps.

## Ways to contribute (easiest first)

### 1. Label data (no coding)
We need accurate follicular-unit annotations. See `data-pipeline/ANNOTATION_GUIDE.md`, then pick an open item on the [bounties board](link).

### 2. Validate a dataset
Run `data-pipeline/scripts/validate_dataset.py` against any public follicle dataset and file an issue with the report. Finding broken annotations in existing datasets is genuinely valuable work.

### 3. Improve the demo
`scalp-analyzer` is Gradio. Good first issues are labeled `good first issue`.

### 4. Train and publish models
Use the Colab notebook in `follicle-detect/notebooks/`, publish results as an issue in the model-zoo tracker with your metrics.

### 5. Write the benchmark
`follicle-detect/benchmark/` needs a clean, CI-runnable evaluation on all license-clean datasets. This is the highest-leverage code contribution right now.

## Pull request checklist

- [ ] Commits are signed off (`-s`)
- [ ] Tests pass / manual steps documented
- [ ] Docs updated if behavior changed
- [ ] New data includes license + provenance in `DATASETS.md`
- [ ] You've read the Charter (it's short)

## Setup (Python 3.10+)

```bash
git clone https://github.com/openhairstack/<repo>.git
cd <repo>
python -m venv .venv && source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Heavy ML training runs on free cloud GPUs — don't do it on a laptop. See `follicle-detect/notebooks/train_colab.ipynb`.

## Code style

- Python: `ruff` for lint, `black` for format. Run `make lint` where a Makefile exists.
- Keep commits small. Write the "why" in the commit message, not the "what".
- No secrets, tokens, or model weights > 100MB committed to git — use Git LFS or Hugging Face.

## Getting help

Discord `#contributing` is the fastest channel once it's live. Until then — or if you don't do chat — DM [@salik on X](https://x.com/salik) or open a discussion in this repo. Nothing here is obvious to everyone — ask early.

## Recognition

Every merged contributor is added to the repo README's contributors section. Model release cards credit contributors by name. If money ever shows up, contributors are paid before infrastructure.
