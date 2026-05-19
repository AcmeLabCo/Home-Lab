# Ruckus Networking Homelab

## Overview

Enterprise-style networking homelab focused on:

- CompTIA Network+
- Ruckus RCWA
- Wireless troubleshooting
- VLAN design
- Wi-Fi calling optimization

---

# Hardware

| Device | Purpose |
|---|---|
| Ruckus ICX Switch | Core switching |
| AP-1 | Main floor Wi-Fi |
| AP-2 | Upstairs Wi-Fi |
| AP-3 | Garage/lab Wi-Fi |

---

# Current Goals

- Improve Wi-Fi roaming
- Practice enterprise troubleshooting
- Learn VLAN segmentation
- Document network operations professionally

---

# VLAN Plan

| VLAN | Name | Purpose |
|---|---|---|
| 10 | MGMT | Infrastructure |
| 20 | HOME | User devices |
| 30 | LAB | Testing |
| 40 | IOT | Smart devices |
| 50 | GUEST | Guest Wi-Fi |

---

# Repository Structure

```text
configs/
diagrams/
incidents/
runbooks/
rf-surveys/
changelog/
```
