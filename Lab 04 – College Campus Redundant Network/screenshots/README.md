# 🏫 Lab 04 – College Campus Redundant Network

## 📖 Overview

This project demonstrates the design and implementation of a redundant college campus network using Cisco Packet Tracer. The network provides secure connectivity for students, faculty, wireless users, CCTV systems, and campus servers while ensuring redundancy, scalability, and centralized management.

---

## 🖼️ Network Topology

![Network Topology](images/topology.png)

The network follows a hierarchical design consisting of Core, Distribution, and Access layers. Redundant links between switches provide fault tolerance and high availability.

---

## 🌐 VLAN Design

![VLAN Configuration](images/vlan.png)

The campus network is segmented using VLANs to improve security and reduce broadcast domains.

| VLAN | Name        | Purpose                              |
| ---- | ----------- | ------------------------------------ |
| 10   | STUDENTS    | Student Network                      |
| 20   | FACULTY     | Faculty Network                      |
| 30   | SERVER_ROOM | DHCP, DNS, Syslog and Portal Servers |
| 40   | CAMPUS_WIFI | Wireless Users                       |
| 50   | CCTV        | Surveillance System                  |
| 99   | NET_MGMT    | Network Management                   |

---

## 🔗 EtherChannel Configuration

![EtherChannel](images/etherchannel.png)

LACP EtherChannel was configured between CORE-SW1 and CORE-SW2 to provide:

* Increased bandwidth
* Link redundancy
* Load balancing
* High availability

### Verification

The EtherChannel summary confirms that both physical links are successfully bundled into Port-Channel 1.

---

## 🌲 Spanning Tree Protocol (STP)

![STP Verification](images/stp.png)

STP was implemented to prevent Layer 2 loops.

### Configuration

* CORE-SW1 → Root Primary
* CORE-SW2 → Root Secondary

### Result

The STP output confirms that CORE-SW1 is acting as the Root Bridge for the campus network.

---

## 🔄 Inter-VLAN Routing

![Inter-VLAN Routing](images/inter-vlan-routing.png)

Inter-VLAN routing was configured using SVIs on the multilayer core switch.

### Default Gateways

| VLAN | Gateway      |
| ---- | ------------ |
| 10   | 192.168.10.1 |
| 20   | 192.168.20.1 |
| 30   | 192.168.30.1 |
| 40   | 192.168.40.1 |
| 50   | 192.168.50.1 |
| 99   | 192.168.99.1 |

This allows communication between different VLANs while maintaining network segmentation.

---

## 📡 DHCP Configuration

![DHCP Verification](images/dhcp.png)

A centralized DHCP server was deployed in the Server Room VLAN.

### Features

* Automatic IP assignment
* Separate DHCP pools for each VLAN
* DHCP Relay using IP Helper Address

### Result

Clients successfully obtain IP addresses dynamically from the DHCP server.

---

## 🌍 DNS Configuration

![DNS Verification](images/dns.png)

DNS services were configured on the DHCP-DNS server.

### DNS Records

| Hostname          | IP Address    |
| ----------------- | ------------- |
| campus.edu        | 192.168.30.30 |
| portal.campus.edu | 192.168.30.30 |
| syslog.campus.edu | 192.168.30.20 |

### Result

Clients can access services using hostnames instead of IP addresses.

---

## 📶 Wireless Campus WiFi

![Wireless Connectivity](images/wireless.png)

Wireless connectivity was implemented using a WRT300N Access Point.

### Configuration

* SSID: CampusWiFi
* WPA2 Security
* Centralized DHCP Allocation

### Result

Wireless clients successfully connect and receive IP addresses from VLAN 40.

---

## 🔐 Access Control Lists (ACLs)

![ACL Verification](images/acl.png)

ACLs were implemented to enforce security policies.

### Security Rules

* Students cannot access Server VLAN.
* WiFi users cannot access Server VLAN.
* CCTV devices cannot access Server VLAN.
* Faculty maintain access to campus resources.

### Result

Unauthorized access attempts are successfully blocked.

---

## 🛡️ Port Security

![Port Security](images/port-security.png)

Port Security was configured on access ports.

### Features

* Sticky MAC Address Learning
* Maximum 1 MAC Address
* Shutdown on Violation

### Result

Unauthorized devices are prevented from accessing the network.

---

## 📋 Syslog Monitoring

![Syslog Monitoring](images/syslog.png)

A centralized Syslog server was deployed to collect logs from all switches.

### Logged Events

* Interface status changes
* Configuration changes
* VLAN events
* Port Security violations

### Result

Network events are centrally monitored for troubleshooting and auditing.

---

## 🛠️ Technologies Used

* Cisco Packet Tracer
* VLAN
* Trunking
* EtherChannel (LACP)
* Spanning Tree Protocol (STP)
* Inter-VLAN Routing
* DHCP
* DNS
* Wireless Networking
* ACL
* Port Security
* Syslog

---

## 🎯 Learning Outcomes

* Implemented a hierarchical campus network design.
* Configured VLAN segmentation and trunking.
* Deployed EtherChannel and STP redundancy.
* Enabled Inter-VLAN Routing using a Layer 3 switch.
* Implemented centralized DHCP and DNS services.
* Secured the network using ACLs and Port Security.
* Configured Wireless LAN services.
* Implemented centralized Syslog monitoring.

---

