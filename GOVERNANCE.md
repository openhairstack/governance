# Governance

**Version 0.1**

## Participation ladder

| Role | How you get it | What you can do |
|---|---|---|
| **Participant** | Anyone. Join Discord, open issues, use the software. | Propose, discuss, report |
| **Contributor** | A merged PR (code, data, docs, labels) | Review others' PRs, claim bounties |
| **Maintainer** | 3+ merged PRs and nomination by two existing maintainers | Merge PRs, own a subproject, vote in the Council |
| **Core Maintainer** | Sustained contribution (6+ months) + Council election | Final say on subproject disputes, org-level decisions |

Roles currently in effect: see MAINTAINERS.md.

## Decision process

1. **Small stuff** (docs, bugfixes, dataset additions): lazy consensus — a maintainer merges after 72h with no blocking objection.
2. **Design decisions** (architecture, new subprojects, model releases): written proposal via RFC (short doc in `governance/rfcs/`), comment period 7 days, decided by maintainer vote (simple majority).
3. **Charter or license changes**: 2/3 of the Core Maintainer Council (see Charter).

Everything public, everything written. If it was decided in a call, it gets written into a doc within 48 hours.

## Maintainer Council

5 seats. Elects annually from the maintainer pool by approval voting. Responsibilities: admitting maintainers, resolving disputes, appointing the benevolent-dictator-for-life equivalent (none — deliberately), holding the keys to org settings and the Hugging Face org.

## Working groups

Self-organizing, no permission needed. Start one by opening a PR adding it to this file:
- **data** — dataset acquisition, licensing audit, labeling pipeline
- **models** — training, benchmarking, model releases
- **demo** — the public Space, UX, stability
- **outreach** — docs, talks, community, academic relationships

## Bounties

Money, when available, follows this policy: task published as an issue with `bounty` label → work submitted as PR → maintainer review → payment within 30 days of merge. Bounty amount is set by whoever funds that specific bounty; the Council adjudicates disputes.

## Scientific advisory

A non-governing Advisory Board of clinicians and researchers (target: 3–5 members) reviews safety claims and flag overreach. Advisory members do not control the project; they protect it from itself.

## Conflict of interest

Maintainers disclose affiliations relevant to datasets, models, or funding. Corporate sponsorship may not buy maintainer status, roadmap priority, or veto power. Ever.
