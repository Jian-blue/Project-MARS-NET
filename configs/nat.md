# NAT / PAT reference

The report describes PAT on the Mars Gateway Router so multiple private Mars devices can share the gateway's public-facing address.

```cisco
en
config t
interface GigabitEthernet0/0
ip address 10.0.4.2 255.255.255.252
ip nat inside
no shutdown
exit

interface GigabitEthernet0/1
ip address 200.0.10.1 255.255.255.252
ip nat outside
no shutdown
exit

access-list 1 permit 10.0.0.0 0.255.255.255
ip nat inside source list 1 interface GigabitEthernet0/1 overload
```

Source: submitted lab report, Section 3.1.3.
