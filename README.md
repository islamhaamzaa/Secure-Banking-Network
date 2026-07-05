<div align="center">

# 🏦 Secure Banking Network Infrastructure

### Enterprise Banking Network Simulation using Cisco, FortiGate, MPLS, OSPF, SD-WAN & IPsec VPN

<p align="center">

![Cisco](https://img.shields.io/badge/Cisco-IOS-1BA0D7?logo=cisco&logoColor=white)
![Fortinet](https://img.shields.io/badge/FortiGate-NGFW-EE3124?logo=fortinet&logoColor=white)
![Python](https://img.shields.io/badge/Python-Automation-3776AB?logo=python&logoColor=white)
![OSPF](https://img.shields.io/badge/Routing-OSPF-success)
![MP-BGP](https://img.shields.io/badge/Routing-MP--BGP-orange)
![MPLS](https://img.shields.io/badge/MPLS-L3VPN-blue)
![SD-WAN](https://img.shields.io/badge/SD--WAN-Dual_ISP-success)
![IPsec](https://img.shields.io/badge/IPsec-IKEv2-informational)
![MIT License](https://img.shields.io/badge/License-MIT-green)

</p>

---

Enterprise Banking Infrastructure designed and simulated in **PNETLab** using real-world enterprise networking technologies including Cisco Routing & Switching, FortiGate Next Generation Firewalls, MPLS L3VPN, OSPF, SD-WAN, and IPsec VPN.

Designed as a Graduation Project for the **Giza High Institute for Engineering and Technology**.

</div>

---

# 📑 Table of Contents

- [📖 Project Overview](#-project-overview)
- [🎯 Project Objectives](#-project-objectives)
- [🖼 Network Topology](#-network-topology)
- [🏛 Enterprise Architecture](#-enterprise-architecture)
- [🌍 Site Architecture](#-site-architecture)
- [⚙ Technologies Used](#-technologies-used)
- [🌐 Routing & WAN](#-routing--wan)
- [🛡 Security Architecture](#-security-architecture)
- [🏢 Headquarters](#-headquarters)
- [🏭 Data Center](#-data-center)
- [🏦 Branch Office](#-branch-office)
- [🤖 Network Automation](#-network-automation)
- [🧪 Validation & Testing](#-validation--testing)
- [📊 Project Statistics](#-project-statistics)
- [📂 Repository Structure](#-repository-structure)
- [📚 Documentation](#-documentation)
- [🚀 Future Improvements](#-future-improvements)
- [👥 Team](#-team)
- [👨‍💻 Author](#-author)

---

# 📖 Project Overview

This project presents the design and implementation of a secure, scalable, and highly available enterprise banking infrastructure.

The simulated environment connects the **Headquarters (HQ)**, **Data Center (DC)**, and **Branch Office** through a resilient MPLS backbone while providing secure communication, redundancy, and centralized security management.

The network follows enterprise design principles commonly adopted in the financial sector, including network segmentation, dynamic routing, firewall policy enforcement, VPN connectivity, and WAN resiliency.

---

# 🎯 Project Objectives

- Design a secure enterprise banking infrastructure.
- Ensure high availability using dual WAN connectivity.
- Implement dynamic routing using OSPF.
- Secure all inter-site communication using IPsec VPN.
- Provide WAN resiliency with SD-WAN.
- Segment departments using VLAN technology.
- Protect network resources using FortiGate NGFW.
- Automate configuration backup using Python.

---

# 🖼 Network Topology

> Replace the image below with your exported topology image.

<p align="center">

![Network Topology](Images/Topology/Network_Topology.png)

</p>

---

# 🏛 Enterprise Architecture

```text
                           Internet
                               │
              ┌────────────────┴────────────────┐
              │                                 │
          WE MPLS                         Vodafone MPLS
              │                                 │
              └────────────────┬────────────────┘
                               │
                      HQ FortiGate NGFW
                               │
                   Cisco Core Switching Layer
                               │
      ┌────────────────────────┼────────────────────────┐
      │                        │                        │
    Servers                  Users                  DMZ Zone
      │
      │
   MPLS Backbone
      │
      │
 Branch FortiGate
      │
 Cisco Access Switches
      │
 HR • IT • Sales • Management
```

---

# 🌍 Site Architecture

| Site | Description |
|------|-------------|
| 🏢 Headquarters | Main campus hosting the enterprise core infrastructure, firewall cluster, and automation server |
| 🏭 Data Center | Critical services, centralized resources, and disaster recovery |
| 🏦 Branch Office | Remote banking branch connected through MPLS and protected using FortiGate |
| 🌐 MPLS Cloud | Dual-provider WAN connectivity using WE and Vodafone |
| 🛡 FortiGate | Security gateway providing NGFW, VPN, NAT, and SD-WAN |
| 🤖 Automation Server | Python-based backup automation and email notification system |

---

# ⚙ Technologies Used

| Category | Technology |
|----------|------------|
| Routing | OSPF |
| WAN | MPLS L3VPN |
| VPN | IPsec IKEv2 |
| Firewall | FortiGate NGFW |
| Switching | Cisco Catalyst |
| Redundancy | SD-WAN |
| Automation | Python + Paramiko |
| Monitoring | FortiAnalyzer |
| Segmentation | VLAN |
# 🌐 Routing & WAN

The enterprise network is designed to provide secure, resilient, and scalable communication between all banking sites.

### Routing Protocol

- OSPF Dynamic Routing
- Fast Route Convergence
- Automatic Route Advertisement
- Multi-Area Enterprise Design
- Dynamic Path Selection

### MPLS Backbone

The WAN infrastructure is built on an MPLS L3VPN network connecting all enterprise locations.

Features include:

- Secure Layer-3 VPN
- Private Enterprise WAN
- Low Latency
- High Availability
- Carrier Redundancy

### SD-WAN

Each site connects to two different Internet/MPLS providers.

**Primary Provider**

- WE MPLS

**Secondary Provider**

- Vodafone MPLS

SD-WAN continuously monitors:

- Link Health
- Packet Loss
- Latency
- Jitter

Traffic automatically switches to the healthy link during failures.

---

# 🔐 Security Architecture

The security layer is built using FortiGate Next Generation Firewalls deployed at every site.

## Security Features

- Next Generation Firewall (NGFW)
- Stateful Firewall Policies
- NAT
- Security Zones
- VLAN Isolation
- IPSec VPN
- Application Control
- Web Filtering
- Intrusion Prevention
- Secure Remote Management (SSH)

---

# 🏢 Headquarters

The Headquarters hosts the enterprise core infrastructure.

## Network Interfaces

![](Images/HQ/Interfaces.png)

---

## OSPF Configuration

![](Images/HQ/OSPF_Configuration.png)

---

## SD-WAN Status

![](Images/HQ/SDWAN_Status.png)

---

## IPSec VPN

![](Images/HQ/IPsec_Tunnels.png)

---

## Firewall Policies

![](Images/HQ/Firewall_Policies.png)

---

## Static Routes

![](Images/HQ/Static_Routes.png)

---

## Traffic Logs

![](Images/HQ/Traffic_Logs.png)

---

# 🏭 Data Center

The Data Center hosts critical banking services and provides redundancy.

## Interfaces

![](Images/DC/Interfaces.png)

---

## OSPF Configuration

![](Images/DC/OSPF_Configuration.png)

---

## Firewall Policies

![](Images/DC/Firewall_Policies.png)

---

## Static Routes

![](Images/DC/Static_Routes.png)

---

## Traffic Logs

![](Images/DC/Traffic_Logs.png)

---

# 🏦 Branch Office

The Branch Office communicates securely with HQ through MPLS and IPsec VPN.

## Interfaces

![](Images/Branch/Interfaces.png)

---

## OSPF Configuration

![](Images/Branch/OSPF_Configuration.png)

---

## SD-WAN

![](Images/Branch/SDWAN_Status.png)

---

## IPSec VPN

![](Images/Branch/IPsec_Tunnels.png)

---

## Firewall Policies

![](Images/Branch/Firewall_Policies.png)

---

## Static Routes

![](Images/Branch/Static_Routes.png)

---

## Traffic Logs

![](Images/Branch/Traffic_Logs.png)

---
# 🤖 Network Automation

To reduce manual effort and improve operational efficiency, a Python-based automation solution was implemented.

The automation server connects securely to Cisco routers and FortiGate firewalls using SSH.

## Features

- Automated Configuration Backup
- Secure SSH Connection
- Scheduled Execution using Cron
- Email Notification
- Backup Archiving
- Error Logging

---

## Backup Process

![](Automation/Images/Backup_Process.png)

---

## Email Notification

![](Automation/Images/Email_Notification.png)

---

# 🧪 Validation & Testing

After deployment, multiple validation tests were performed to verify connectivity, routing, VPN operation, firewall policies, and WAN redundancy.

---

## End-to-End Connectivity

### HR → HR

![](Images/Testing/HR_to_HR_Test.png)

---

### IT → IT

![](Images/Testing/IT_to_IT_Test.png)

---

### Sales → Sales

![](Images/Testing/Sales_to_Sales_Test.png)

---

### HR → IT

![](Images/Testing/HR_to_IT_Test.png)

---

### IT → Sales

![](Images/Testing/IT_to_Sales_Test.png)

---

### Sales → HR

![](Images/Testing/Sales_to_HR_Test.png)

---

# 📊 Validation Summary

| Test | Status |
|-------|--------|
| OSPF Neighbor Adjacency | ✅ Passed |
| MPLS Connectivity | ✅ Passed |
| Inter-VLAN Routing | ✅ Passed |
| Site-to-Site VPN | ✅ Passed |
| SD-WAN Failover | ✅ Passed |
| Internet Connectivity | ✅ Passed |
| Firewall Policies | ✅ Passed |
| Configuration Backup | ✅ Passed |

---

# 📈 Project Statistics

| Category | Value |
|-----------|------:|
| Cisco Routers | 20+ |
| Cisco Switches | 10+ |
| FortiGate Firewalls | 3 |
| MPLS Routers | 10+ |
| VLANs | 6 |
| VPN Tunnels | 6 |
| Firewall Policies | 50+ |
| Automation Scripts | 2 |
| Validation Tests | 20+ |
| Configuration Files | 30+ |

---

# 📂 Repository Structure

```text
Secure-Banking-Network
│
├── Automation
│   ├── Images
│   ├── backup.py
│   └── backup.sh
│
├── Cisco
│
├── Documentation
│
├── FortiGate
│
├── Images
│   ├── Branch
│   ├── DC
│   ├── HQ
│   ├── Testing
│   └── Topology
│
├── PNETLab
│
├── LICENSE
│
└── README.md
```

---

# 📚 Documentation

The repository contains:

- Complete Graduation Project Book
- Cisco Router Configurations
- Cisco Switch Configurations
- FortiGate Firewall Configurations
- PNETLab Topology
- Network Automation Scripts
- Validation Screenshots

---

# 🚀 Future Improvements

Future enhancements may include:

- EVPN VXLAN Fabric
- Cisco DNA Center Integration
- FortiManager Centralized Management
- FortiAnalyzer Reporting
- Zabbix Monitoring
- Grafana Dashboard
- Ansible Automation
- NetBox IPAM
- Terraform Infrastructure as Code

---

# 🏆 Project Highlights

- Enterprise Banking Network Design
- Cisco Enterprise Routing & Switching
- MPLS Layer-3 VPN
- MP-BGP Provider Network
- OSPF Dynamic Routing
- SD-WAN with Dual ISP
- FortiGate NGFW Deployment
- Site-to-Site IPsec VPN
- VLAN Segmentation
- DMZ Implementation
- Python Network Automation
- Configuration Backup Server
- Enterprise Security Policies
- High Availability Design

---

# 👥 Team Members

This project was developed by:

- Islam Ashraf Hamza
- Mahmoud Hesham
- Mariam Wefky
- Abd Elhakem Ezzat
- Mohamed Salah
- Bassem Adel
- Hisham Hany

Supervisor:

**Dr. Atef Salama**

---

# 👨‍💻 Author

## Islam Ashraf Hamza

Communication & Electronics Engineer

**Certifications**

- Cisco Certified Network Associate (CCNA)
- CCNP Enterprise (In Progress)

**Skills**

- Cisco Routing & Switching
- FortiGate NGFW
- MPLS
- OSPF
- MP-BGP
- SD-WAN
- IPsec VPN
- Python Automation

GitHub:

https://github.com/islamhaamzaa

LinkedIn:

https://www.linkedin.com/in/islam-ashraf-hamza

---

# ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

Feedback, suggestions, and contributions are always welcome.

---

<div align="center">

## Thank You ❤️

Enterprise Banking Network Simulation

Cisco • Fortinet • MPLS • SD-WAN • OSPF • Python Automation

</div>
| Security | ACL, NAT, Firewall Policies |

---
