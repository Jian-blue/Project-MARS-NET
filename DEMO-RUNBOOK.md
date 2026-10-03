# MARS-NET Demo Runbook

This is a compact reviewer/demo sequence for the final `.pkt` artifact. Run it from top to bottom so the architecture story is visible before individual configuration details.

## 1. Open and orient

Open `network/MARS-NET.pkt` in Cisco Packet Tracer and identify the Earth gateway, Mars gateway, Research, Medical, Habitat, Security, Habitat switch, clients, and service servers.

## 2. Validate segmentation

On the Habitat switch:

```cisco
show vlan brief
show interfaces trunk
```

Confirm VLANs 10, 20, 30, and 40 and the trunk carrying the allowed VLANs.

## 3. Validate routing

Inspect the routed links and routing state:

```cisco
show ip interface brief
show ip route
show ip eigrp neighbors
show ip ospf neighbor
```

Confirm EIGRP inside the Mars network and OSPF on the Mars/Earth gateway path.

## 4. Validate NAT

Generate Mars-to-Earth traffic, then inspect:

```cisco
show ip nat translations
```

The project report describes PAT on the Mars gateway so internal private addresses can share the outside interface address.

## 5. Validate ACL policy

Inspect the ACLs:

```cisco
show access-lists
```

Then test both an authorized path and a path that the documented department policy is designed to block. Record the observed result in the presentation/demo notes.

## 6. Validate services

- Confirm a client receives an address through DHCP.
- Resolve a configured hostname through DNS.
- Send an SMTP message from one department and receive it in another mailbox.

## 7. Use Simulation Mode

Run at least one packet flow through Simulation Mode to show the path across the routers and the effect of routing/NAT/ACL policy.

## 8. Close with limitations

State clearly that the environment is simulated in Cisco Packet Tracer and that the Mars–Earth link is a simplified academic model.
