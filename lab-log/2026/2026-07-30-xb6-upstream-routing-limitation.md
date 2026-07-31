# XB6 Upstream Routing Limitation for Multi-VLAN Design

**Date:** 2026-07-30  
**Type:** Architecture discovery  
**Status:** Confirmed limitation  
**Environment:** Household production network with controlled lab activity  
**Risk:** Low; documentation and design review only  

## Objective

Determine whether the existing Xfinity XB6 gateway and Ruckus ICX 7650 could support multiple internet-connected VLAN-backed subnets without adding another edge router or firewall.

## Starting state

- The XB6 provided the active internet gateway, NAT boundary, DHCP service, and household LAN.
- The Ruckus ICX 7650 provided managed switching and Layer 3 capability.
- A target VLAN design existed for management, home, lab, IoT, and guest traffic.
- The VLAN design had not been verified as implemented.

## Actions performed

1. Reviewed the intended multi-VLAN architecture.
2. Confirmed that the ICX 7650 can create VLANs and perform internal Layer 3 routing.
3. Evaluated the upstream return-path requirement for VLAN subnets reaching the internet.
4. Reviewed the XB6 role as the active NAT gateway.
5. Determined that the available XB6 management controls did not provide the static-route or equivalent upstream routing functions required for the proposed design.

## Validation

The design was evaluated against the required traffic path:

```text
VLAN client
   ↓
ICX VLAN gateway and routing
   ↓
XB6 NAT gateway
   ↓
Internet
```

For bidirectional communication, the upstream gateway must know how to return traffic to each VLAN subnet, or another device must perform the required routing and NAT. The available XB6 configuration did not provide that control.

## Result

The planned internet-connected VLAN deployment was deferred. No production VLAN implementation was claimed or completed as part of this work.

## Observations

- The ICX 7650 is capable of VLAN creation and inter-VLAN routing.
- The XB6 remained the active upstream NAT gateway.
- The XB6 interface available in this environment did not expose the required custom route controls.
- The existing repository wording could be read as though VLANs and trunks were already implemented.

## Analysis

The primary constraint was not VLAN capability in the ICX. The constraint was the edge-routing and NAT boundary at the XB6.

The ICX could support isolated VLANs or internal routing, but clean internet access for multiple routed subnets requires an upstream return path and appropriate NAT or a dedicated VLAN-aware edge device.

## Production impact

None. The discovery was documented before proceeding with a design that could have disrupted household connectivity.

## Rollback plan

No rollback was required because no production routing or VLAN configuration was changed.

## Lessons learned

- Confirm edge-routing, NAT, DHCP, and return-path requirements before implementing VLANs.
- A Layer 3 switch can route VLANs internally without necessarily replacing the edge firewall or NAT gateway.
- Architecture documents must clearly distinguish planned state from implemented and validated state.
- Consumer ISP gateways commonly prioritize a single-subnet residential design over advanced routing controls.

## Follow-up actions

- Keep VLANs 10, 20, 30, 40, and 50 marked as **Planned**.
- Evaluate a dedicated VLAN-aware router/firewall.
- Consider placing the XB6 into bridge mode if a supported edge-router design is selected.
- Build and validate the future design in stages, beginning with an isolated lab VLAN.
- Record any implementation as a separate change record and lab entry with verification and rollback steps.
