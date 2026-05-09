
# DNS Troubleshooting Guide

## Overview

This document covers common DNS (Domain Name System) issues encountered in network environments and the troubleshooting steps used to resolve them.

DNS problems can prevent users from accessing websites and network services even when internet connectivity is available.

---

⚠️ **Common Symptoms**

- Websites do not load
- “DNS Server Not Responding” message
- Ping works with IP addresses but not domain names
- Slow website access
- Intermittent internet connectivity

---

# Diagnostic Steps

 1. **Check Internet Connectivity**

Test basic connectivity:

```bash
ping 8.8.8.8
```
If the ping succeeds, the internet connection is working.


2. **Test DNS Resolution**
   
```
nslookup google.com
```
or 

```
ping google.com
```
If domain names fail to resolve, DNS may be misconfigured.

3. **Verify DNS Server Settings**
 
Windows
```
ipconfig /all
```

Check:

- DNS server addresses
- Default gateway
- Network adapter configuration

Linux
```
cat /etc/resolv.conf
```

4. **Flush DNS Cache**
 
Windows
```
ipconfig /flushdns
```

Linux
```
sudo systemd-resolve --flush-caches
```

5. **Restart Network Services**

Restart:

- Router
- DNS service
- Network adapter

**Common Solutions**

-Configure public DNS servers:
   8.8.8.8
   1.1.1.1
- Restart router
- Renew IP configuration
- Clear DNS cache
- Disable problematic VPNs or proxies

---

**Resolution Example**

Issue:
Users could access websites using IP addresses but not domain names.

Cause:
Incorrect DNS server configured on the router.

Fix:
Updated DNS configuration to Google DNS (8.8.8.8).

Result:
Normal internet access restored.

---

**Skills Demonstrated**

- DNS Troubleshooting
- TCP/IP Diagnostics
- Network Configuration
- Command-Line Troubleshooting
- Connectivity Testing





