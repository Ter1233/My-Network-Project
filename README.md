# Enterprise Network Infrastructure Lab (IPv4 / IPv6)

This project is a comprehensive **enterprise network simulation** built using Cisco Packet Tracer.
The goal of this lab is to practice real-world networking concepts including **routing, switching, network segmentation, redundancy, and security implementation**.

The topology simulates **multiple office branches connected through routers and central switches**, implementing both **IPv4 and IPv6 dual-stack networking**.

---

# Network Topology

## Core Network Topology

![Core Network](docs/core-network-topology.png)

---

## Security / DHCP / VLAN Lab

![Security Lab](docs/security-lab-topology.png)

---

## Multi-Office Enterprise Network

![Enterprise Network](docs/enterprise-network-topology.png)

---

# Network Design Overview

This network includes several enterprise-level networking components:

• Multiple branch offices
• Core switching infrastructure
• VLAN segmentation
• Layer 2 and Layer 3 security mechanisms
• Dynamic routing protocols
• IPv4 / IPv6 dual-stack implementation

---

# Technologies Implemented

## IPv4 & IPv6 Networking

All routers are configured with:

• IPv4 addressing
• IPv6 addressing
• Dual-stack networking

Network addressing uses:

• **Subnetting**
• **VLSM (Variable Length Subnet Mask)**

---

# Routing Configuration

## OSPF & OSPFv3

Dynamic routing protocols used:

• **OSPF (IPv4)**
• **OSPFv3 (IPv6)**

Configuration includes:

• Multiple areas

* Area 0
* Area 1

• Passive interfaces
• Point-to-point links
• DR / BDR priority configuration
• Loopback interfaces used for router IDs

---

## Static Routing

Additional routing features:

• Floating static routes
• Backup path configuration

---

# VLAN Segmentation

Network segmentation is implemented using VLANs.

Examples:

• VLAN 100 — User network
• VLAN 200 — Admin network
• VLAN 101 — Office2 network
• VLAN 201 — Office2 accounting network

---

# Trunking

Switch-to-switch and switch-to-router connections use:

**IEEE 802.1Q trunking**

Security improvement:

• Native VLAN modified

---

# Router on a Stick (ROAS)

Inter-VLAN routing is implemented using:

• Router subinterfaces
• VLAN tagging (802.1Q)

This allows communication between VLANs and shared services.

---

# DHCP Configuration

DHCP is configured to dynamically assign IP addresses.

Features implemented:

• DHCP pools for each office
• DHCP relay for VLAN networks

DHCP deployed in:

• Office 1
• Office 2
• Office 3

---

# Network Security Features

## Port Security

Access switch ports are protected using:

• Maximum MAC address = **2**
• Sticky MAC learning
• Violation mode: **restrict**

Purpose:

Prevent unauthorized devices from connecting to the network.

---

## DHCP Snooping

DHCP Snooping protects the network from rogue DHCP servers.

Configuration includes:

• Trusted ports
• Untrusted ports

---

## Dynamic ARP Inspection (DAI)

DAI protects against **ARP spoofing attacks**.

ARP packets are validated using DHCP Snooping bindings.

---

## BPDU Guard & PortFast

Switch ports use:

• PortFast
• BPDU Guard

Configured on:

```
FastEthernet0/3
FastEthernet0/4
```

Purpose:

Prevent rogue switches from causing spanning-tree topology changes.

---

# Spanning Tree

Switches use:

**Rapid Spanning Tree Protocol (RSTP)**

Benefits:

• Faster convergence
• Loop prevention
• Network redundancy

---

# EtherChannel

EtherChannel is configured between switches for:

• Link aggregation
• Higher bandwidth
• Redundancy

Configured on:

• Central switch
• Office2 switches

---

# NAT Implementation

## PAT (Port Address Translation)

Configured in:

**Office 1**

Allows multiple internal hosts to share a single public IP.

---

## Dynamic NAT

Configured in:

**Office 2**

Maps private addresses dynamically to public addresses.

---

# Access Control Lists (ACL)

ACL rules are implemented on:

**Office3 Router**

Purpose:

• Traffic filtering
• Access control between networks

---

# Network Management

## SSH / Telnet

Remote device management configured on all routers.

Configuration includes:

• SSH access
• Telnet access
• Local authentication
• RSA key generation (1024 bit)

---

## SNMP

Simple Network Management Protocol configured on all routers.

Permissions:

• RO — Read Only
• RW — Read Write

Used for network monitoring.

---

## NTP

Network Time Protocol is used to synchronize time across devices.

---

# Switch Features

Switches include configuration for:

• VLAN segmentation
• Trunking
• EtherChannel
• Rapid Spanning Tree
• DHCP Snooping
• Dynamic ARP Inspection
• Port Security

---

# Discovery Protocol

Switches use:

**LLDP (Link Layer Discovery Protocol)**

Used for discovering neighboring network devices.

---

# Key Networking Concepts Demonstrated

This lab demonstrates practical implementation of:

• Enterprise network design
• VLAN segmentation
• Inter-VLAN routing
• Routing protocols (OSPF / OSPFv3)
• IPv4 / IPv6 networking
• Layer 2 security mechanisms
• NAT and ACL implementation
• Network redundancy and high availability

---

# Tools Used

• Cisco Packet Tracer
• Cisco IOS CLI

---

# Author

Ter1233
