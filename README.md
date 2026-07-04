# 🏦 Secure Banking Network Infrastructure

[![Cisco](https://img.shields.io/badge/Cisco-IOS-blue?logo=cisco)](https://www.cisco.com/)
[![Fortinet](https://img.shields.io/badge/Fortinet-FortiGate-red?logo=fortinet)](https://www.fortinet.com/)
[![Python](https://img.shields.io/badge/Python-Automation-yellow?logo=python)](https://www.python.org/)
![OSPF](https://img.shields.io/badge/Routing-OSPF-green)
![BGP](https://img.shields.io/badge/Routing-BGP-orange)
![SD-WAN](https://img.shields.io/badge/SD--WAN-Enabled-success)
![IPsec](https://img.shields.io/badge/IPsec-VPN-blue)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📖 Project Overview

This project simulates a complete Enterprise Banking Network Infrastructure designed using Cisco Enterprise Networking and FortiGate Next Generation Firewalls.

The infrastructure connects multiple banking sites through a secure and highly available WAN architecture while providing network segmentation, redundancy, disaster recovery, automation, and enterprise-grade security.

---

# 🌍 Network Architecture

The project includes:

- 🏢 Headquarters (HQ)
- 🏢 Data Center (DC)
- 🏢 Disaster Recovery Site (DR)
- 🏢 Branch Office (Aswan)
- 🌐 MPLS WAN
- 🌐 Dual ISP Connectivity
- 🔒 IPsec VPN
- 🚀 SD-WAN
- 🛡 FortiGate NGFW
- ⚙ Cisco Enterprise Routing & Switching

---

# 🖼 Network Topology

> Add your topology image here

![Network Topology](Images/Topology/Network_Topology.png)

---

# ⚙ Technologies Used

## Cisco

- Cisco IOS
- Layer 2 Switching
- Layer 3 Switching
- Core Switching
- Enterprise Routing

## Routing

- OSPF
- BGP
- Static Routing
- MPLS

## Security

- FortiGate NGFW
- Firewall Policies
- NAT
- Access Control
- Security Zones
- DMZ

## WAN

- SD-WAN
- IPsec VPN
- Dual ISP
- WAN Failover

## Network Services

- DHCP
- DNS
- VLAN
- Inter-VLAN Routing

## Monitoring

- Traffic Logging
- FortiGate Logs
- Connectivity Validation

## Automation

- Python
- Paramiko
- SSH
- Linux
- Cron
- Email Notification

---

# 🏢 Headquarters (HQ)

The Headquarters contains:

- Cisco Core Switch
- Cisco Access Switches
- FortiGate Firewall
- OSPF Routing
- SD-WAN
- IPsec VPN
- VLAN Segmentation
- DMZ
- Automation Server

---

## HQ Interfaces

![Interfaces](Images/HQ/Interfaces.png)

---

## OSPF

![OSPF](Images/HQ/OSPF_Configuration.png)

---

## SD-WAN

![SD-WAN](Images/HQ/SDWAN_Status.png)

---

## IPsec VPN

![VPN](Images/HQ/IPsec_Tunnels.png)

---

## Firewall Policies

![Policies](Images/HQ/Firewall_Policies.png)

---

## Static Routes

![Routes](Images/HQ/Static_Routes.png)

---

## Traffic Logs

![Logs](Images/HQ/Traffic_Logs.png)

---

# 🏢 Data Center

The Data Center hosts critical enterprise services and is securely connected to HQ through dedicated routing and firewall policies.

---

# 🏢 Disaster Recovery

A Disaster Recovery Site provides business continuity through redundant connectivity and secure routing.

---

# 🏢 Branch Office

The Branch connects to HQ using:

- Dual ISP
- SD-WAN
- IPsec VPN
- OSPF Routing

---

# 🔒 Security Features

- FortiGate Next Generation Firewall
- Firewall Policies
- NAT
- DMZ
- VLAN Segmentation
- Access Control
- IPsec VPN
- SD-WAN
- Traffic Logging

---

# 🚀 Routing Features

- OSPF Dynamic Routing
- BGP
- MPLS Connectivity
- Static Routes
- Inter-VLAN Routing

---

# 🌐 SD-WAN

Implemented using:

- WE ISP
- Vodafone ISP

Features:

- Automatic Failover
- Load Balancing
- VPN Health Monitoring

---

# 🔐 IPsec VPN

Site-to-Site VPN tunnels secure communication between:

- HQ
- Data Center
- Branch

---

# 🤖 Network Automation

Python automation was developed to:

- Connect to Cisco Routers
- Connect to FortiGate Firewalls
- Backup Configurations
- Compress Files
- Send Email Notifications

---

## Backup Process

![Automation](Automation/Images/Backup_Process.png)

---

## Email Notification

![Email](Automation/Images/Email_Notification.png)

---

# 🧪 Network Validation

The network was successfully validated.

## DHCP

All clients received IP addresses successfully.

## Connectivity

Successful communication verified between:

- HQ HR ↔ Branch HR
- HQ IT ↔ Branch IT
- HQ Sales ↔ Branch Sales
- HR ↔ IT
- Sales ↔ HR
- IT ↔ Sales

Average latency:

8–13 ms

---

## Test Results

### HR Test

![HR](Images/Testing/HR_to_HR_Test.png)

---

### IT Test

![IT](Images/Testing/IT_to_IT_Test.png)

---

### Sales Test

![Sales](Images/Testing/Sales_to_Sales_Test.png)

---

### HR → IT

![HRIT](Images/Testing/HR_to_IT_Test.png)

---

### IT → Sales

![ITSales](Images/Testing/IT_to_Sales_Test.png)

---

### Sales → HR

![SalesHR](Images/Testing/Sales_to_HR_Test.png)

---

# 📂 Repository Structure

```
Secure-Banking-Network
│
├── Images
├── Cisco
├── FortiGate
├── Automation
├── Documentation
├── PNETLab
└── README.md
```

---

# 📚 Documentation

- Project Report
- Presentation
- Cisco Configurations
- FortiGate Configurations
- Automation Scripts

---

# 🎯 Results

✅ Enterprise Banking Network Successfully Designed

✅ Cisco Enterprise Infrastructure

✅ FortiGate NGFW Deployment

✅ OSPF Routing

✅ BGP Connectivity

✅ MPLS Backbone

✅ SD-WAN

✅ IPsec VPN

✅ VLAN Segmentation

✅ Inter-VLAN Routing

✅ Firewall Policies

✅ Network Automation

✅ Automatic Backup

✅ Email Notification

✅ High Availability

✅ Disaster Recovery

---

# 👨‍💻 Author

## Islam Ashraf

Junior Network Engineer

CCNA Certified

CCNP Enterprise (In Progress)

GitHub

https://github.com/islamhaamzaa

LinkedIn

https://www.linkedin.com/in/islam-ashraf-hamza

---

⭐ If you like this project, don't forget to Star the repository.
