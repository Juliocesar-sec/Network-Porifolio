#  VLAN Setup Lab

**Overview**

This project demonstrates the configuration and implementation of VLANs (Virtual Local Area Networks) using Cisco networking devices in a simulated environment.

The purpose of this lab is to improve network organization, security, and traffic management by separating departments into different VLANs.

---

#  Objectives

- Create and configure VLANs
- Assign switch ports to VLANs
- Configure trunk ports
- Test VLAN communication
- Improve network segmentation
- Practice basic switch administration

---

#  Network Structure

The lab environment includes:

- 1 Cisco Switch
- Multiple PCs
- VLAN segmentation by department
- Trunk configuration for VLAN traffic

---

#  Files Included

| File | Description |
|------|-------------|
| `vlan-config.txt` | VLAN configuration commands |
| `diagram.png` | VLAN network diagram |
| `README.md` | Project documentation |

---

#  VLAN Design

| VLAN ID | Department | Network |
|---|---|---|
| 10 | Administration | 192.168.10.0/24 |
| 20 | Sales | 192.168.20.0/24 |
| 30 | IT Support | 192.168.30.0/24 |

---

#  Configuration Tasks

## VLAN Creation
- Created VLAN 10
- Created VLAN 20
- Created VLAN 30

## Port Assignment
- Assigned switch ports to specific VLANs
- Configured access ports

## Trunk Configuration
- Enabled trunking between switches
- Allowed VLAN traffic across trunk links

---

#  Testing Performed

The following tests were completed:

- VLAN verification
- Device communication within VLANs
- VLAN isolation testing
- Trunk port validation
- IP connectivity testing

---

#  Benefits of VLANs

- Improved network organization
- Reduced broadcast traffic
- Better security separation
- Easier network management
- Department segmentation

---

#  Skills Demonstrated

- VLAN Configuration
- Switch Administration
- Cisco CLI
- Network Segmentation
- TCP/IP Configuration
- Basic Network Security

---

# 📌 Notes

This lab was created using Cisco Packet Tracer for educational and portfolio purposes to demonstrate practical networking fundamentals.

---
