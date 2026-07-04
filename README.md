# 🏦 Secure Banking Network Infrastructure

[![Cisco](https://img.shields.io/badge/Cisco-IOS-1BA0D7?logo=cisco&logoColor=white)](https://www.cisco.com/)
[![Fortinet](https://img.shields.io/badge/Fortinet-FortiGate_NGFW-EE3124?logo=fortinet&logoColor=white)](https://www.fortinet.com/)
[![Python](https://img.shields.io/badge/Python-Automation-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![OSPF](https://img.shields.io/badge/Routing-OSPF-2E7D32)](#-routing--wan-architecture)
[![BGP](https://img.shields.io/badge/Routing-MP--BGP_VPNv4-F57C00)](#-routing--wan-architecture)
[![SD-WAN](https://img.shields.io/badge/SD--WAN-Dual_ISP_Failover-2E7D32)](#-sd-wan--wan-resilience)
[![IPsec](https://img.shields.io/badge/IPsec-IKEv2_VPN-1565C0)](#-security-architecture)
[![PCI-DSS](https://img.shields.io/badge/Compliance-PCI--DSS_v4.0-6A1B9A)](#-compliance--standards)
[![ISO 27001](https://img.shields.io/badge/Compliance-ISO_27001%3A2022-6A1B9A)](#-compliance--standards)
[![License](https://img.shields.io/badge/License-MIT-2E7D32)](LICENSE)

A graduation-project simulation of an enterprise, multi-site banking network — built on **PNETLab** and designed around real ISP/MPLS, dual-firewall, and dynamic-routing practices used in production financial networks.

---

## 📖 Project Overview

This project designs and simulates a complete **enterprise banking WAN**, connecting a **Cairo Headquarters (HQ)**, a **Data Center (DC)**, and an **Aswan Branch** over a resilient, security-hardened infrastructure.

The design combines:

- Dual-carrier **MPLS L3VPN transport** (WE and Vodafone) for WAN connectivity between sites
- **FortiGate NGFW** at every site for perimeter security, VPN termination, and traffic inspection
- **SD-WAN with automatic ISP failover** for high availability
- **Site-to-site IPsec IKEv2 VPN** as a backup/overlay path
- **OSPF with BFD** for fast intra-site and core convergence, and **MP-BGP (VPNv4)** for MPLS-provider routing
- **VLAN micro-segmentation** and a **DMZ** to isolate banking departments (HR, IT, Sales) and public-facing services
- Centralized visibility via **FortiAnalyzer** and endpoint compliance via **FortiClient EMS**
- Python-based **network automation** for configuration backup and alerting

The architecture was designed with **PCI-DSS v4.0** and **ISO 27001:2022** control objectives in mind — segmentation of cardholder-adjacent zones, restricted administrative access, and centralized logging.

> 🎓 Graduation Project — Giza High Institute for Engineering and Technology, Communications & Electronics Engineering, 2025/2026 (Supervisor: Dr. Atef Salama)

---

## 🖼 Network Topology

![Network Topology](Images/Topology/Network_Topology.png)

The topology connects three sites — **Cairo HQ**, **Data Center**, and **Aswan Branch** — through dual-provider MPLS backbones (WE and Vodafone), with FortiGate firewalls at the WAN edge of each site handling SD-WAN steering and IPsec VPN termination.

---

## 🌍 Site Architecture

| Site | Role | Key Components |
|---|---|---|
| **Cairo HQ** | Headquarters | Core/Access switching, FortiGate NGFW, SD-WAN hub, DMZ, VLAN segmentation, automation server |
| **Data Center** | Critical services & DR | Core switching, FortiGate NGFW, dedicated routing/firewall policies to HQ |
| **Aswan Branch** | Remote branch | Dual-ISP SD-WAN, FortiGate NGFW, IPsec VPN back to HQ, OSPF |
| **MPLS Core** | Transport | Dual-carrier PE/P/RR routers (WE & Vodafone) providing L3VPN transport between sites |

---

## ⚙ Technologies Used

**Cisco:** IOS · Layer 2/3 Switching · Core Switching · Enterprise Routing

**Routing:** OSPF (with BFD) · MP-BGP (VPNv4) · Static Routing · MPLS L3VPN

**Security:** FortiGate NGFW · Firewall Policies · NAT · DMZ · Access Control · Security Zones · FortiAnalyzer · FortiClient EMS

**WAN:** SD-WAN · IPsec IKEv2 VPN · Dual ISP (WE / Vodafone) · Automatic Failover

**Network Services:** DHCP · DNS · VLAN · Inter-VLAN Routing

**Monitoring:** Traffic Logging · FortiGate Logs · Connectivity Validation

**Automation:** Python · Paramiko · SSH · Cron · Email Notification

---

## 🚦 Routing & WAN Architecture

- **OSPF with BFD** runs within each site and across the MPLS-facing edge for fast (sub-second) failure detection and convergence.
- **MP-BGP (VPNv4)** is used across the MPLS provider backbones to exchange site VPNv4 routes between the WE and Vodafone PE routers, keeping HQ, DC, and Branch reachable across either carrier.
- **Static routing** is used at select edge points for default/backup paths.

## 🌐 SD-WAN & WAN Resilience

Each site's FortiGate is dual-homed to **WE** and **Vodafone** MPLS circuits. SD-WAN rules provide:

- Automatic failover between carriers based on link health (jitter/latency/packet loss SLAs)
- Load balancing across both ISPs
- Continuous VPN/tunnel health monitoring

## 🔐 Security Architecture

- **FortiGate NGFW** at HQ, DC, and Branch — firewall policies, NAT, and security-zone enforcement
- **Site-to-site IPsec IKEv2 VPN** between HQ, DC, and Branch as a resilient overlay to the MPLS transport
- **VLAN-based segmentation** isolating HR, IT, and Sales departments from each other and from the DMZ
- **DMZ** for any externally reachable services, isolated from internal VLANs
- **FortiAnalyzer** for centralized log correlation and traffic visibility
- **FortiClient EMS** for endpoint compliance and posture enforcement

## 📋 Compliance & Standards

The design maps to control objectives from:

- **PCI-DSS v4.0** — network segmentation, restricted administrative access, logging and monitoring of cardholder-adjacent zones
- **ISO 27001:2022** — access control, network security management, and operational security controls

> ⚠️ This is an academic simulation intended to demonstrate these controls conceptually; it has not been through a formal PCI-DSS/ISO 27001 audit.

---

## 🤖 Network Automation

Python-based automation (Paramiko/SSH) connects to Cisco routers and FortiGate firewalls to:

- Pull and back up running configurations on a schedule (cron)
- Compress and archive backup files
- Send email notifications on completion/failure

| Backup Process | Email Notification |
|---|---|
| ![Automation](Automation/Images/Backup_Process.png) | ![Email](Automation/Images/Email_Notification.png) |

---

## 🧪 Validation & Testing

The network was validated end-to-end after deployment:

- ✅ All clients received addressing via DHCP successfully
- ✅ Verified connectivity between HQ and Branch across HR, IT, and Sales VLANs
- ✅ Verified inter-VLAN connectivity within a site (HR ↔ IT ↔ Sales)
- ✅ Average measured latency across the WAN: **8–13 ms**

<details>
<summary><b>HQ configuration screenshots</b></summary>

| Interfaces | OSPF | SD-WAN Status |
|---|---|---|
| ![Interfaces](Images/HQ/Interfaces.png) | ![OSPF](Images/HQ/OSPF_Configuration.png) | ![SD-WAN](Images/HQ/SDWAN_Status.png) |

| IPsec Tunnels | Firewall Policies | Static Routes |
|---|---|---|
| ![VPN](Images/HQ/IPsec_Tunnels.png) | ![Policies](Images/HQ/Firewall_Policies.png) | ![Routes](Images/HQ/Static_Routes.png) |

![Traffic Logs](Images/HQ/Traffic_Logs.png)

</details>

<details>
<summary><b>Connectivity test results</b></summary>

| Test | Result |
|---|---|
| HR ↔ HR (HQ ↔ Branch) | ![HR](Images/Testing/HR_to_HR_Test.png) |
| IT ↔ IT (HQ ↔ Branch) | ![IT](Images/Testing/IT_to_IT_Test.png) |
| Sales ↔ Sales (HQ ↔ Branch) | ![Sales](Images/Testing/Sales_to_Sales_Test.png) |
| HR → IT | ![HRIT](Images/Testing/HR_to_IT_Test.png) |
| IT → Sales | ![ITSales](Images/Testing/IT_to_Sales_Test.png) |
| Sales → HR | ![SalesHR](Images/Testing/Sales_to_HR_Test.png) |

</details>

---

## 📂 Repository Structure

```
Secure-Banking-Network
│
├── Cisco/                # Router & switch configs (MPLS PE/P/RR, Core, Access, DMZ)
├── FortiGate/             # FortiGate NGFW configs — HQ, DC, Branch (sanitized, see note below)
├── Automation/            # Python backup/notification scripts + screenshots
├── Documentation/         # Graduation project report (.docx)
├── PNETLab/               # PNETLab lab topology file (.unl)
├── Images/                # Topology diagram + validation screenshots
└── README.md
```

---

## 📚 Documentation

- 📄 [Graduation Project Book](Documentation/Graduation_Project_Book.docx) — full written report (design, implementation, testing, conclusion)
- 🖧 [PNETLab Topology File](PNETLab/Graduation%20project.unl) — importable lab file
- ⚙ Full Cisco and FortiGate configuration exports (see `Cisco/` and `FortiGate/`)

---

## 🔒 A Note on Configuration Files

The FortiGate configuration exports in this repository have had all administrative passwords, PSK/IPsec secrets, and private keys **redacted** prior to publishing. If you're reviewing these configs for learning purposes, treat the redacted values as placeholders — they are not usable credentials.

---

## 🎯 Results

✅ Multi-site enterprise banking network designed and deployed in simulation
✅ Dual-carrier MPLS transport (WE & Vodafone) with MP-BGP VPNv4
✅ OSPF + BFD for fast intra-site convergence
✅ FortiGate NGFW deployment across HQ, DC, and Branch
✅ SD-WAN with automatic ISP failover
✅ Site-to-site IPsec IKEv2 VPN
✅ VLAN micro-segmentation & DMZ isolation
✅ Centralized visibility via FortiAnalyzer, endpoint compliance via FortiClient EMS
✅ PCI-DSS v4.0 / ISO 27001:2022–aligned design
✅ Python-based configuration backup automation with email alerting
✅ End-to-end connectivity and latency validation

---

## 👥 Team

This project was designed and built by a 7-member graduation team:

- **Islam Ashraf Hamza**
- Mariam Wefky
- Eslam Ashraf
- Abd Elhakem Ezat
- Mahmoud Hesham
- Mohamed Salah
- Basem Adel
- Hisham Hany

Supervised by **Dr. Atef Salama** — Giza High Institute for Engineering and Technology.

---

## 👨‍💻 Author / Contact

**Islam Ashraf Hamza**
Junior Network Engineer · CCNA Certified · CCNP Enterprise (In Progress)

[![GitHub](https://img.shields.io/badge/GitHub-islamhaamzaa-181717?logo=github&logoColor=white)](https://github.com/islamhaamzaa)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Islam_Ashraf_Hamza-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/islam-ashraf-hamza)

---

⭐ If you found this project useful, consider starring the repository.

