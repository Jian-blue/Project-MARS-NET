# Network services reference

## DHCP

A dedicated DHCP server is located at `10.0.100.2`. DHCP relay is configured from routed interfaces/subinterfaces with `ip helper-address 10.0.100.2`.

Example documented relay configuration:

```cisco
en
configure t
interface GigabitEthernet0/0
ip helper-address 10.0.100.2
exit
```

Habitat VLAN subinterfaces also point to `10.0.100.2`.

## DNS

The dedicated DNS server uses `10.0.100.3`. The report documents DNS A-records and a validation flow that reaches the Earth server from Mars using DNS resolution.

## SMTP

The dedicated mail server uses `10.0.100.4`. Email accounts are created for required users and SMTP is enabled. The report includes send/receive evidence across departments.

Source: submitted lab report, Sections 3.1.5–3.1.7 and 3.2.5–3.2.7.
