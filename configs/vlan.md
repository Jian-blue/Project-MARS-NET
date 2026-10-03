# VLAN / trunk / Router-on-a-Stick reference

## Habitat VLANs

| VLAN | Name | Purpose | Gateway |
|---:|---|---|---|
| 10 | Residential | Residential users | 10.0.110.1/24 |
| 20 | Greenhouse | Greenhouse systems | 10.0.120.1/24 |
| 30 | Robot_Maintenance | Robot maintenance systems | 10.0.130.1/24 |
| 40 | Tourist | Tourist users | 10.0.140.1/24 |

## Switch configuration

```cisco
en
config t
vlan 10
name Residential
vlan 20
name Greenhouse
vlan 30
name Robot_Maintenance
vlan 40
name Tourist
ex

interface fa0/2
switchport mode access
switchport access vlan 10
ex

interface fa0/3
switchport mode access
switchport access vlan 20
ex

interface fa0/4
switchport mode access
switchport access vlan 30
ex

interface fa0/5
switchport mode access
switchport access vlan 40
ex

interface fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30,40
no shutdown
```

## Habitat router subinterfaces

```cisco
en
config t
interface gigabitEthernet0/0.10
encapsulation dot1Q 10
ip address 10.0.110.1 255.255.255.0
exit

interface gigabitEthernet0/0.20
encapsulation dot1Q 20
ip address 10.0.120.1 255.255.255.0
exit

interface gigabitEthernet0/0.30
encapsulation dot1Q 30
ip address 10.0.130.1 255.255.255.0
exit

interface gigabitEthernet0/0.40
encapsulation dot1Q 40
ip address 10.0.140.1 255.255.255.0
exit
```

Source: submitted lab report, Section 3.1.2.
