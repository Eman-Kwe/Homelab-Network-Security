🛡️ Homelab Network Security

A comprehensive documentation project covering network hardening, intrusion detection, and DNS privacy for a production homelab environment.

## 📋 Overview

This repository documents the end-to-end security implementation for a multi-VLAN homelab running pfSense, Suricata IDS, and PiHole with encrypted DNS. Every configuration decision, firewall rule, and tuning step is recorded here as a reference for myself and the homelab community.

## 🌐 Network Topology

```
[Internet / Fiber ISP]
        ↓
[Adtran Router] ─── Static IP (MAC-bound) + Port Forwarding (WireGuard UDP 51820)
        ↓
[pfSense Firewall]
  ├─ WAN ─── DHCP Static IP, forwarding enabled
  │
  ├─ LAN1: InfraNet (10.20.10.0/24)
  │    ├── Dell A Server
  │    ├── Dell B Server
  │    ├── AK1 MICRO PC
  │    ├── KAMRUI MICRO PC
  │    └── Managed Switch
  │
  └─ LAN2: OfficeNet (10.30.0.0/24)
       ├── Netgear AP (Bridge Mode)
       ├── Dev Workstations
       └── Docked Laptops
```

## 🔧 Technology Stack

| Component       | Role                        | Version |
|:----------------|:----------------------------|:--------|
| pfSense         | Firewall / Router           | _TBD_   |
| Suricata        | Intrusion Detection System  | _TBD_   |
| PiHole          | DNS Sinkhole / Ad Blocker   | _TBD_   |
| WireGuard       | VPN (remote access)         | _TBD_   |
| Adtran Router   | ISP Edge / NAT              | _TBD_   |

## 📖 Documentation

| Guide | Description |
|:------|:------------|
| [pfSense Firewall Rules](docs/pfsense-firewall-rules.md) | WAN hardening, VLAN segmentation, alias management |
| [Static IP Assignments](docs/static-ip-assignments.md) | DHCP reservations and IP address plan |
| [Suricata IDS Setup](docs/suricata-setup.md) | Installation, rule sets, tuning, and alert workflow |
| [PiHole + Encrypted DNS](docs/pihole-setup.md) | Deployment, DoH/DoT configuration, pfSense integration |

## 📂 Repository Structure

```
homelab-network-security/
├── docs/                  # Detailed configuration guides
│   ├── pfsense-firewall-rules.md
│   ├── static-ip-assignments.md
│   ├── suricata-setup.md
│   └── pihole-setup.md
├── configs/               # Sanitized configuration exports
│   ├── pfsense/
│   └── suricata/
├── diagrams/              # Network topology and traffic flow diagrams
├── scripts/               # Backup and monitoring automation
├── CHANGELOG.md           # Implementation progress log
├── LICENSE                # MIT License
└── README.md              # This file
```

## ⚠️ Disclaimer

All IP addresses, MAC addresses, hostnames, and credentials in this repository have been sanitized or replaced with placeholders (e.g., `YOUR_IP_HERE`, `XX:XX:XX:XX:XX:XX`). **Never publish real network identifiers in a public repository.**

