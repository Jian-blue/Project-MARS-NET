# Testing and validation

The submitted report states that multiple tests were performed after implementation to verify routing, VLANs, network services, NAT, and ACL behavior.

## Reproducible validation checklist

| Area | What to inspect in Packet Tracer | Evidence in repo |
|---|---|---|
| Routing | Routing tables and routing-neighbor state | `docs/evidence/routing-*.png` |
| VLANs | VLAN database, access ports, trunk allowed VLANs | `vlan-switch.png`, `trunk.png` |
| Inter-VLAN | Ping across authorized Habitat VLANs | `vlan-router-interfaces.png` |
| NAT/PAT | Translation entries during Mars → Earth traffic | `nat-translations.png` |
| ACL | Hit counts / permitted and denied flows | `acl-*.png` |
| DHCP | Client receives expected address/gateway/DNS | `dhcp-client-assignment.png` |
| DNS | Resolve a configured hostname and reach the service | `dns-service.png` + Earth-server evidence |
| SMTP | Send and receive a test email between departments | `smtp-send.png`, `smtp-delivery.png`, `smtp-receive.png` |
| Simulation | Observe packet path and policy behavior | Packet Tracer Simulation Mode |

## Useful verification commands

These are standard Packet Tracer/Cisco IOS checks that make the repository easier to audit alongside the `.pkt` artifact:

```cisco
show ip route
show ip eigrp neighbors
show ip ospf neighbor
show vlan brief
show interfaces trunk
show ip nat translations
show access-lists
show ip interface brief
```

## Reported outcome

The academic report concludes that authorized communication was allowed and restricted traffic was blocked, with DHCP, DNS, SMTP, NAT, EIGRP, OSPF, VLANs, and ACLs operating together in the simulation.
