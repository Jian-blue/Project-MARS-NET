# ACL / security reference

The submitted project uses extended ACLs to enforce department-to-department communication policy. The following entries are reproduced from the report.

## Research router

```cisco
configure t
ip access-list extended RESEARCH_ACL
permit ip 10.0.10.0 0.0.0.255 10.0.200.0 0.0.0.255
permit ip 10.0.10.0 0.0.0.255 10.0.20.0 0.0.0.255
permit ip 10.0.10.0 0.0.0.255 10.0.130.0 0.0.0.255
permit ip 10.0.10.0 0.0.0.255 10.0.100.0 0.0.0.255
deny ip 10.0.10.0 0.0.0.255 10.0.0.0 0.255.255.255
permit ip any any
exit
interface GigabitEthernet0/0
ip access-group RESEARCH_ACL in
exit
```

## Medical router

```cisco
configure t
ip access-list extended MEDICAL_ACL
permit ip 10.0.20.0 0.0.0.255 10.0.200.0 0.0.0.255
permit ip 10.0.20.0 0.0.0.255 10.0.100.0 0.0.0.255
permit ip 10.0.20.0 0.0.0.255 10.0.10.0 0.0.0.255
permit ip 10.0.20.0 0.0.0.255 10.0.110.0 0.0.0.255
permit ip 10.0.20.0 0.0.0.255 10.0.120.0 0.0.0.255
permit ip 10.0.20.0 0.0.0.255 10.0.140.0 0.0.0.255
deny ip 10.0.20.0 0.0.0.255 10.0.0.0 0.255.255.255
permit ip any any
exit
interface GigabitEthernet0/0
ip access-group MEDICAL_ACL in
exit
```

## Habitat router — Residential / Greenhouse / Robot Maintenance / Tourist

The report defines four extended ACLs named `RESIDENTIAL_ACL`, `GREENHOUSE_ACL`, `ROBOT_MAINT_ACL`, and `TOURIST_ACL`. Their permit/deny entries are preserved in the academic report and the evidence screenshots in `docs/evidence/`.

## Security router

```cisco
configure t
ip access-list extended SEC_INBOUND
permit icmp any 10.0.200.0 0.0.0.255 echo-reply
permit tcp any 10.0.200.0 0.0.0.255 established
permit udp host 10.0.100.3 10.0.200.0 0.0.0.255 eq domain
deny icmp 10.0.0.0 0.255.255.255 10.0.200.0 0.0.0.255 echo
deny ip 10.0.0.0 0.255.255.255 10.0.200.0 0.0.0.255
permit ip any any
exit
interface GigabitEthernet0/0
ip access-group SEC_INBOUND out
exit
```

Source: submitted lab report, Section 3.1.4.
