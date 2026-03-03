# Enterprise VLAN Network Implementation & Inter-VLAN Routing
Tech Hierarchy Internship Program  
Internship ID: TH-CYB-1112  
Author: Jeremiah Olayinka Olatubosun  

---

## 1. Project Overview

This project involved the design and implementation of a logically segmented enterprise network using VLAN technology and Router-on-a-Stick architecture in Cisco Packet Tracer.

The network simulates departmental separation across:

- IT Department
- HR Department
- Web Servers Segment

The implementation demonstrates Layer 2 segmentation, Layer 3 routing, optimized subnet allocation, and enterprise-grade documentation practices.

---

## 2. Network Objectives

- Implement VLAN-based segmentation
- Configure IEEE 802.1Q trunking
- Deploy Router-on-a-Stick inter-VLAN routing
- Allocate subnets based on host requirements
- Validate routing using CLI verification
- Ensure successful intra- and inter-VLAN communication

---

## 3. Logical Network Design

| VLAN | Department     | Hosts | Subnet               | Default Gateway     |
|------|---------------|--------|----------------------|---------------------|
| 10   | IT            | 5      | 192.168.10.0/27      | 192.168.10.1        |
| 20   | HR            | 5      | 192.168.10.32/27     | 192.168.10.33       |
| 30   | Web-Servers   | 3      | 192.168.10.64/28     | 192.168.10.65       |

Each VLAN operates within an independent broadcast domain to reduce broadcast traffic and improve performance.

Subnet allocation was optimized according to departmental host requirements.

---

## 4. Network Topology Architecture

Architecture Type: Star Topology  
Routing Design: Router-on-a-Stick  

- End devices connect to a central Layer 2 switch.
- The switch connects to a router using a trunk link.
- The router performs Layer 3 gateway functionality using subinterfaces.
- VLAN tags are handled using IEEE 802.1Q encapsulation.

---

## 5. Switch Configuration

### 5.1 VLAN Creation


enable
configure terminal
vlan 10
name IT
vlan 20
name HR
vlan 30
name WEB
exit


### 5.2 Access Port Assignment


interface fa0/1
switchport mode access
switchport access vlan 10


Access ports were assigned according to departmental VLAN requirements.

### 5.3 Trunk Configuration


interface g0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30


The trunk link allows VLAN traffic between the switch and router.

---

## 6. Router Configuration (Router-on-a-Stick)

### 6.1 Enable Physical Interface


interface g0/0
no shutdown


### 6.2 Subinterface Configuration

VLAN 10:


interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.224


VLAN 20:


interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.10.33 255.255.255.224


VLAN 30:


interface g0/0.30
encapsulation dot1Q 30
ip address 192.168.10.65 255.255.255.240


Each subinterface acts as the default gateway for its respective VLAN.

---

## 7. IP Addressing Strategy

Static IP addressing was assigned to all 13 end devices.

Example (IT Host):

IP Address: 192.168.10.2  
Subnet Mask: 255.255.255.224  
Default Gateway: 192.168.10.1  

Addressing ensured no overlap between broadcast domains.

---

## 8. Verification & Validation

### Commands Used


show vlan brief
show interfaces trunk
show ip interface brief
show ip route


### Validation Performed

- Confirmed VLAN creation and port membership
- Verified trunk encapsulation
- Confirmed active subinterfaces
- Validated routing table entries
- Performed intra-VLAN ping tests
- Performed inter-VLAN ping tests

All connectivity tests returned successful responses.

---

## 9. Security & Design Considerations

- VLAN segmentation reduces broadcast domain size
- Logical departmental isolation improves security posture
- Router-controlled inter-VLAN communication limits unrestricted lateral movement
- Structured IP addressing improves scalability

---

## 10. Challenges Encountered

- Subnet mask alignment between /27 and /28 networks
- Correct trunk port identification
- Proper encapsulation configuration
- Interface state validation and troubleshooting

---

## 11. Skills Demonstrated

- VLAN implementation
- Inter-VLAN routing
- IP subnetting and address planning
- IEEE 802.1Q trunk configuration
- Router-on-a-Stick deployment
- CLI-based verification and troubleshooting
- Enterprise network documentation

---

## Repository Structure


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

End of Documentation
