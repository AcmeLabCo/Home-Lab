# CompTIA Network+ N10-009 Objective Map

Source of record: CompTIA Network+ N10-009 Exam Objectives version 4.0. Domain weights are 23% Networking Concepts, 20% Network Implementation, 19% Network Operations, 14% Network Security, and 24% Network Troubleshooting.

`Direct` means the installed lab can produce hands-on evidence. `Partial` means concepts beyond the hardware require diagrams, packet analysis, virtual systems, or scenario work. Completion requires the official sub-bullets, not merely this summary.

| Objective | Practical interpretation | Modules | Primary evidence | Coverage |
|---|---|---:|---|---|
| 1.1 OSI model | Locate protocols, addresses, devices, and symptoms by layer | 01, 09 | Annotated packet trace and fault tree | Direct |
| 1.2 Appliances/applications/functions | Compare router, switch, firewall, IDS/IPS, proxy, storage, AP/controller, VPN, QoS, TTL | 01, 10 | Function matrix and topology | Partial |
| 1.3 Cloud concepts/connectivity | NFV, VPC controls/gateways, connectivity, deployment/service models, elasticity and tenancy | 01, 11 | Cloud design scenario | Partial |
| 1.4 Ports/protocols/traffic | Recognize official port list, IP protocols, and unicast/multicast/anycast/broadcast | 01, 02 | Packet capture and port matrix | Direct |
| 1.5 Media/transceivers | Compare wireless, copper, fiber, speeds, ratings, transceivers, and connectors | 01, 03 | Media inspection and selection scenario | Partial |
| 1.6 Topologies/architectures/types | Mesh, hybrid, star, spine-leaf, point-to-point, hierarchical/collapsed core, traffic flows | 01, 05 | Current/enterprise comparison diagrams | Partial |
| 1.7 IPv4 addressing | Public/private, APIPA, loopback, RFC1918, VLSM/CIDR, address classes | 02 | Timed subnet worksheet and address plan | Direct |
| 1.8 Modern environments | SDN/SD-WAN, VXLAN, ZTA/SASE/SSE, IaC/source control, IPv6 migration | 01, 02, 10 | Architecture comparison and repository workflow | Partial |
| 2.1 Routing | Static/dynamic protocols, route selection, NAT/PAT, FHRP/VIP, subinterfaces | 03, 10 | Route analysis and target edge design | Partial |
| 2.2 Switching | VLAN/SVI, interface/VLAN settings, 802.1Q, aggregation, STP, MTU | 03, 10 | Isolated ICX configuration and test matrix | Direct |
| 2.3 Wireless | Channels/bands, SSID/BSSID/ESSID, network types, WPA2/3, guest, authentication, antennas, AP types | 04-06 | RF survey, frame capture, WLAN/security matrix | Direct |
| 2.4 Physical installations | MDF/IDF/rack/cabling, airflow/locks, UPS/PDU/load/voltage, environment | 00, 03 | Physical diagram and installation checklist | Partial |
| 3.1 Processes/procedures | Documentation, inventory/IPAM/SLA/survey, lifecycle, change/configuration management | 00, 07 | Repository artifacts, backup and change record | Direct |
| 3.2 Monitoring | SNMP, flow, capture, baselines, alerts, logs/SIEM, API, mirroring, discovery/analysis/monitoring | 07, 09 | Baseline and telemetry plan | Partial |
| 3.3 Disaster recovery | RPO/RTO/MTTR/MTBF, sites, HA modes, tabletop and validation tests | 00, 07 | Recovery tabletop | Partial |
| 3.4 IPv4/IPv6 services | DHCP/SLAAC, DNS records/zones/security/encrypted DNS, hosts, NTP/PTP/NTS | 02, 07 | DORA/DNS capture and service worksheet | Direct/partial |
| 3.5 Access/management | Site/client VPN, tunnel choices, SSH/GUI/API/console, jump host, in/out-of-band | 07, 08 | Secure-management matrix | Partial |
| 4.1 Security concepts | Encryption/PKI/IAM/AAA, physical/deception, CIA/risk/compliance, segmentation | 08 | Threat model and control matrix | Partial |
| 4.2 Attacks/impact | DoS, VLAN/MAC/ARP/DNS attacks, rogue DHCP/AP/evil twin, on-path, social engineering, malware | 08 | Safe threat-analysis scenarios | Partial |
| 4.3 Defenses/solutions | Hardening, NAC/port security/802.1X/MAC filters, key management, ACL/filtering, zones | 06, 08, 10 | Hardening review and proposed policy tests | Partial |
| 5.1 Methodology | Identify, theorize, test, plan, implement/escalate, verify/prevent, document | 09 | Completed fault-injection records | Direct |
| 5.2 Cabling/interfaces | Cable/signal/termination/TX-RX faults, counters/status, PoE, transceivers | 03, 09 | Interface and PoE diagnostics | Partial |
| 5.3 Network services | STP/VLAN/ACL, routes/default route, address pool/gateway/IP/mask faults | 02, 03, 09 | Fault-injection matrix | Direct |
| 5.4 Performance | Congestion/bottleneck/bandwidth, latency/loss/jitter, interference/coverage/roaming | 04, 06, 09 | Repeated RF/performance measurements | Direct |
| 5.5 Tools/protocols | Official software, hardware, discovery, and device-command tool list | 01-03, 09 | Tool-selection scenarios and real outputs | Partial |

## Coverage audit rule

For each objective, maintain three separate claims in `PROGRESS.md`: **Know** (teach all official sub-bullets), **Do** (perform what the environment permits), and **Prove** (link sanitized evidence). A `Partial` hardware row can still be exam-ready when theory and scenario work cover the remaining sub-bullets, but it must not be described as hands-on experience.
