# AcmeLabCo Home Lab Charter

## 1. Purpose

The AcmeLabCo Home Lab is a controlled wireless and networking environment used to build practical competence in Wi-Fi fundamentals, administration, troubleshooting, design, and operations.

The primary learning objective is to reinforce the knowledge areas covered by the CWNA-109 curriculum through direct observation, measurement, configuration, and troubleshooting. A secondary objective is to practice as many RUCKUS Certified Wi-Fi Associate (RCWA) concepts as the available hardware and Unleashed platform permit.

The lab is not intended to reproduce every enterprise feature, controller architecture, authentication system, or large-scale deployment scenario. Where a curriculum objective cannot be reproduced faithfully, the limitation must be documented rather than implied away.

## 2. Current environment

The lab currently includes:

| Component | Function |
|---|---|
| Xfinity XB6 | Residential internet gateway and upstream NAT boundary |
| RUCKUS ICX switch | Wired switching, PoE, and available Layer 2/Layer 3 lab functions |
| RUCKUS R650 | Primary Unleashed access point |
| RUCKUS H350 access points | Secondary, room-level, and controlled lab wireless functions |
| Client devices | Association, roaming, security, performance, and troubleshooting tests |

The network also serves household production traffic. Availability and safety therefore take priority over experimentation.

## 3. Learning outcomes

The lab should develop the ability to:

1. Explain RF behavior, attenuation, reflection, absorption, interference, noise, and signal-to-noise ratio.
2. Relate channels, channel width, transmit power, data rates, modulation, and spatial streams to observed wireless behavior.
3. Understand 802.11 discovery, authentication, association, roaming, and client decision-making.
4. Configure and validate WLANs, AP roles, radio settings, security settings, and wired uplinks.
5. Perform basic site-survey and coverage measurements using repeatable methods.
6. Diagnose common Wi-Fi failures using evidence rather than guesswork.
7. Document changes, incidents, assumptions, results, and limitations in a professional format.
8. Develop operational familiarity with RUCKUS Unleashed and applicable ICX integration functions.

## 4. Scope

### In scope

- RF measurements and controlled coverage tests
- AP placement and orientation comparisons
- 2.4 GHz, 5 GHz, and available 6 GHz observations
- Channel planning, channel width, and transmit-power experiments
- Client discovery, association, roaming, and band-selection behavior
- WLAN creation and configuration
- WPA2/WPA3-Personal testing
- Guest-access and isolation tests where supported
- ICX port, PoE, VLAN, trunk, and management exercises where technically feasible
- Packet capture and protocol observation using lawful traffic generated within the lab
- Throughput, latency, loss, jitter, and Wi-Fi-calling observations
- Incident response, rollback, and post-change validation
- RUCKUS Unleashed administration and monitoring

### Conditionally in scope

These exercises require additional equipment, software, licensing, or architectural changes:

- Routed production VLANs with internet access
- 802.1X and enterprise authentication
- RADIUS integration
- Spectrum analysis using dedicated hardware
- Predictive design validation using commercial survey tools
- Large-scale controller, SmartZone, Cloud, or RUCKUS One workflows
- High-density and multi-floor enterprise capacity testing
- Advanced location services, DPSK at scale, and policy systems

### Out of scope

- Testing against networks or devices without authorization
- Deliberate disruption of household or neighboring networks
- Credential interception, password attacks, or evasion exercises
- Publishing secrets, serial numbers, public IP addresses, or personally identifying client data
- Representing simulated or planned configurations as implemented production state

## 5. Operating principles

### Production first

The home network supports real users. Every material change should have:

- a stated objective,
- a risk level,
- a defined test window,
- a rollback plan,
- success criteria, and
- post-change validation.

### Evidence over assumption

Observed facts must be separated from interpretation. A result should be supported by screenshots, sanitized configuration output, measurements, packet captures, or repeatable tests when practical.

### Change one variable at a time

When evaluating RF or configuration behavior, modify one principal variable at a time. Examples include channel width, transmit power, AP placement, security mode, or client location.

### Record limitations

A lab result is only valid within the tested environment. Conclusions should identify relevant constraints such as client hardware, firmware, residential-gateway limitations, floor plan, interference, and sample size.

### Protect sensitive information

Before publishing, remove or generalize:

- credentials and secrets,
- public IP addresses,
- serial numbers,
- client names and MAC addresses,
- exact household location data,
- unredacted configuration exports, and
- unnecessary internal addressing.

## 6. Documentation model

| Document type | Purpose |
|---|---|
| Lab charter | Defines purpose, scope, governance, and operating principles |
| Curriculum map | Connects planned exercises to CWNA and applicable RUCKUS concepts |
| Lab entry | Records an experiment, installation, discovery, or validation activity |
| Change record | Records a deliberate production configuration change |
| Incident report | Records an unexpected failure, impact, diagnosis, and recovery |
| Runbook | Provides a repeatable procedure for a recurring task |
| Diagram | Shows the current or planned architecture with status clearly identified |

## 7. Completion standard for a lab

A lab is complete when it includes:

1. Objective
2. Curriculum concept
3. Starting state
4. Required equipment and prerequisites
5. Procedure
6. Expected result
7. Actual result
8. Evidence
9. Analysis
10. Production impact
11. Rollback or restoration
12. Lessons learned
13. Follow-up actions

## 8. Success measures

Progress should be assessed by demonstrated capability rather than the number of files created. Useful measures include:

- percentage of planned labs completed,
- percentage of CWNA knowledge areas supported by hands-on work,
- ability to reproduce a test and obtain comparable results,
- reduction in unsupported conclusions,
- ability to diagnose an issue using a structured process,
- quality of rollback and validation practices, and
- ability to explain the technical result in clear language.

## 9. Curriculum references

This charter is aligned at a high level to the current CWNA-109 areas published by CWNP: RF technologies, antenna concepts, WLAN hardware and software, design and management, standards, 802.11 architecture, security, troubleshooting, and site surveys.

RUCKUS work is aligned to the vendor's stated certification purpose of installing, configuring, managing, and supporting RUCKUS solutions. Exact RCWA objective mapping should be updated when an authoritative current RCWA study guide or course-objective list is available.

## 10. Review cycle

Review this charter when:

- major equipment is added or removed,
- the upstream routing architecture changes,
- the target certification version changes,
- a new controller or authentication platform is introduced, or
- at least every six months during active study.
