# AcmeLabCo Home Lab

## Overview

Enterprise-style wireless and networking home lab used for hands-on learning, controlled testing, troubleshooting, and professional operations documentation.

Primary focus areas:

- CWNA-109 concepts and practical Wi-Fi fundamentals
- Applicable RUCKUS Certified Wi-Fi Associate (RCWA) concepts
- RUCKUS Unleashed administration
- RF observation, WLAN design, roaming, security, and troubleshooting
- ICX switching and VLAN foundations where the architecture permits
- Incident, change, and lab documentation

## Governing documents

- [Home Lab Charter](governance/HOME-LAB-CHARTER.md) — purpose, scope, safety, operating principles, and completion standards
- [CWNA-109 Lab Exercise Map](curriculum/CWNA-109-LAB-MAP.md) — planned exercises mapped to CWNA knowledge areas and applicable RUCKUS skills
- [Lab Log Standard and Index](lab-log/README.md) — what should be logged and how entries are published
- [VLAN Plan](vlan-plan.md) — target segmentation design and current implementation status

## Environment

| Device | Role | State |
|---|---|---|
| Xfinity XB6 | Internet gateway and upstream NAT boundary | Implemented |
| RUCKUS ICX switch | Core switching, PoE, and lab Layer 2/Layer 3 functions | Implemented; exact model to verify in inventory |
| RUCKUS R650 | Primary Unleashed access point | Implemented |
| RUCKUS H350 #1 | Secondary / lab AP | Implemented; role under refinement |
| RUCKUS H350 #2 | Expansion / isolated-lab AP | Planned or in testing |

> This is also a household production network. Lab changes must minimize disruption and include verification and rollback steps.

## VLAN Plan

| VLAN | Name | Purpose | State |
|---|---|---|---|
| 10 | MGMT | Infrastructure management | Planned / verify before use |
| 20 | HOME | Trusted household clients | Planned / verify before use |
| 30 | LAB | Isolated testing | Planned / verify before use |
| 40 | IOT | Smart-home devices | Planned / verify before use |
| 50 | GUEST | Guest access | Planned / verify before use |

The table is a target design, not proof that every VLAN is currently deployed. See `vlan-plan.md` and individual lab records for verified state.

## Repository Structure

```text
governance/     Purpose, scope, safety, and operating standards
curriculum/     Certification-aligned exercise roadmaps
configs/        Sanitized configuration examples
diagrams/       Logical and physical topology diagrams
incidents/      Service-impacting events and root-cause analysis
runbooks/       Repeatable operational procedures
rf-surveys/     Wireless measurements and findings
changelog/      Controlled production changes
Labs/           Structured training exercises
lab-log/        Chronological experiments, installations, and tests
.github/        Issue forms and GitHub Actions workflows
```

## Lab-log workflow

1. Record a meaningful lab action in ChatGPT or through the repository workflow.
2. Separate observed facts from interpretation.
3. Sanitize secrets and sensitive identifiers.
4. Publish the entry to a dedicated branch.
5. Open a draft pull request.
6. Review the rendered Markdown and diff.
7. Merge only after explicit approval.

See [`lab-log/README.md`](lab-log/README.md) for details.

## Public-repository safety

Do not publish credentials, API keys, Wi-Fi passwords, public IP addresses, unredacted configuration exports, serial numbers, VPN secrets, or personally identifying client information. See [`SECURITY.md`](SECURITY.md).
