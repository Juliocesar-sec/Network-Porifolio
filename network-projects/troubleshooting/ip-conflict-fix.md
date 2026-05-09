
# IP Conflict Resolution

**Overview**

This document explains how to diagnose and resolve IP address conflicts in a local network environment.

An IP conflict occurs when two devices are assigned the same IP address, causing connectivity problems and unstable communication.

---

⚠️ **Common Symptoms**

- “IP Address Conflict” warning
- Intermittent network access
- Devices disconnecting randomly
- Inability to access shared resources
- Network instability

---

#  Diagnostic Steps

**1. Identify the Affected Device**

Windows
```bash
ipconfig
```

Linux
```
ip addr
```

Record:

- IP address
- MAC address
- Network adapter

 **2. Test Connectivity**

```
ping <gateway-ip>
```

Check whether the device can communicate with the network gateway.

 **3. Verify DHCP Configuration**

Check:

- DHCP server status
- IP address range
- Reserved addresses
- Static IP assignments

 **4. Scan the Network**

Use:

```
arp -a
```

Identify duplicate IP addresses associated with different MAC addresses.


**Resolution Steps**

**Option 1: Renew IP Address**

Windows
```
ipconfig /release
ipconfig /renew
```
Linux
```
sudo dhclient -r
sudo dhclient
```

**Option 2: Assign a New Static IP**

Ensure:

- IP is outside DHCP conflict range
- Gateway and subnet mask are correct

**Option 3: Restart DHCP Service**

Restart:

- Router
- DHCP server
- Network switch (if necessary)

**Resolution Example**

Issue:
Two office computers received the same static IP address.

Cause:
Manual configuration error.

Fix:
Assigned unique IP addresses and updated DHCP reservations.

Result:
Network connectivity restored successfully.

---

## Skills Demonstrated

- DHCP Troubleshooting
- IP Address Management
- Network Diagnostics
- TCP/IP Troubleshooting
- Router Administration




