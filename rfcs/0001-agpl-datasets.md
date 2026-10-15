# RFC 0001 — AGPL datasets (Ultralytics "scalps")

- **Status:** open for comment — no decision yet; nothing AGPL-derived ships in any release
- **Date:** 2026-10
- **Tracking:** open an issue titled `RFC 0001 discussion` in this repo

## Context

The Ultralytics "scalps" dataset (~4,005 images, 59k+ annotations, AGPL-3.0) is the largest
publicly available follicle dataset we know of. AGPL on a *dataset export* is unusual. The
practical reading: the license likely extends to its label set and to any published release
that mixes its images with ours, which would make that combined release AGPL — changing the
permissions for every downstream user.

## The question

Do we (a) exclude it, (b) use it for internal benchmarking only, or (c) merge it into a
separately-labeled AGPL release track?

## Options

1. **Exclude.** Releases stay strictly CC BY 4.0. (Default until this RFC is decided.)
2. **Benchmark-only.** Evaluate models on it internally; publish aggregate scores and model
   cards, never images or mixed labels.
3. **Separate AGPL track.** A clearly-labeled `follicle-agpl-*` release for users who accept
   AGPL terms.

## Considerations

- The Charter commits to license hygiene and freely-redistributable releases; mixing licenses
  silently would violate both.
- 5–6× more data is a big lever for v0.2+; excluding is not free.
- Consulting a licensing professional before any merge is mandatory for any option above.

## Decision

Not yet decided. Comment period: 7 days from the first comment on the tracking issue.
