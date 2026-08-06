# Lab Catalog

## Core starter labs

| Lab | Purpose | Modules | Risk |
|---|---|---:|---|
| [001 Network discovery](001-network-discovery) | Inventory and current-state topology | 00 | Low/read-only |
| [002 Follow a packet](002-follow-a-packet) | Encapsulation, protocols, services, and path | 01 | Low/read-only |
| [003 Switching and MAC learning](003-switching-mac) | CAM behavior and Layer 2 forwarding | 03 | Low/read-only |
| [004 Isolated VLAN and MAC behavior](004-vlans-mac) | Tagging, broadcast boundaries, and negative tests | 03, 10 | Moderate |
| [005 DHCP](005-dhcp) | DORA, addressing options, and fault isolation | 02 | Low/read-only core |

The preserved [CWNA exercise map](../curriculum/CWNA-109-LAB-MAP.md) contains the expanded RF, antenna, MAC, security, wired-integration, survey, and operations backlog. Create new lab plans using [`templates/lab-template.md`](../templates/lab-template.md).

## Execution rules

- Record the starting state before changes.
- Use a dedicated test client and isolated VLAN/SSID when possible.
- Never test destructive wireless techniques or unauthorized traffic.
- Define stop conditions and rollback before touching production.
- Change one principal variable at a time.
- Record expected and actual results separately.
- Sanitize evidence before it enters Git.
- A lab stays planned until verification and restoration are documented.
