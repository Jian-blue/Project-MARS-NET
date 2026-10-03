# Routing configuration reference

The following command blocks are reproduced from the submitted lab report. The final `.pkt` file should be treated as the authoritative implementation.

## EIGRP — Mars internal routing

```cisco
en
config t
router eigrp 10
network 10.0.0.0
no auto-summary
ex
```

## OSPF — Mars/Earth gateway routing

```cisco
en
config t
router ospf 1
network 200.0.10.0 0.0.0.255 area 0
network 20.0.0.0 0.0.0.255 area 0
ex
```

## Route redistribution — Mars gateway

```cisco
router ospf 1
redistribute eigrp 10 subnets
router eigrp 10
redistribute ospf 1 metric 10000 100 255 1 1500
```

Source: submitted lab report, Section 3.1.1.
