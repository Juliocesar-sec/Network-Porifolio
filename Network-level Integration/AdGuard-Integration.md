# AdGuard-Integration

This repository provides a simple way to install and activate **AdGuard Home** on your server. AdGuard Home allows you to **block ads network**-wide and **monitor traffic** across all your devices.

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

-c <channel> : Use the specified release channel
-r : Reinstall AdGuard Home
-u : Uninstall AdGuard Home
-v : Enable verbose output

 Note: Options -r and -u are mutually exclusive.
 
 
