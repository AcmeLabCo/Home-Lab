# CWNA-109 Home Lab Exercise Map

## Purpose

This document is the working lab roadmap for the AcmeLabCo Home Lab. It maps practical exercises to the major knowledge areas published for CWNA-109 and identifies RUCKUS Unleashed or ICX skills that can be practiced at the same time.

This is not an official CWNP objective document and does not replace the CWNA study guide. It is a practical interpretation designed around the equipment available in this home lab.

## Status definitions

| Status | Meaning |
|---|---|
| Planned | Defined but not started |
| In progress | Work has begun but evidence or validation is incomplete |
| Completed | Procedure, evidence, result, and lessons are documented |
| Blocked | Requires equipment, licensing, architecture, or software not currently available |
| Optional | Useful enrichment but not required for the core sequence |

## Lab sequence

### Phase 1 — Baseline and observation

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| WL-001 | Document physical and logical topology | WLAN hardware, network architecture, design and management | Unleashed roles, AP inventory, ICX integration | Sanitized topology diagram and inventory | Planned |
| WL-002 | Establish a known-good network baseline | Troubleshooting methodology, WLAN management | Dashboard health, client count, AP status, alarms | Baseline table and screenshots | Planned |
| WL-003 | Inventory client capabilities | Standards, bands, channel widths, spatial streams, security support | Client details in Unleashed | Sanitized client capability matrix | Planned |
| WL-004 | Record current RF environment | RF technologies, channels, interference, noise | Channel utilization and neighboring WLAN views | RF snapshot by location | Planned |
| WL-005 | Measure RSSI and SNR by room | RF propagation, received signal strength, noise floor | AP radio statistics | Floor-plan measurement table | Planned |

### Phase 2 — RF fundamentals

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| RF-001 | Distance-versus-signal test | Free-space path loss, attenuation, RSSI | AP/client monitoring | RSSI measurements at fixed distances | Planned |
| RF-002 | Material attenuation comparison | Absorption and attenuation | AP monitoring | Before/after measurements through drywall, doors, or floors | Planned |
| RF-003 | Reflection and multipath observation | Reflection, multipath, constructive/destructive interference | Client-rate and signal observations | Measurements at small location increments | Planned |
| RF-004 | 2.4 GHz versus 5 GHz coverage | Frequency-dependent propagation, channel availability | Radio-band configuration and client association | Coverage and throughput comparison | Planned |
| RF-005 | 5 GHz versus available 6 GHz behavior | Band characteristics, regulatory availability, client support | 6 GHz-capable AP/client configuration where available | Coverage and capability comparison | Blocked until confirmed hardware/client support |
| RF-006 | Channel-width comparison | 20/40/80 MHz operation, noise and contention tradeoffs | Radio configuration | Throughput, latency, retry, and coverage table | Planned |
| RF-007 | Transmit-power comparison | Link budget, cell size, asymmetric links | Radio power configuration | RSSI, roaming, and performance results | Planned |
| RF-008 | Co-channel contention observation | CCI, airtime sharing, channel reuse | Channel assignment and utilization views | Utilization and performance comparison | Planned |
| RF-009 | Adjacent-channel interference demonstration | ACI and channel planning | Manual channel configuration | Controlled comparison where legal and non-disruptive | Optional |

### Phase 3 — Antennas and AP placement

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| ANT-001 | Compare AP mounting locations | Antenna patterns, placement, coverage | R650/H350 deployment considerations | Heat-map-style measurement table | Planned |
| ANT-002 | Compare AP orientation | Polarization and radiation-pattern effects | AP mounting/orientation | Signal and throughput comparison | Planned |
| ANT-003 | Observe client orientation effects | Polarization mismatch and client antenna behavior | Client monitoring | Repeated measurements by orientation | Planned |
| ANT-004 | Identify coverage overlap | Cell boundaries and roaming design | Multi-AP Unleashed deployment | Overlap measurements and roaming observations | Planned |

### Phase 4 — 802.11 operations and client behavior

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| MAC-001 | Capture beacon and probe traffic | Management frames, discovery, information elements | WLAN and radio configuration | Sanitized packet capture and frame notes | Planned |
| MAC-002 | Observe authentication and association | 802.11 state transitions and management frames | Client connection workflow | Packet sequence diagram | Planned |
| MAC-003 | Compare passive and active scanning behavior | Discovery and scanning | Client/AP event logs | Packet capture and timing observations | Planned |
| MAC-004 | Observe data rates and rate adaptation | Modulation, coding, data rates, environmental effects | Client link-rate statistics | Movement-versus-rate table | Planned |
| MAC-005 | Measure airtime impact of a weak client | Airtime fairness, low-rate client effects | Airtime/client statistics | Controlled performance comparison | Planned |
| MAC-006 | Roaming walk test | Roaming, reassociation, client decision-making | Multi-AP roaming and event logs | Timestamped roaming record | Planned |
| MAC-007 | Band-steering observation | Client choice, band capabilities, steering limitations | Unleashed band steering | Association results across repeated trials | Planned |
| MAC-008 | Minimum data-rate experiment | Cell size, legacy rates, design tradeoffs | WLAN advanced settings if exposed | Coverage and association results | Optional |
| MAC-009 | Wi-Fi calling continuity test | Mobility, latency, jitter, loss, roaming | Multi-AP tuning and client monitoring | Call continuity and roam timeline | Planned |

### Phase 5 — WLAN configuration and security

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| SEC-001 | Create a dedicated lab SSID | WLAN configuration and service-set concepts | Unleashed WLAN creation | Sanitized configuration summary | Planned |
| SEC-002 | Compare open, WPA2-Personal, and WPA3-Personal behavior | Authentication, encryption, compatibility | Unleashed security configuration | Connection and compatibility matrix | Planned |
| SEC-003 | Test protected management frames | PMF concepts and compatibility | PMF settings where exposed | Client support and connection results | Planned |
| SEC-004 | Guest isolation validation | Client isolation and segmentation concepts | Guest WLAN/client isolation | Connectivity test matrix | Planned |
| SEC-005 | Password and configuration hygiene review | Security operations and key management | Unleashed administration | Security checklist without secrets | Planned |
| SEC-006 | 802.1X/RADIUS authentication | Enterprise authentication, EAP, AAA | RUCKUS WLAN integration | Authentication flow and packet evidence | Blocked pending RADIUS environment |
| SEC-007 | Dynamic or role-based access policy | Segmentation and access control | RUCKUS policy features | Policy test matrix | Blocked pending platform/features |

### Phase 6 — Wired integration and VLAN foundations

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| NET-001 | Validate AP Ethernet links and PoE | WLAN infrastructure, Ethernet integration, PoE | ICX port and PoE monitoring | Port status and power table | Planned |
| NET-002 | Identify access versus trunk behavior | 802.1Q concepts and WLAN-to-VLAN mapping | ICX VLAN and tagged/untagged ports | Sanitized lab configuration | Planned in isolated environment |
| NET-003 | Build an isolated Layer 2 lab VLAN | Segmentation and broadcast domains | ICX VLAN creation | Connectivity matrix | Planned |
| NET-004 | Map a lab SSID to a VLAN | WLAN/VLAN integration | Unleashed SSID VLAN setting and ICX trunking | Client addressing and isolation tests | Planned; internet access not assumed |
| NET-005 | Test inter-VLAN routing on the ICX | Layer 3 support concepts adjacent to WLAN operations | ICX virtual interfaces and routing | Route and connectivity matrix | Planned in controlled lab |
| NET-006 | Validate XB6 upstream-routing limitation | Routing boundary, NAT, return path, design constraints | ICX versus residential gateway roles | Existing architecture-discovery entry | Completed |
| NET-007 | Design future routed VLAN architecture | WLAN design, segmentation, resiliency considerations | Edge router/firewall plus ICX design | Planned topology and migration steps | Planned |

### Phase 7 — Site survey and design

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| SUR-001 | Define application requirements | Capacity, coverage, roaming, voice requirements | WLAN service requirements | Requirements table | Planned |
| SUR-002 | Create a basic floor plan | Survey preparation and documentation | AP placement planning | Sanitized floor plan | Planned |
| SUR-003 | Perform a manual coverage survey | RSSI, SNR, noise, coverage thresholds | R650/H350 measurements | Measurement grid | Planned |
| SUR-004 | Validate AP placement changes | Post-installation validation | AP placement and radio monitoring | Before/after results | Planned |
| SUR-005 | Evaluate channel reuse and overlap | Channel planning, CCI, roaming boundaries | Channel assignment and Radio Resource Management observations | Channel map | Planned |
| SUR-006 | Capacity test with multiple clients | Airtime, contention, application requirements | Client and AP utilization | Concurrent-client performance table | Planned |
| SUR-007 | Voice-oriented validation | Roaming, latency, jitter, packet loss | Wi-Fi calling and AP event monitoring | Voice test report | Planned |
| SUR-008 | Spectrum analysis survey | Non-Wi-Fi interference and spectral signatures | External spectrum-analysis tooling | Spectrum captures | Blocked pending dedicated tool |

### Phase 8 — Troubleshooting and operations

| ID | Exercise | CWNA concepts | RUCKUS / platform concepts | Evidence | Status |
|---|---|---|---|---|---|
| OPS-001 | Develop a layered troubleshooting workflow | Troubleshooting methodology | Unleashed, ICX, client, and packet evidence | Runbook | Planned |
| OPS-002 | Diagnose incorrect WLAN credentials | Authentication failure and client troubleshooting | Unleashed event logs | Failure/recovery lab entry | Planned |
| OPS-003 | Diagnose DHCP failure | IP services as a WLAN dependency | WLAN/VLAN/ICX path validation | Packet capture and fault tree | Planned |
| OPS-004 | Diagnose DNS-versus-connectivity failure | Layered troubleshooting | Client and gateway validation | Test matrix | Planned |
| OPS-005 | Diagnose weak signal versus interference | RSSI, SNR, noise, retries, channel utilization | Radio/client statistics | Comparative diagnosis report | Planned |
| OPS-006 | Diagnose sticky-client behavior | Roaming and client decisions | AP event logs and radio tuning | Roaming observations | Planned |
| OPS-007 | Document ICX Unleashed adoption failure | Discovery, authentication, management-plane troubleshooting | Unleashed ICX integration | Existing troubleshooting entry | Completed |
| OPS-008 | Practice configuration backup and restore | Change management and recovery | Unleashed and ICX backup procedures | Runbook and restore validation | Planned |
| OPS-009 | Practice controlled firmware review | Compatibility, release management, rollback risk | RUCKUS firmware inventory and release assessment | Upgrade decision record | Planned |
| OPS-010 | Build a post-change validation checklist | WLAN operations and troubleshooting | Dashboard, clients, radios, switch, internet, voice | Reusable checklist | Planned |

## Coverage by CWNA knowledge area

| CWNA knowledge area | Primary labs |
|---|---|
| RF technologies | RF-001 through RF-009; WL-004; WL-005 |
| Antenna concepts | ANT-001 through ANT-004 |
| WLAN hardware and software | WL-001 through WL-003; NET-001; SEC-001 |
| Design, installation, and management | SUR-001 through SUR-007; OPS-008 through OPS-010 |
| Wireless standards and organizations | WL-003; MAC-001; MAC-004; SEC-002 |
| 802.11 network architecture | MAC-001 through MAC-009; NET-004 |
| WLAN security | SEC-001 through SEC-007 |
| Troubleshooting | OPS-001 through OPS-010; NET-006 |
| Site surveys | SUR-001 through SUR-008 |

## Recommended execution order

1. WL-001 through WL-005
2. RF-001 through RF-007
3. ANT-001 through ANT-004
4. MAC-001 through MAC-009
5. SEC-001 through SEC-005
6. NET-001 through NET-005
7. SUR-001 through SUR-007
8. OPS-001 through OPS-010

Some labs should be repeated after major topology, firmware, or AP-placement changes.

## Mapping limitations

- A residential environment cannot faithfully reproduce enterprise density, scale, user diversity, or RF complexity.
- Client behavior is vendor-specific; one client result must not be generalized to all clients.
- The XB6 currently limits clean internet-connected routed VLAN deployment.
- Dedicated spectrum analysis, enterprise AAA, and controller-scale workflows require additional resources.
- RUCKUS product interfaces and available features vary by model and software release.
- This legacy map keeps RCWA references intentionally high-level. Use `RCWA-OBJECTIVE-MAP.md` for the authoritative 2025 blueprint mapping.

## Sources and version control

- CWNA target: CWNA-109, released September 30, 2023, as identified on the official CWNP certification page.
- RUCKUS target: the 2025 RCWA blueprint, mapped in `RCWA-OBJECTIVE-MAP.md`; this file remains supplemental CWNA-oriented practice.

Review this map whenever the CWNA exam version, RUCKUS curriculum, firmware, or lab architecture changes.
