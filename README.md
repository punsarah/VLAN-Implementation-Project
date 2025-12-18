# VLAN Implementation Project

## Overview
This project demonstrates the implementation of VLANs (Virtual Local Area Networks) using **Cisco Packet Tracer**.  
It includes configuration of **access ports, trunk ports, and VLAN isolation testing** across multiple departments in a simulated network.

![Topology](Topology.PNG)
![Trunk Configuration](Trunk_Configuration.png)
![Ping Testing](VLAN_Testing.png)



---

## Objectives
- Create multiple VLANs for different departments:
  - VLAN 10 – Admin
  - VLAN 20 – Staff
  - VLAN 30 – Guests
- Assign access ports for PCs
- Configure trunk ports between switches
- Test VLAN isolation (same VLAN communication works, different VLAN fails)
- Apply security best practices (parking VLAN for unused ports)
- Save and verify configurations

---

## Devices Used
- 2 × Cisco 2960-24TT Switches
- 6 × PCs
- Copper Straight-Through cables

---

## VLAN & Port Configuration

| VLAN | Department | Switch Ports |
|------|-----------|-------------|
| 10   | Admin     | Fa0/1 – Fa0/2 |
| 20   | Staff     | Fa0/3 – Fa0/4 |
| 30   | Guests    | Fa0/5 – Fa0/6 |
| 99   | Parking   | Unused Ports |

**Trunk Port:**
- Switch1 Fa0/24 ↔ Switch2 Fa0/24

---

## IP Address Plan

| VLAN | Network | PCs |
|------|--------|----|
| 10   | 192.168.10.0/24 | Admin PCs |
| 20   | 192.168.20.0/24 | Staff PCs |
| 30   | 192.168.30.0/24 | Guest PCs |

---

## Key Commands Used
```text
enable
configure terminal
vlan 10
name Admin
exit
interface range fa0/1-2
switchport mode access
switchport access vlan 10
exit
interface fa0/24
switchport mode trunk
exit
show vlan brief
write memory

