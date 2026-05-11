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


![1Step 1](https://github.com/Juliocesar-sec/Network-Portfolio/blob/78a0051631f8675373576585329c5e69bae96c02/Network-Tools/WireShark/Screenshot/wireshark_2.png)
 
So after adding the group, you must either:

- Log out and log back in, or
- Reboot 

---

##  **Part 2: Capture and Analyze Local ARP Data in Wireshark**

In this part of the lab, Wireshark is used to capture and analyze ARP (Address Resolution Protocol) traffic on the local network. The goal is to observe how devices resolve IP addresses into MAC addresses when communicating on a LAN.

## **Step 1: Retrieve your PC’s interface addresses.**

For this lab, you will need to retrieve your PC’s IPv4 address and the MAC address. 

### **1A: Identify IP and MAC Address (Debian 13)**

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

### **1B – Identify Active Network Interface**
Screenshot 27 – Active Network Interface

Identified the active network interface being used to access the network.

### **2C – Record IPv4 and MAC Address**
Screenshot 28 – IPv4 and MAC Address

![2Step 1](https://github.com/Juliocesar-sec/Network-Portfolio/blob/fa8b82c2980a60d5258ecfea3dd005463502e3ab/Network-Tools/WireShark/Screenshot/wirewshark_3.png)

## **Step 2 — Start Wireshark and Capture ARP Traffic**

### **2A — Launch Wireshark**

Wireshark was launched from the Debian application menu.

After opening the application, the active network interface identified earlier (enp0s3 or wlan0) was selected for packet capture.

### **2B — Configure ARP Packet Filter**

To capture only ARP traffic, the following display filter was entered into the Wireshark filter bar:

```
arp
```
After selecting the correct interface and applying the ARP filter, packet capture was started by clicking the Start Capturing Packets button (shark fin icon).

This configuration allows Wireshark to display only ARP packets exchanged between devices on the local network.

![2Step 2B](https://github.com/Juliocesar-sec/Network-Portfolio/blob/4547f5f7268dc441dbe5239a53ce8dcf78047477/Network-Tools/WireShark/Screenshot/wireshark_4.png)

**Observations**

Once the capture began, live network traffic started appearing in the packet list pane.
Each entry represented communication between source and destination devices on the LAN.


### **2C — Test Connectivity to the Default Gateway***

To generate ARP traffic, connectivity to the default gateway was tested using the ping command.

```
ping 192.168.1.1
Example Output
PING 192.168.1.1 (192.168.1.1) 56(84) bytes of data.
64 bytes from 192.168.1.1: icmp_seq=1 ttl=64 time=2.1 ms
64 bytes from 192.168.1.1: icmp_seq=2 ttl=64 time=1.8 ms
64 bytes from 192.168.1.1: icmp_seq=3 ttl=64 time=2.0 ms
64 bytes from 192.168.1.1: icmp_seq=4 ttl=64 time=1.9 ms
```

The successful replies confirmed network connectivity between the PC and the default gateway.

**ARP Activity**

During the ping process, Wireshark captured ARP request and ARP reply packets used to resolve the MAC address associated with the gateway’s IPv4 address.

![Step 2C](https://github.com/Juliocesar-sec/Network-Portfolio/blob/292f4370b54d4b21b595dd5d98c535505def45e9/Network-Tools/WireShark/Screenshot/wireshark_5.png)

### **2D — Ping Other PCs on the LAN**

To generate additional ARP traffic, the IPv4 addresses of other PCs on the local network were pinged.

Example command:

```
ping 192.168.1.x
```

Example Output:

```
PING 192.168.1.x (192.168.1.x) 56(84) bytes of data.
64 bytes from 192.168.1.x: icmp_seq=1 ttl=64 time=1.2 ms
64 bytes from 192.168.1.x: icmp_seq=2 ttl=64 time=1.0 ms
64 bytes from 192.168.1.x: icmp_seq=3 ttl=64 time=1.1 ms
```

The successful replies confirmed connectivity between devices on the same LAN.

**ARP Activity Observed**

While the ping command was running, Wireshark captured additional ARP request and ARP reply packets between the local devices.

These packets showed how the system resolved the IPv4 addresses of neighboring hosts into their corresponding MAC addresses before communication could occur.

If a device did not respond to the ping requests, this was likely caused by firewall settings blocking ICMP traffic.

## **2E — Stop Packet Capture**

After generating and analyzing the ARP traffic, packet capturing was stopped in Wireshark.

This was done by clicking the Stop Capture button (red square icon) located on the Wireshark toolbar.

Stopping the capture finalized the packet collection and preserved the captured ARP traffic for analysis.

![Step 2D](https://github.com/Juliocesar-sec/Network-Portfolio/blob/553b1d13a3eba1fae1f1cd32ead7d4e1ac959665/Network-Tools/WireShark/Screenshot/wireshark_6.png)

## **Step 3: Examine the Captured Data**

In this step, the data generated by the ping requests was examined using Wireshark. The captured traffic was analyzed through the three primary Wireshark panes.

Wireshark displays captured network traffic in three sections:

1. **Packet List Pane**  
   Displays a summary of all captured PDU frames, including source and destination addresses, protocol type, and packet details.

2. **Packet Details Pane**  
   Displays detailed protocol information for the selected frame and separates the captured PDU into protocol layers.

3. **Packet Bytes Pane**  
   Displays the raw packet data in both hexadecimal and ASCII/decimal representation.


### **3A — Analyze the ARP Request Frame**

An ARP frame was selected in the top section of Wireshark where:

- The PC MAC address appeared as the **Source**
- The destination appeared as **Broadcast**

This frame represented the ARP Request being sent to all devices on the LAN.

### ARP Request Analysis

The selected frame showed the following:

| Field | Description |
|---|---|
| Destination MAC | `ff:ff:ff:ff:ff:ff` (Broadcast) |
| Source MAC | MAC address of the local PC |
| Protocol | ARP |
| ARP Opcode | Request |

The ARP request was broadcast because the sender did not yet know the MAC address associated with the destination IPv4 address.

![Step 3A – ARP Request](INSERT_SCREENSHOT_HERE)


### **3B — Examine Ethernet II Header Information**

With the ARP request frame still selected, the **Ethernet II** section in the middle pane was expanded.

The Ethernet II header displayed:

- **Destination MAC Address** → Broadcast address
- **Source MAC Address** → MAC address of the local PC

### Ethernet II Observations

| Ethernet II Field | Value |
|---|---|
| Destination | Broadcast (`ff:ff:ff:ff:ff:ff`) |
| Source | Local PC MAC Address |
| Type | ARP |

The Ethernet II header provides Layer 2 addressing information used for communication on the local network.

![Step 3B – Ethernet II Header](INSERT_SCREENSHOT_HERE)

### **3C — Examine the ARP Request Contents**

The **Address Resolution Protocol (request)** section was expanded in the middle pane to inspect the contents of the ARP request.

The ARP request contained:

| Field | Description |
|---|---|
| Sender MAC Address | MAC address of the local PC |
| Sender IP Address | IPv4 address of the local PC |
| Target MAC Address | Unknown (`00:00:00:00:00:00`) |
| Target IP Address | IPv4 address being resolved |

**ARP Request Behavior**

The ARP request asks:

```text
Who has <Target IP Address>?
Tell <Sender IP Address>
```

This allows devices on the LAN to determine which host owns the requested IPv4 address.

![Step 3C – ARP Request Details](INSERT_SCREENSHOT_HERE)


## **Step 4: Locate the ARP Response Frame**

The ARP reply frame corresponding to the ARP request was then located in the packet list.

The ARP reply was sent directly back to the requesting device using unicast communication.

### ARP Reply Analysis

The ARP response contained:

| Field | Description |
|---|---|
| Source MAC Address | MAC address of the responding device |
| Destination MAC Address | MAC address of the local PC |
| Sender IP Address | IPv4 address being resolved |
| Protocol | ARP Reply |

The ARP reply informed the sender of the correct MAC address associated with the requested IPv4 address.

![Step 4 – ARP Reply Frame](INSERT_SCREENSHOT_HERE)

---

## **Part 3: Examine the ARP Cache Entries on the PC**

After receiving the ARP reply, the MAC-to-IP address mapping was temporarily stored in the ARP cache of the operating system.

These entries remain cached for a short period of time before being removed if they are no longer used.

### 3A — View the ARP Cache Table (Debian 13)

On Debian/Linux systems, the ARP cache can be viewed using the following command:

```bash
ip neigh
```

Example Output:

```text
192.168.1.1 dev wlan0 lladdr 00:11:22:33:44:55 REACHABLE
192.168.1.10 dev wlan0 lladdr aa:bb:cc:dd:ee:ff STALE
192.168.1.15 dev wlan0 lladdr 12:34:56:78:90:ab DELAY
```

**ARP Cache Observations**

The output displays:

- IPv4 addresses discovered on the LAN
- Associated MAC addresses
- Network interface being used
- Current ARP neighbor state

### Neighbor States

| State | Description |
|---|---|
| REACHABLE | Device is reachable and recently contacted |
| STALE | Entry exists but has not been recently verified |
| DELAY | Waiting before verifying connectivity |
| FAILED | Address resolution failed |

The dynamically learned entries remain cached temporarily before expiring if unused.

![Step 5A – ARP Cache Table](INSERT_SCREENSHOT_HERE)

---

### **3B — View Additional ARP/Neighbor Command Options**

Additional options for the `ip neigh` command can be viewed using:

```bash
ip neigh help
```

This utility allows administrators to:

- View neighbor cache entries
- Add static neighbor entries
- Delete entries
- Troubleshoot Layer 2 connectivity issues

Example commands:

```bash
ip neigh show
ip neigh flush all
```

![Step 5B – Neighbor Command Help](INSERT_SCREENSHOT_HERE)
