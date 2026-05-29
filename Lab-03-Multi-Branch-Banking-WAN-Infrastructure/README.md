# 🏦 Lab 03 – Multi-Branch Banking WAN Infrastructure

## Overview

This project simulates a real-world banking enterprise network connecting Mumbai Headquarters with Pune and Nashik branch offices using OSPF dynamic routing.

The network was designed to demonstrate enterprise networking concepts including VLAN segmentation, inter-VLAN routing, centralized services, dynamic routing, and security implementation.

---

## Network Architecture

### Headquarters (Mumbai)

* Layer 3 Core Switch
* Dual WAN Routers
* DHCP/DNS Server
* Banking Portal Server
* Syslog Server
* Backup Server
* Access Switches
* IP Phones
* CCTV Infrastructure

### Branch Offices

#### Pune Branch

* Branch Router
* Access Switch
* Employee Network
* Guest WiFi
* ATM Network
* Voice Network

#### Nashik Branch

* Branch Router
* Access Switch
* Employee Network
* Guest WiFi
* ATM Network
* Voice Network

---

## Technologies Implemented

### Routing

* OSPF Area 0
* Dynamic Route Advertisement
* Redundant WAN Topology

### Switching

* VLAN Segmentation
* Trunk Links
* Inter-VLAN Routing

### Services

* Centralized DHCP Server
* DNS Server
* Banking Portal Server
* Syslog Server
* Backup Server

### Security

* ACL-Based Traffic Filtering
* Guest Network Isolation
* ATM Network Protection
* CCTV Network Segmentation

### Voice & Surveillance

* Voice VLAN
* IP Phones
* CCTV VLAN
* Security Monitoring Station

---

## VLAN Design

| VLAN | Purpose            |
| ---- | ------------------ |
| 10   | Employee           |
| 20   | Management         |
| 30   | Servers            |
| 40   | Guest WiFi         |
| 50   | Voice              |
| 60   | ATM                |
| 70   | CCTV               |
| 99   | Network Management |

---

## OSPF Design

All routers and the Layer 3 Core Switch participate in OSPF Area 0.

OSPF dynamically exchanges routing information between Mumbai HQ, Pune Branch, and Nashik Branch, ensuring automatic route learning and simplified network management.

---

## Security Policies

### Guest VLAN

* Denied access to internal enterprise resources
* Isolated from ATM and Server networks

### ATM VLAN

* Allowed access only to banking services
* Restricted from accessing user networks

### CCTV VLAN

* Dedicated surveillance network
* Isolated from employee devices

---

## Validation Performed

* OSPF Neighbor Verification
* Dynamic Route Learning
* Inter-VLAN Connectivity
* DHCP Relay Functionality
* DNS Resolution
* Banking Portal Access
* Syslog Monitoring
* ACL Enforcement Testing

---

## Skills Demonstrated

* Enterprise Network Design
* OSPF Routing
* VLAN Configuration
* DHCP Relay
* Network Segmentation
* ACL Implementation
* Syslog Monitoring
* Cisco Packet Tracer

---

## Future Enhancements

* HSRP Gateway Redundancy
* NTP Centralized Time Synchronization
* AAA Authentication
* Site-to-Site VPN
* SNMP Monitoring
* Firewall Integration
