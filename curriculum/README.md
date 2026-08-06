# Integrated Network+ and RCWA Curriculum

## Purpose

This 12-module path combines the complete CompTIA Network+ N10-009 objective structure with the current RCWA exam blueprint and the capabilities of the AcmeLabCo home lab. It deliberately separates three kinds of learning:

- **Know:** explain a concept without the interface in front of you.
- **Do:** configure, measure, or troubleshoot it safely.
- **Prove:** publish sanitized evidence and explain why the result is valid.

Estimated core effort is 120-160 hours. RCWA topics that require SmartZone, RUCKUS One, Cloudpath, licensing, clusters, data planes, APIs, or enterprise scale are studied and simulated; they are never claimed as hands-on Unleashed experience.

## How to run a module

1. Read the listed sections of the official objective documents and the relevant official product documentation.
2. Define every vocabulary term in your own words.
3. Complete the whiteboard prompt before touching equipment.
4. Perform the required labs during a safe window.
5. Save a completed lab record with sanitized evidence in `lab-log/`.
6. Answer the knowledge check without notes and explain each answer.
7. Update `PROGRESS.md` only after the evidence exists.

Passing a module requires at least 80% on its knowledge check, successful verification for all required labs, and a clear teach-back. Rework weak areas; do not average away a failed practical skill.

## Sequence

### Module 00 - Orientation, safety, and baseline (4-6 hours)

**Objectives:** Establish the repository workflow, verify inventory, diagram the current state, capture a known-good baseline, and distinguish observed, inferred, planned, and simulated claims.

**Read:** Charter; repository safety; N10-009 3.1; RCWA management and troubleshooting blueprint; device release notes and support status.

**Vocabulary:** baseline, golden configuration, rollback, RPO, RTO, MTTR, asset inventory, physical diagram, logical diagram, evidence, sanitization.

**Concept lesson:** A reliable lab starts with state and boundaries. A diagram is a model, not proof; a backup is useful only if restore steps and sensitive handling are understood. Production safety requires a hypothesis, change window, success criteria, stop conditions, and rollback.

**Whiteboard:** Draw the physical path from ISP to a wireless client and the logical responsibilities of XB6, ICX, Unleashed master, AP, DHCP, DNS, and NAT. Mark every unverified assumption.

**Labs:** `001-network-discovery`; create physical and logical diagrams; capture a sanitized baseline; test the lab-record template.

**Verify:** Every device has a role and state; diagrams agree with observed links; no secret appears in the staged evidence; a second reader can distinguish current from target state.

**Knowledge check:** Why is a configuration export not automatically safe to commit? What is the difference between RTO and RPO? Which artifact proves a port is up? When must a rollback begin?

**Reflection:** Which assumption in the original topology was wrong or unverified, and how did evidence change it?

### Module 01 - Models, traffic, protocols, and network types (10-12 hours)

**Objectives:** N10-009 1.1-1.6 and relevant 1.8; explain encapsulation, appliances, cloud models, ports/protocols, media, topologies, and traffic flows.

**Read:** Official N10-009 objectives 1.1-1.6 and 1.8; product data sheets for the installed APs and switch.

**Vocabulary:** OSI, PDU, frame, packet, segment, TCP, UDP, ICMP, unicast, multicast, broadcast, anycast, north-south, east-west, NFV, VPC, SASE, VXLAN.

**Concept lesson:** Follow data as headers are added and removed. Separate a device's physical identity from its function: an XB6 combines routing, switching, firewall, DHCP, DNS proxy, Wi-Fi, and NAT. Compare copper, fiber, and RF by medium, reach, interference, connector, and transceiver constraints.

**Whiteboard:** Follow a DNS lookup and HTTPS request from a Wi-Fi client to the internet. Label addresses, ports, protocols, and OSI layers at each hop.

**Labs:** `002-follow-a-packet`; inspect ARP, DNS, TCP, TLS, DHCP, and ICMP using lawful client-generated traffic; produce a protocol/port matrix.

**Verify:** Identify each captured exchange, its endpoints, transport, purpose, and failure symptom. Explain where NAT changes the packet and where 802.11 becomes 802.3.

**Knowledge check:** TCP versus UDP tradeoff? Broadcast versus multicast scope? Why can ping succeed while HTTPS fails? Which cloud model gives the customer most OS control?

**Reflection:** Which layer model was most useful during the trace, and where did it oversimplify reality?

### Module 02 - IPv4, IPv6, and core services (12-16 hours)

**Objectives:** N10-009 1.7, IPv6 portion of 1.8, 1.4, and 3.4; calculate subnets and explain DHCP, DNS, and time services.

**Read:** Official objectives 1.4, 1.7, 1.8, 3.4; current XB6 DHCP/DNS documentation.

**Vocabulary:** CIDR, VLSM, RFC1918, APIPA, loopback, SLAAC, dual stack, NAT64, lease, reservation, exclusion, relay, A, AAAA, CNAME, MX, PTR, DNSSEC, DoH, DoT, NTP.

**Concept lesson:** Address plans encode boundaries. Subnetting must answer network, broadcast, usable range, and host capacity. DHCP supplies configuration; DNS maps names; time underpins logs and certificates. A default gateway is a routing choice, not merely another address.

**Whiteboard:** Design subnets for the five planned VLANs with growth margin. Show DHCP scope, exclusions, gateway, DNS, and why the XB6 cannot return traffic to them today.

**Labs:** `005-dhcp`; perform subnet drills; observe DHCP DORA and DNS recursion; compare configured versus effective client data; document IPv6 state without disabling it.

**Verify:** Score 90% on mixed CIDR/VLSM exercises; explain every DHCP option observed; distinguish DNS failure from routing failure.

**Knowledge check:** What creates APIPA? Why reserve outside or exclude within a scope? Forward versus reverse lookup? When is a DHCP relay required?

**Reflection:** Which address-plan choice will simplify the future OPNsense migration?

### Module 03 - Ethernet, switching, routing, and PoE (14-18 hours)

**Objectives:** N10-009 2.1, 2.2, 2.4, 5.2, 5.3, and device-command portion of 5.5; build evidence on ICX 7150-C08P.

**Read:** Official objectives; the installed FastIron release documentation; ICX 7150 hardware guide.

**Vocabulary:** CAM/MAC table, VLAN, SVI, tagged, untagged, native VLAN, 802.1Q, STP/RSTP, LACP, MTU, duplex, route, prefix, metric, administrative distance, NAT, PAT, PoE budget.

**Concept lesson:** A switch forwards within a Layer 2 domain by learned MAC address; a router forwards between IP networks by longest-prefix selection. VLANs create logical broadcast boundaries. Loops are dangerous before IP is involved. PoE negotiation and budget are physical dependencies for wireless service.

**Whiteboard:** Trace same-VLAN and inter-VLAN traffic. Draw tagged AP uplinks and an untagged client port. Predict MAC, ARP, VLAN, and route-table entries.

**Labs:** `003-switching-mac`; `004-vlans-mac`; validate AP link speed and PoE; build an isolated VLAN with no production uplink; inspect STP and interface counters.

**Verify:** Connectivity matrix matches the design; isolation survives negative tests; configuration is backed up outside the public repo; restoration is demonstrated.

**Knowledge check:** Why does STP block a port? Native VLAN risk? Longest prefix versus administrative distance? Symptoms of duplex mismatch or exhausted PoE budget?

**Reflection:** Which boundary belongs on ICX now, and which should wait for OPNsense?

### Module 04 - RF and 802.11 foundations (14-18 hours)

**Objectives:** N10-009 2.3 and 5.4; RCWA foundational Wi-Fi (5%); preserved CWNA RF/MAC labs.

**Read:** RCWA blueprint foundational section; RUCKUS Wi-Fi fundamentals; radio specifications for R650 and H350.

**Vocabulary:** frequency, wavelength, amplitude, dB, dBm, RSSI, SNR, noise floor, attenuation, reflection, refraction, diffraction, absorption, multipath, Fresnel zone, OFDM, OFDMA, MIMO, channel width, CCI, ACI, BSS, ESS.

**Concept lesson:** RF is a shared, half-duplex medium. More signal or wider channels do not automatically mean more usable capacity. Client capability, noise, contention, rate selection, spatial streams, and airtime interact. Association is client-driven even when infrastructure attempts to steer.

**Whiteboard:** Predict 2.4/5/6 GHz behavior through two materials, then explain the expected effect of doubling channel width and increasing transmit power.

**Labs:** RF-001, RF-004, RF-006, MAC-001, and MAC-002 from the CWNA map; capture beacons and association; measure RSSI, SNR, latency, and throughput at fixed locations.

**Verify:** Use repeated measurements and control one variable; identify SSID/BSSID, channel, width, security, and information elements; state limitations instead of generalizing one client.

**Knowledge check:** dB versus dBm? CCI versus ACI? OFDM versus OFDMA? Why can high AP power worsen roaming?

**Reflection:** Which measured result contradicted the RF prediction, and what competing variable could explain it?

### Module 05 - RUCKUS architecture, products, and design (12-16 hours)

**Objectives:** RCWA RUCKUS technologies/products (15%) and design/planning (30%).

**Read:** 2025 RCWA guide; official R650/H350/ICX documents; RUCKUS controller/platform comparisons; official design course material available to the learner.

**Vocabulary:** BeamFlex, ChannelFly, SmartMesh, Unleashed, SmartZone, RUCKUS One, Cloudpath, data plane, zone, domain, AP group, venue, local breakout, tunneling, DPSK, VXLAN, RBAC, auto-cell sizing, Bonjour Gateway.

**Concept lesson:** Product selection follows requirements: client count, applications, RF environment, failure domains, management scale, licensing, uplink speed, PoE, security, and operational model. Unleashed provides real practice but is not equivalent to SmartZone or RUCKUS One.

**Whiteboard:** Produce two designs for this home: current Unleashed and hypothetical 100-AP enterprise. Defend platform, AP, redundancy, management, segmentation, and licensing choices.

**Labs:** Requirements worksheet; AP/PoE/link budget; placement comparison; channel reuse plan; platform capability matrix; planned-versus-supported feature review.

**Verify:** Every design choice traces to a requirement; unsupported features are labeled simulation/theory; failure and growth paths are explicit.

**Knowledge check:** When choose Unleashed, SmartZone, or RUCKUS One? Local breakout versus tunneling? What constrains AP count and data plane? Why plan VLAN tagging with WLANs?

**Reflection:** Which RCWA design domain cannot this lab reproduce, and what evidence could still demonstrate understanding?

### Module 06 - Unleashed deployment, WLANs, security, and roaming (14-18 hours)

**Objectives:** RCWA RUCKUS Wi-Fi solutions (30%) and tuning (10%); N10-009 2.3 and wireless portions of 4.1-4.3 and 5.4.

**Read:** Current Unleashed administrator guide for the installed release; RCWA setup, AP, advanced WLAN, security, and optimization topics.

**Vocabulary:** discovery, preprovisioning, reimage, PSK, WPA2, WPA3, PMF, 802.1X, EAP, RADIUS, captive portal, WISPr, 802.11k/r/v, sticky client, CAC, BSS minimum rate, DFS, airtime fairness.

**Concept lesson:** Deployment joins RF design, wired reachability, discovery, software compatibility, and authentication. Security configuration is a compatibility and risk decision. Roaming remains client-controlled; 802.11k/r/v can assist but cannot guarantee movement.

**Whiteboard:** Draw AP discovery/adoption, client authentication/association, and roaming flows. Mark which steps are handled by client, AP, Unleashed master, switch, DHCP, DNS, and AAA.

**Labs:** SEC-001 through SEC-005; MAC-006, MAC-007, and MAC-009; reproduce the ICX credential troubleshooting lesson as a fault tree; test guest isolation with negative cases.

**Verify:** No production key is published; test clients reconnect after restoration; isolation matrix includes gateway, peer client, management plane, and internet; roam results include timestamps and AP/BSSID changes.

**Knowledge check:** WPA2 versus WPA3? Role of PMF? 802.11k/r/v functions? DFS tradeoff? Why did discovery succeed while ICX adoption failed?

**Reflection:** Which tuning control improved one metric while harming another?

### Module 07 - Operations, monitoring, availability, and lifecycle (10-14 hours)

**Objectives:** N10-009 3.1-3.3 and 3.5; RCWA management (5%).

**Read:** Official objectives; Unleashed event/alarm, backup, upgrade, and administration documentation; FastIron monitoring and backup documentation.

**Vocabulary:** SNMPv3, MIB, trap, syslog, flow, packet capture, port mirror, SIEM, API, anomaly, SLA, EOL, EOS, HA, active-active, active-passive, jump host, in-band, out-of-band.

**Concept lesson:** Monitoring begins with a baseline and an action threshold. Logs need trustworthy time. Availability is a design property spanning power, links, management, configurations, and recovery. Home-lab scale still supports professional change and lifecycle habits.

**Whiteboard:** Build a telemetry path for AP, switch, firewall, and client. Define normal, warning, critical, owner, and response for five signals.

**Labs:** Build baseline dashboard; collect sanitized event and interface samples; configuration backup/restore runbook; firmware decision record; tabletop restore and gateway failure.

**Verify:** Alerts are actionable; restore steps identify where the real secret-bearing backup resides; lifecycle records include release, date, support status, and decision.

**Knowledge check:** SNMP trap versus poll? Packet versus flow data? RPO versus RTO? In-band versus out-of-band? Why is a baseline needed for anomaly detection?

**Reflection:** What would fail silently in the current monitoring design?

### Module 08 - Network security and access control (10-14 hours)

**Objectives:** N10-009 4.1-4.3; RCWA security planning, RBAC, PKI, guest, and access-control topics.

**Read:** Official security objectives; Unleashed hardening and guest documentation; OPNsense concepts for future planning only.

**Vocabulary:** CIA, risk, threat, vulnerability, exploit, PKI, certificate, IAM, MFA, RBAC, least privilege, RADIUS, TACACS+, SAML, NAC, 802.1X, ACL, trusted/untrusted zone, evil twin, rogue AP, VLAN hopping, ARP poisoning.

**Concept lesson:** Layered security combines identity, segmentation, hardened management, encryption, visibility, and recovery. A VLAN is not automatically a security policy. Design positive and negative tests: what must work and what must be denied.

**Whiteboard:** Threat-model management, HOME, LAB, IOT, and GUEST. Identify assets, trust boundaries, threats, preventive controls, detective controls, and recovery.

**Labs:** Credential/default-service audit; unused-port hardening plan; guest isolation validation; rogue-AP observation without interference; proposed firewall policy matrix; certificate-chain inspection.

**Verify:** Management paths use secure protocols; every proposed rule has source, destination, service, action, logging, rationale, and test; lab activities stay within authorization.

**Knowledge check:** Authentication versus authorization? Threat versus vulnerability? Evil twin versus rogue AP? Why does client isolation not replace firewall policy?

**Reflection:** Which current trust assumption creates the largest risk, and what is the least disruptive mitigation?

### Module 09 - Structured troubleshooting and performance (12-16 hours)

**Objectives:** All N10-009 5.1-5.5; RCWA troubleshooting/repair (5%); integrate every earlier module.

**Read:** Official troubleshooting objectives; RUCKUS troubleshooting course material; existing lab logs and incident report.

**Vocabulary:** symptom, scope, theory, hypothesis, escalation, CRC, runts, giants, attenuation, jitter, latency, loss, congestion, bottleneck, disassociation, root cause, contributing factor.

**Concept lesson:** Preserve evidence before changing state. Scope by user, device, service, place, band, AP, VLAN, and time. Use the OSI model as a search strategy, not a ritual. Confirm the cause by reversing or isolating it, then verify full service and prevention.

**Whiteboard:** Build a fault tree for “Wi-Fi connected, no internet” and a second for “calls drop while roaming.” Include physical, RF, switching, addressing, DNS, security, and application branches.

**Labs:** Inject one safe fault at a time: wrong PSK, disabled lab port, wrong lab VLAN, DHCP exhaustion simulation, DNS override, weak coverage; use `ping`, route trace, DNS tools, interface/MAC/ARP/VLAN/power views, packet capture, and Wi-Fi analysis.

**Verify:** Each case records symptom, scope, theory, discriminating test, cause, fix, full-service validation, and lesson; restore the known-good state after every fault.

**Knowledge check:** Correct CompTIA methodology order? CRC symptom category? How distinguish DNS failure from no route? Congestion versus bandwidth? When escalate?

**Reflection:** Which test produced the most information with the least change risk?

### Module 10 - OPNsense and segmented-network migration (12-18 hours)

**Objectives:** Apply N10-009 2.1-2.2, 3.1, 3.4, 4.1-4.3, and 5.1; apply RCWA segmentation, VLAN, local-breakout, security, and PoE/link planning.

**Read:** `vlan-plan.md`; official OPNsense documentation for the chosen release when hardware is acquired; XB6 bridge-mode guidance; ICX and Unleashed VLAN documentation.

**Vocabulary:** WAN, LAN, trunk, subinterface, stateful firewall, NAT, PAT, rule order, alias, DHCP scope, DNS resolver, return path, bridge mode, cutover, rollback.

**Concept lesson:** The target edge owns inter-VLAN policy, DHCP/DNS decisions, NAT, and the default route; the ICX carries tagged/untagged Layer 2 domains unless a consciously tested Layer 3 design says otherwise. Migration is a controlled change, not a topology sketch.

**Whiteboard:** Draw current, staging, and target states. Write a traffic-policy matrix before rules: default deny between user VLANs, explicit management paths, IOT exceptions, guest internet-only behavior, and logging.

**Labs:** Offline OPNsense build when available; isolated LAB VLAN; DHCP/DNS/NAT validation; negative firewall tests; AP SSID-to-VLAN mapping; cutover tabletop; rollback rehearsal. Until hardware exists, perform design and configuration review only and mark it simulated.

**Verify:** Complete the six gates in `vlan-plan.md`; obtain owner approval before any production cutover; verify household internet, DNS, Wi-Fi calling, AP/switch management, isolation, logging, and rollback.

**Knowledge check:** Why did XB6 block the original routed design? Stateful rule versus NAT? Where should VLAN gateways live? Why test negative cases? What triggers rollback?

**Reflection:** Which dependency creates the greatest cutover risk, and how will the staged design reduce it?

### Module 11 - Capstone and certification readiness (12-20 hours)

**Objectives:** Integrate every N10-009 domain and all seven RCWA blueprint sections; identify gaps honestly.

**Read:** Complete official objective documents; personal error log; completed lab records; relevant official product documentation.

**Vocabulary:** Review every acronym and term missed in prior checks; no new vocabulary list.

**Concept lesson:** Certification readiness means recall plus scenario judgment; engineering readiness also requires safe implementation, evidence, communication, and rollback. Hardware coverage does not equal blueprint coverage.

**Whiteboard:** From a blank page, design a small secure multi-AP site with requirements, addressing, VLANs, routing, WLANs, RF plan, authentication, monitoring, availability, lifecycle, test plan, and troubleshooting approach.

**Capstone:** Produce a sanitized current-state assessment and target design; execute a safe subset on the home lab; diagnose an injected fault; present design tradeoffs; submit a lab log, diagram, configuration excerpts, validation matrix, and rollback.

**Verify:** Audit every row in both objective maps as Know/Do/Prove; pass two timed N10-009 practice exams from legitimate sources at the chosen threshold; complete an RCWA blueprint teach-back weighted toward design and solution configuration; close or schedule every gap.

**Knowledge check:** Use scenario-based mixed questions and performance tasks; do not use unauthorized exam dumps.

**Reflection:** What can you now demonstrate, what remains theoretical, and what is the next safest lab investment?

## Graduation artifacts

- Current and target physical/logical diagrams
- Sanitized asset, addressing, VLAN, WLAN, and port inventories
- At least eight complete lab records spanning wired, wireless, operations, security, and troubleshooting
- One incident analysis and one controlled change with rollback
- RF measurement set and design recommendation
- Configuration backup/restore and troubleshooting runbooks
- N10-009 and RCWA objective audits with no unsupported “complete” claims
- Capstone design, validation matrix, and oral/written teach-back
