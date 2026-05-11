# 🦈  Wireshark Installation and Setup 🦈 

## Part 1: Download and Install Wireshark

Wireshark has become the industry standard packet-sniffer program used by network engineers. This open source software is available for many different operating systems, including Windows, Mac, and Linux.

If Wireshark is already installed on your PC, you can skip Part 1 and go directly to Part 2. If Wireshark is not installed on your PC, check with your instructor about your academy’s software download policy. 

## **Step 1: Update Package Lists**

```bash
sudo apt update
```

Updated the Debian package repository information before installing Wireshark.

 ### **1A: Install Wireshark**

```
sudo apt install wireshark
```

Installed Wireshark and all required dependencies using the Debian package manager.

![Install Wireshark](https://github.com/Juliocesar-sec/Network-Portfolio/blob/704f001e867143531e43e1e8fa4b32e17a0ced57/Network-Tools/WireShark/Screenshot/wireshark_1.png)

### **1B: Add User to the Wireshark Group**

Screenshot 3 – Adding User Permissions

```
sudo usermod -aG wireshark $USER
```

Added the current user to the wireshark group to allow packet capture without running as root.


### **1C: Apply Group Changes**

Screenshot 4 – Applying Group Membership

```
newgrp wireshark
```

Applied the new group permissions in the current terminal session.


### **1D: Verify Wireshark Installation**

Screenshot 5 – Verifying Installation

```
wireshark --version
```

Verified that Wireshark 4.4.15 was successfully installed.


![Step 1](https://github.com/Juliocesar-sec/Network-Portfolio/blob/78a0051631f8675373576585329c5e69bae96c02/Network-Tools/WireShark/Screenshot/wireshark_2.png)

---

##  **Part 2: Capture and Analyze Local ARP Data in Wireshark**

In this part of the lab, Wireshark is used to capture and analyze ARP (Address Resolution Protocol) traffic on the local network. The goal is to observe how devices resolve IP addresses into MAC addresses when communicating on a LAN.

## **Step 1: Identify IP and MAC Address (Debian 13)**

Before capturing traffic, the PC’s network information is required.

```bash
ip a
```

This command displays the network interfaces, IPv4 address, and MAC (link-layer) address of the system.

Example Output (Recorded Information)

```
IPv4 Address: 192.168.x.x
MAC Address: xx:xx:xx:xx:xx:xx
Interface: enp0s3 / wlan0 (depends on system)
```


