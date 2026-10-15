# Security Policy

## Supported versions

Security fixes apply to the latest release of `follicle-detect`, `scalp-analyzer`, and `data-pipeline`.

## Reporting a vulnerability

**Do not open a public issue.** Report privately by DMing [@salik on X](https://x.com/salik),
or use GitHub's "Report a vulnerability" button on the repo (Security → Report) for anything
involving credentials or dependency supply chain.

Include in your report:

- affected repo and version
- reproduction steps
- impact assessment

Response within 72 hours. We follow coordinated disclosure: fix first, advisory after release.

## Special note: patient data in images

If you discover patient data inside any dataset, model artifact, or demo input, treat it as a security incident and report it immediately. Do not redistribute it. We will purge, document, and notify affected maintainers within 24 hours.

## Scope notes

This project contains no clinical pathways, no patient accounts, and no hosted PHI. The most likely security surface is supply-chain and dependency issues in the ML stack (ultralytics, gradio, roboflow). We pin dependencies and re-review release PRs.
