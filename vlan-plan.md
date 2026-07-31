# VLAN Plan

**Status:** Planned — not currently implemented.

The Ruckus ICX 7650 supports VLAN creation and Layer 3 routing. The target design below was not completed because the upstream Xfinity XB6 gateway does not expose the static-route or equivalent return-path controls needed for clean internet-connected multi-subnet operation.

| VLAN | Name | Purpose | State |
|---|---|---|---|
| 10 | MGMT | Infrastructure management | Planned |
| 20 | HOME | Trusted household clients | Planned |
| 30 | LAB | Isolated testing | Planned |
| 40 | IOT | Smart-home devices | Planned |
| 50 | GUEST | Guest access | Planned |

## Intended design

- AP uplinks would use 802.1Q trunk ports.
- Infrastructure management would use VLAN 10.
- Guest traffic would be isolated from the HOME network.
- The ICX would provide internal Layer 3 routing where appropriate.

These statements describe the target architecture, not the current production state.

## Blocking dependency

For internet-connected routed VLANs, the upstream edge must either:

1. know routes back to each VLAN subnet, or
2. be replaced or bypassed by a VLAN-aware router/firewall that performs routing, DHCP, policy enforcement, and NAT.

The current XB6 configuration does not provide the required routing controls. Deployment is therefore deferred pending an edge-router decision.

## Related lab entry

See `lab-log/2026/2026-07-30-xb6-upstream-routing-limitation.md`.
