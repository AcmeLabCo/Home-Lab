# RUCKUS Certified Wi-Fi Associate Objective Map

Source of record: 2025 RCWA Exam Study Guide. The blueprint spans the full RUCKUS portfolio; the installed lab runs Unleashed and cannot reproduce all controller, cloud, licensing, data-plane, scale, and AAA tasks.

| Blueprint section | Weight | Required capabilities summarized | Modules | Home-lab evidence | Coverage |
|---|---:|---|---:|---|---|
| Foundational Wi-Fi technologies, standards, and concepts | 5% | RF/802.11 bands and generations through 802.11be, antennas/Fresnel, mesh/bridge, OFDM/OFDMA, authentication/association, PKI/hotspot concepts, roaming | 04, 06 | RF measurements, frame captures, roam timeline | Direct + study gaps |
| RUCKUS technologies, products, and solutions | 15% | Proprietary technologies; Bonjour/fencing; auto-cell sizing/zero touch; platforms/APs/data planes/clustering/IoT/API; services; licensing/support | 05 | Installed-product inventory and capability matrix | Study/simulate beyond Unleashed |
| Designing and planning a RUCKUS Wi-Fi solution | 30% | Requirements/survey; tunneling/local breakout; segmentation; traffic/load; product/services/host sizing; security/RBAC/PKI; discovery/PoE/zones/groups/templates/redundancy/VLANs | 05, 08, 10 | Requirements, RF plan, product/PoE/VLAN/policy design | Direct design; simulated scale |
| RUCKUS Wi-Fi solutions | 30% | SmartZone/RUCKUS One setup/licensing/organization; AP deployment/discovery/migration/CLI; advanced WLAN, policies, VLANs, maps, mesh; WLAN security/RBAC/guest | 05, 06 | Unleashed WLAN/AP/guest/mesh labs and comparative platform design | Direct Unleashed; study SZ/R1 |
| Enhancement through tuning and optimization | 10% | Performance, load/band balance, airtime/decongestion, 11k/r/v/sticky clients/CAC, data/management rates, DFS/channel and power optimization | 04, 06 | Controlled radio and roaming experiments | Direct where UI supports |
| Troubleshooting and repair | 5% | Data gathering/analysis, client/AP-controller troubleshooting, capture, API/NBI/AAA/syslog/SNMP | 07, 09 | Fault injection, logs, capture, ICX adoption analysis | Direct + study gaps |
| Solution management | 5% | Upgrades, admins/roles, events/alarms, audit, backup/restore, reports, health/thresholds, rogue AP location | 07, 08 | Baseline, alarms, backup/restore, lifecycle and rogue review | Direct where Unleashed supports |

## Portfolio gap register

| Topic requiring more than this lab | Required alternative evidence |
|---|---|
| SmartZone and RUCKUS One setup, hierarchy, licensing, and operations | Official course lab, annotated design, and platform comparison; label simulated |
| Clustering, geo-redundancy, failover, and external data planes | Failure-domain diagram, sizing scenario, and teach-back |
| Cloudpath, RUCKUS AI/Analytics, Network Director, IoT modules | Product-positioning matrix using current official documents |
| Enterprise AAA, PKI enrollment, Hotspot 2.0/ANQP/OSU/WISPr | Protocol-flow diagram and authorized virtual RADIUS lab if added |
| API/NBI integrations and large-scale automation | Official sandbox/course exercise or documented mock workflow |
| Large venue, density, capacity, and predictive survey | Requirements/design case plus explicit residential limitations |

Do not mark a gap “complete” because the term was read once. Readiness requires an accurate explanation, selection criteria, failure modes, and a scenario decision.
