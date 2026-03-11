🏠 Homelab Infrastructure

Personal homelab for hands-on practice with self-hosted infrastructure.


📋 Overview

This repository documents my homelab setup — configurations, decisions, and lessons learned.  
Hands-on practice with real infrastructure tools — built at home, skills for the real world.


🖥️ Hardware

Host Machine - MSI GF63 Thin 11SC | 12 x 11th Gen Intel(R) Core(TM) i5-11400H @ 2.70GHz | 8 GB RAM DDR4
Hypervisor - Proxmox pve-manager 9.1.1
Access Point - 	TP-Link Wireless N Access Point WA801N
USB to LAN Adapter 

🧱 Stack

| Component | Role |
|-----------|------|
| [Proxmox VE](https://www.proxmox.com/) | Hypervisor — manages all VMs and LXC containers |
| [OPNsense](https://opnsense.org/) | Firewall & router — network segmentation, rules |
| [Grafana](https://grafana.com/) | Metrics visualization & dashboards |
| [Prometheus](https://prometheus.io/) | Metrics collection & alerting |
| [Docker](https://www.docker.com/) | Container runtime for services |

---

🗺️ Architecture

```
Internet
   │
   ▼
Fritzbox Router
   │
OPNsense (Firewall/Router)
   │
   ├── WLAN ──► Laptop (management)
   │
   └── Proxmox Host
         ├── VM: OPNsense
         ├── LXC: monitoring-stack
         │     ├── Grafana
         │     └── Prometheus
         └── VM/LXC: Other services

📁 Repository Structure

```
homelab/
├── proxmox/          # Proxmox setup, config, scripts
├── opnsense/         # Firewall rules, VLAN config, notes
├── monitoring/       # Grafana dashboards, Prometheus config
├── docker/           # docker-compose files for services
└── docs/             # Runbooks, troubleshooting, decisions
```

---

🔧 Setup Guides

- [`proxmox/README.md`](./proxmox/README.md) — Proxmox installation and VM setup
- [`opnsense/README.md`](./opnsense/README.md) — OPNsense firewall configuration
- [`monitoring/README.md`](./monitoring/README.md) — Monitoring stack setup
- [`docker/README.md`](./docker/README.md) — Docker services and compose files

---

💡 Why This Stack?

- **Proxmox** — free, enterprise-grade hypervisor used widely in SMB environments
- **OPNsense** — open-source firewall with strong community, better UI than pfSense
- **Grafana + Prometheus** — industry standard monitoring combo used in most companies
- **Docker** — essential skill for any sysadmin/DevOps role today

---

📌 Skills Practiced

- Virtualization & hypervisor management (Proxmox)
- Network segmentation, firewall rules (OPNsense)
- Metrics collection, alerting, dashboard creation (Prometheus + Grafana)
- Container management and service deployment (Docker)
- Infrastructure documentation and version control (GitHub)

---

🚧 Work in Progress



*Built and maintained as a personal learning lab. All configs are sanitized before publishing.*
