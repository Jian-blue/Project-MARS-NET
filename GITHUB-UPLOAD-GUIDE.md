# GitHub Upload Guide

## 1. Put the Packet Tracer artifact in place

Copy your final Packet Tracer file to:

```text
network/MARS-NET.pkt
```

## 2. Initialize and push

```bash
git init
git add .
git commit -m "Initial commit: MARS-NET computer networks lab project"
git branch -M main
git remote add origin https://github.com/<your-account>/<your-repo>.git
git push -u origin main
```

## 3. Recommended repository name

```text
mars-net-computer-network
```

Alternative:

```text
mars-net-cisco-packet-tracer
```

## 4. Recommended GitHub About text

```text
Enterprise-style Mars habitat network simulation built in Cisco Packet Tracer using VLANs, Router-on-a-Stick, EIGRP, OSPF, NAT/PAT, ACLs, DHCP, DNS, and SMTP.
```

## 5. First README section reviewers should see

The repository is already arranged so the README leads with architecture, technologies, validation evidence, quick start, and file layout. That is intentionally more reviewer-friendly than making the academic report the homepage.

## Suggested GitHub repository topics

```text
computer-networks
cisco-packet-tracer
network-engineering
network-security
routing
vlan
eigrp
ospf
nat
acl
dhcp
dns
smtp
```

## Suggested initial commit

```text
feat: publish MARS-NET network simulation and documentation
```
