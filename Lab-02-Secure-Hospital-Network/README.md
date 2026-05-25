# Lab 02 — Secure Hospital Network Infrastructure

## Scenario

A Pune-based hospital required a secure and scalable enterprise network infrastructure with departmental segmentation, centralized services, wireless guest access, IP telephony, and access control policies.

The objective of this lab was to simulate a real-world healthcare network using Cisco Packet Tracer while implementing enterprise-grade security and communication architecture.

---

# Technologies Implemented

- VLAN Segmentation
- Inter-VLAN Routing
- Layer 3 Switching
- DHCP Server
- DHCP Relay (IP Helper Address)
- DNS Server
- HTTP Server
- Voice VLAN
- IP Phones
- Wireless Access Point
- Extended ACL Security
- Trunking
- Redundant Backup Server Design

---

# Network Architecture

## Core Layer
- Cisco 3560 Multilayer Switch

## Access Layer
- Critical Department Access Switch
- Public Department Access Switch

## Server Infrastructure
- Primary Hospital Server
- Backup Server

---

# VLAN Plan

| VLAN | Name | Purpose | Network |
|------|------|----------|----------|
| 10 | RECEPTION | Reception Department | 192.168.10.0/24 |
| 20 | DOCTORS | Doctors Department | 192.168.20.0/24 |
| 30 | PHARMACY | Pharmacy Department | 192.168.30.0/24 |
| 40 | GUEST_WIFI | Guest Wireless Network | 192.168.40.0/24 |
| 50 | VOICE | IP Phones | 192.168.50.0/24 |
| 99 | SERVER | Server Infrastructure | 192.168.99.0/24 |

---

# Key Features

## Departmental Segmentation
Each department was isolated using VLANs to improve:
- security
- scalability
- broadcast management

---

## Voice Infrastructure
IP Phones were deployed for:
- Doctors
- Pharmacy
- Reception

A dedicated Voice VLAN was implemented to separate voice traffic from data traffic.

---

## Guest Wireless Access
A dedicated Access Point was configured for guest wireless users using VLAN 40.

Guest traffic was isolated from internal hospital infrastructure using ACL security policies.

---

## Centralized Services
The primary server provided:
- DHCP
- DNS
- HTTP Services

A backup server was included to simulate enterprise redundancy and service continuity.

---

# ACL Security Policies

## Guest VLAN Restrictions
Guest users were denied access to:
- internal VLANs
- server infrastructure
- voice VLAN

---

## Reception Restrictions
Reception users were allowed access only to:
- DNS services
- internal hospital portal

Direct access to server infrastructure was restricted.

---

## Doctors VLAN
Doctors were granted full access to hospital resources and services.

---

# Hospital Portal

A DNS and HTTP server was configured to host an internal healthcare portal.

Accessible using:

www.punehospital.local

---

# Enterprise Concepts Demonstrated

- Hierarchical Network Design
- Enterprise VLAN Architecture
- Voice and Data Integration
- Secure Wireless Segmentation
- Centralized Services
- ACL-Based Traffic Control
- DHCP Relay Operations
- Enterprise Redundancy Concepts

---

# Verification & Testing

- Successful DHCP IP Allocation
- Inter-VLAN Routing Verification
- DNS Resolution Testing
- Internal Web Portal Access
- ACL Restriction Validation
- Guest Isolation Testing
- Voice VLAN Verification

---

# Screenshots

## Network Topology
(Add topology screenshot here)

## DHCP Verification
(Add DHCP screenshot here)

## Voice VLAN Configuration
(Add IP phone screenshot here)

## ACL Testing
(Add ACL verification screenshot here)

## Hospital Web Portal
(Add website screenshot here)

---

# Learning Outcome

This lab provided practical understanding of how healthcare organizations implement secure enterprise networking using VLAN segmentation, centralized services, IP telephony, wireless access control, and ACL-based security enforcement.
