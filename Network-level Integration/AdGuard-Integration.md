# AdGuard-Integration

This repository provides a simple way to install and activate **AdGuard Home** on your server. AdGuard Home allows you to **block ads network**-wide and **monitor traffic** across all your devices.

AdGuard Home is a network-wide solution for blocking ads and trackers. Once set up, it protects all devices in your home without the need to install any client-side software.

It works as a DNS server, intercepting requests to tracking or ad domains and redirecting them to a “black hole,” effectively preventing your devices from connecting to those servers. AdGuard Home is built on the same robust codebase as our public AdGuard DNS servers, sharing much of the underlying technology to deliver reliable and efficient protection.

⚠️ Note: All information about installation, configuration, and advanced guides is available in the **official AdGuard Home repository**: [AdGuardHome on GitHub](https://github.com/AdguardTeam/AdGuardHome)

---

## Installation

You can install AdGuard Home using one of the following methods:

**Using `curl`**

```bash
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```
**Using wget**

```
wget --no-verbose -O - https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

**Using fetch**

```
fetch -o - https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

**Script Options**

The installation script supports the following options:

- `-c <channel>` : Use the specified release channel;
- `-r` : Reinstall AdGuard Home;
- `-u` : Uninstall AdGuard Home;
- `-v` : Enable verbose output;

 Note: Options -r and -u are mutually exclusive.
 
 
