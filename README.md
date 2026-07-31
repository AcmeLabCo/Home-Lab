# AcmeLabCo Home Lab

## Overview

Enterprise-style networking home lab used for hands-on learning, controlled testing, troubleshooting, and professional operations documentation.

Primary focus areas:

- CompTIA Network+
- Ruckus wireless administration
- VLAN design and segmentation
- Wi-Fi roaming and calling optimization
- Incident, change, and lab documentation

## Environment

| Device | Role | State |
|---|---|---|
| Xfinity XB6 | Internet gateway | Implemented |
| Ruckus ICX 7650 | Core switching | Implemented |
| Ruckus R650 | Primary Unleashed AP | Implemented |
| Ruckus H350 #1 | Secondary / lab AP | Implemented; role under refinement |
| Ruckus H350 #2 | Expansion / isolated-lab AP | Planned or in testing |

> This is also a household production network. Lab changes must be designed to minimize disruption and include verification and rollback steps.

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

1. Record a lab action in ChatGPT or open the **Lab Log Entry** issue form.
2. Sanitize secrets and sensitive identifiers.
3. Publish the entry to a dedicated branch.
4. Open a draft pull request.
5. Review the rendered Markdown and diff.
6. Merge only after explicit approval.

See [`lab-log/README.md`](lab-log/README.md) for details.

## Public-repository safety

Do not publish credentials, API keys, Wi-Fi passwords, public IP addresses, unredacted configuration exports, serial numbers, VPN secrets, or personally identifying client information. See [`SECURITY.md`](SECURITY.md).
