# Enterprise VLAN Network Design & Inter-VLAN Routing

Enterprise-grade VLAN segmentation and inter-VLAN routing implementation using Cisco Packet Tracer.

---

## 📌 Overview

This project demonstrates the design and implementation of a segmented enterprise network using:

- VLAN-based departmental isolation
- IEEE 802.1Q trunking
- Router-on-a-Stick inter-VLAN routing
- Optimized subnet allocation
- CLI-based verification and troubleshooting

The lab simulates structured enterprise segmentation across IT, HR, and Web Server departments.

---

## 🏢 Internship Information

**Program:** Tech Hierarchy Internship Program  
**Internship ID:** TH-CYB-1112  
**Author:** Jeremiah Olayinka Olatubosun  

---

## 🧠 Architecture Summary

- Topology: Star
- Layer 2 Segmentation via VLANs
- Layer 3 Routing via Router-on-a-Stick
- Static IP Allocation
- Structured Subnet Planning

---

## 🌐 VLAN & Subnet Design

| VLAN | Department | Subnet | Default Gateway |
|------|------------|--------|-----------------|
| 10 | IT | 192.168.10.0/27 | 192.168.10.1 |
| 20 | HR | 192.168.10.32/27 | 192.168.10.33 |
| 30 | Web-Servers | 192.168.10.64/28 | 192.168.10.65 |

Each VLAN operates as an independent broadcast domain to improve performance and enforce logical segmentation.

---

## ⚙️ Technologies Used

- Cisco Packet Tracer
- VLAN Configuration
- IEEE 802.1Q Trunking
- Router-on-a-Stick Architecture
- IP Subnetting (/27 and /28)
- CLI Verification Commands

---

## 🔍 Verification Commands

The following commands were used to validate implementation:


show vlan brief
show interfaces trunk
show ip interface brief
show ip route


Connectivity tests confirmed:

- Intra-VLAN communication
- Inter-VLAN routing functionality
- Proper routing table population

---

## 📂 Repository Structure


enterprise-vlan-network-design/
│
├── README.md
├── DOCUMENTATION.md
├── screenshots/
│ ├── topology.png
│ ├── show-ip-route.png
│ ├── show-vlan-brief.png
│
└── packet-tracer/
└── Networking-topology.pkt


---

## 🚀 Skills Demonstrated

- VLAN deployment
- Inter-VLAN routing
- IP address planning
- Broadcast domain segmentation
- Layer 2 / Layer 3 integration
- CLI troubleshooting methodology
- Enterprise network documentation

---

## 📎 Documentation

Detailed technical documentation is available in:

`DOCUMENTATION.md`

---

## 📌 Author

Jeremiah Olayinka Olatubosun  
Aspiring Network & Infrastructure Engineer
