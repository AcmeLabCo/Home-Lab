# AcmeLabCo Home Lab

An evidence-driven networking and wireless engineering lab built around CompTIA Network+ N10-009 and the RUCKUS Certified Wi-Fi Associate (RCWA) blueprint.

This repository is the authoritative record of what is **planned**, **tested**, and **implemented**. It is both a learning system and an engineering portfolio: every material change should produce a lab record, sanitized evidence, verification, and a rollback plan.

## Start here

1. Read the [Home Lab Charter](governance/HOME-LAB-CHARTER.md) and [safety rules](SECURITY.md).
2. Follow the [12-module curriculum](curriculum/README.md).
3. Use the [lab catalog](Labs/README.md) and copy the appropriate file from [`templates/`](templates/).
4. Track objective coverage in the [progress tracker](curriculum/PROGRESS.md).
5. Publish completed work through the [lab-log workflow](lab-log/README.md).

## Current environment

| Device | Role | Verified state |
|---|---|---|
| Xfinity XB6 | Internet gateway, NAT, and current household edge | Implemented; limits routed lab VLANs |
| RUCKUS ICX 7150-C08P | Managed PoE switch and Layer 2/Layer 3 learning platform | Implemented |
| RUCKUS R650 | Primary Unleashed AP | Implemented |
| RUCKUS H350 #1 | Secondary/room AP and wired-edge lab platform | Implemented |
| RUCKUS H350 #2 | Additional roaming, placement, and isolated-test AP | Implemented |
| OPNsense | Future VLAN-aware firewall/router | Planned; not yet authoritative edge |

See the [hardware and objective map](curriculum/HARDWARE-MAP.md) for what each device can teach and what must be simulated.

> This is also a household production network. Availability and privacy take priority over experiments. Never represent a planned VLAN, firewall rule, or test result as implemented.

## Target learning path

| Phase | Modules | Outcome |
|---|---|---|
| Orient | 00 | Inventory, safety, baseline, and evidence standards |
| Build foundations | 01-03 | Models, protocols, addressing, Ethernet, switching, and routing |
| Build wireless skill | 04-06 | RF/802.11, RUCKUS design, Unleashed deployment and security |
| Operate securely | 07-09 | Services, monitoring, change control, hardening, and troubleshooting |
| Evolve the lab | 10 | Design and stage the OPNsense/VLAN migration |
| Prove readiness | 11 | Capstone, objective audit, and certification review |

## Certification coverage

- [CompTIA Network+ N10-009 objective map](curriculum/N10-009-OBJECTIVE-MAP.md)
- [2025 RCWA blueprint map](curriculum/RCWA-OBJECTIVE-MAP.md)
- [Preserved CWNA-109 lab map](curriculum/CWNA-109-LAB-MAP.md) for additional vendor-neutral wireless depth
- [Source register](curriculum/SOURCES.md) defining versions and mapping limitations

This curriculum is original lab guidance. It does not reproduce exam questions and does not replace official courseware or objectives.

## Target VLAN plan

| VLAN | Name | Purpose | State |
|---|---|---|---|
| 10 | MGMT | Infrastructure management | Planned |
| 20 | HOME | Trusted household clients | Planned |
| 30 | LAB | Isolated testing | Planned |
| 40 | IOT | Smart-home devices | Planned |
| 50 | GUEST | Guest access | Planned |

The XB6 does not provide the required return-route controls for the intended design. Internet-connected routed VLANs remain blocked until a VLAN-aware edge such as OPNsense is staged, validated, and approved. See [`vlan-plan.md`](vlan-plan.md).

## Repository map

```text
curriculum/   Learning sequence, certification maps, sources, and progress
Labs/         Guided exercises and lab catalog
templates/    Reusable lab, change, incident, runbook, survey, and quiz forms
governance/   Charter and operating rules
configs/      Sanitized configuration artifacts and backups
diagrams/     Logical, physical, and RF diagrams
incidents/    Service-impacting events and root-cause analyses
lab-log/      Chronological evidence of completed work
rf-surveys/   Measurement sets and wireless findings
runbooks/     Repeatable operational procedures
changelog/    Controlled production change records
```

## Definition of done

A completed lab has an objective, starting state, risk, prerequisites, procedure, expected and actual results, evidence, validation, rollback/restoration, analysis, reflection, objective mapping, and follow-up actions. A checkbox alone is not proof of competence.

## Public-repository safety

Do not publish credentials, Wi-Fi keys, public IP addresses, serial numbers, unredacted exports, exact household location data, or personally identifying client information. Use synthetic or generalized values in examples and review [`SECURITY.md`](SECURITY.md) before every commit.
