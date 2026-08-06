# Lab Log

This directory contains chronological records of home-lab experiments, installations, architecture discoveries, validation work, and lessons learned.

## What belongs here

Create an entry when work:

- changes the environment,
- reveals a technical constraint,
- produces a reusable lesson,
- affects production service,
- requires meaningful troubleshooting,
- changes a future design decision, or
- demonstrates a technical skill.

Routine checks with no meaningful result do not require separate entries. Include them as steps within a larger entry when relevant.

## Entry standard

Each entry should separate directly observed facts from interpretation and include:

- Objective
- Starting state
- Actions performed
- Validation
- Result
- Observations
- Analysis
- Production impact
- Rollback plan
- Lessons learned
- Follow-up actions

Start from [`templates/lab-template.md`](../templates/lab-template.md) for new work. Existing historical records do not need to be rewritten, but their limitations and confidence notes must remain visible.

## Publishing workflow

1. Capture the completed work and evidence.
2. Remove credentials, secrets, public IP addresses, serial numbers, client identifiers, and unnecessary sensitive topology detail.
3. Draft the entry on a dedicated branch.
4. Open a draft pull request.
5. Review the rendered Markdown and file diff.
6. Merge only after explicit approval.

## Index

### 2026

- [ICX Unleashed adoption troubleshooting](2026/2026-07-30-icx-unleashed-adoption-troubleshooting.md)
- [XB6 upstream routing limitation for multi-VLAN design](2026/2026-07-30-xb6-upstream-routing-limitation.md)
