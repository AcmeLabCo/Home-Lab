# Hardware-to-Learning Map

| Component | Best hands-on uses | Certification alignment | Important limits |
|---|---|---|---|
| Xfinity XB6 | Trace gateway/NAT/DHCP/DNS; document consumer-edge constraints; baseline internet service | N10 1.2, 1.4, 2.1, 3.4, 5.3; RCWA upstream dependencies | No suitable static-return-route control for target routed VLANs; production household impact |
| ICX 7150-C08P | MAC learning, VLANs/tagging, STP, interfaces, PoE, LLDP, counters, management, backup | N10 2.2, 2.4, 3.1-3.2, 5.2-5.5; RCWA PoE/link/VLAN and controller integration | Exact commands/features depend on installed FastIron; limited ports/PoE versus enterprise scale |
| R650 | Primary Unleashed role, WLAN/radio/security/client visibility, RF and performance | N10 2.3, 3.2, 4.x, 5.4; broad RCWA Unleashed/RF work | Installed release and regulatory domain control features; no SmartZone/R1 proof |
| H350 #1 and #2 | Multi-AP adoption, room placement, roaming, overlap, mesh/uplink, wired-edge scenarios | N10 2.3, 5.4; RCWA deployment, design, optimization, troubleshooting | Residential density and client variety; feature parity must be verified |
| Future OPNsense | VLAN gateways, DHCP/DNS, NAT, firewall policy, logs, VPN, controlled faults | N10 2.1-2.2, 3.2-3.5, 4.x, 5.x; RCWA segmentation/security planning | Planned only; XB6 bridge mode and household rollback must be solved first |
| Client devices | Capability inventory, DHCP/DNS, packet capture, RF measurements, roaming and application tests | N10 1.x, 2.3, 3.4, 5.x; RCWA client behavior | Client-specific decisions cannot be generalized |

## Equipment gaps and safe substitutes

| Gap | Substitute now | Future enhancement trigger |
|---|---|---|
| Fiber optics/transceivers and test tools | Selection and fault scenarios; inspect known-safe samples if available | Add when fiber labs become a priority |
| Dedicated spectrum analyzer | Wi-Fi analyzer and AP telemetry; label inability to identify non-Wi-Fi emitters conclusively | Add for professional survey depth |
| RADIUS/PKI | Protocol diagrams and isolated virtual service | Add when enterprise-auth labs can be isolated and maintained |
| SmartZone/RUCKUS One | Official training/sandbox and comparison design | Add only with legitimate access/licensing |
| UPS/PDU/PoE tester/cable tester/toner | Documentation and simulated tool-selection tasks | Add based on troubleshooting frequency and safety value |

Hardware ownership never proves an objective. Evidence must show the configuration, observation, interpretation, verification, and restoration.
