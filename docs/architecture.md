# Architecture and IP Plan

## Design goals

The project targets a secure and scalable enterprise-style network that supports inter-department communication while restricting access to protected resources. The design uses logical segmentation, dynamic routing, centralized services, NAT, and extended ACLs.

## Addressing plan

| Device / segment | Interface | Address |
|---|---|---|
| Earth Gateway Router | Gi0/0 | 200.0.10.2/30 |
| Earth Gateway Router | Gi0/1 | 20.0.0.1/24 |
| Earth Server | NIC | 20.0.0.5/24 |
| Mars Gateway Router | Gi0/1 | 200.0.10.1/30 |
| Mars Gateway Router | Gi0/0 | 10.0.4.2/30 |
| Research Router | Gi0/0 | 10.0.4.1/30 |
| Research Router | Gi0/1 | 10.0.1.1/30 |
| Research Router | Fa0/1 | 10.0.10.1/24 |
| Medical Router | Gi0/1 | 10.0.1.2/30 |
| Medical Router | Gi0/2 | 10.0.2.1/30 |
| Medical Router | Fa0/1 | 10.0.20.1/24 |
| Habitat Inter-VLAN Router | Gi0/1 | 10.0.2.2/30 |
| Habitat Inter-VLAN Router | Gi0/2 | 10.0.3.1/30 |
| Security Router | Gi0/1 | 10.0.3.2/30 |
| Security Router | Gi0/2 | 10.0.100.1/24 |
| Security Router | Fa0/1 | 10.0.200.1/24 |
| DHCP Server | NIC | 10.0.100.2/24 |
| DNS Server | NIC | 10.0.100.3/24 |
| SMTP Server | NIC | 10.0.100.4/24 |
| Habitat VLAN 10 | Gateway | 10.0.110.1/24 |
| Habitat VLAN 20 | Gateway | 10.0.120.1/24 |
| Habitat VLAN 30 | Gateway | 10.0.130.1/24 |
| Habitat VLAN 40 | Gateway | 10.0.140.1/24 |

Source: submitted lab report, Table 2.1.

## Logical zones

- **Research** — 10.0.10.0/24
- **Medical** — 10.0.20.0/24
- **Habitat / Residential** — VLAN 10, 10.0.110.0/24
- **Habitat / Greenhouse** — VLAN 20, 10.0.120.0/24
- **Habitat / Robot Maintenance** — VLAN 30, 10.0.130.0/24
- **Habitat / Tourist** — VLAN 40, 10.0.140.0/24
- **Security** — 10.0.200.0/24
- **Services** — 10.0.100.0/24
- **Earth LAN** — 20.0.0.0/24
