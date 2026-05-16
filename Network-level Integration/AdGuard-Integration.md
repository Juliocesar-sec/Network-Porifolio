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
 
---

## Next Steps After Installation

After you have installed AdGuard Home using the script, you need to access the web interface to complete the setup and configure your network.

### 1. Find Your Server IP Address**

Before you can access AdGuard Home, you need to know the IP address of the server where it’s installed:

Linux / macOS:
Open a terminal and run:

```
ip addr show
```

Look for the IP under the active network interface (usually eth0 or wlan0).

Windows:
Open Command Prompt and run:

```
ipconfig
```

Look for the IPv4 Address of your active network connection.

### 2. Access the Web Interface

A- Open a web browser on any device connected to the same network.
B- In the address bar, enter:

```
http://<SERVER_IP>:3000
```

Replace <SERVER_IP> with the IP address you found in the previous step.

C- You will see the AdGuard Home setup wizard. Here you can:

- Set the admin email (used for login and notifications)
- Create a secure password for the web interface
- Configure basic settings for your network

### 3. Configure Network Interfaces

AdGuard Home can listen on multiple network interfaces. During the setup wizard:

- You’ll see a list of available network interfaces on your server.
- Select the interface(s) that correspond to your local network (usually the one connected to your router).
   Example: eth0 for a wired connection, wlan0 for Wi-Fi.
- You can also leave it as default (all interfaces) to cover all connections.
- Confirm your choices to let AdGuard Home start listening for DNS requests on the selected interfaces.

### 4. Finalize Setup

- Once the wizard finishes, AdGuard Home will be active and start blocking ads and trackers for devices on your network.
- You can access the dashboard anytime via:

```
http://<SERVER_IP>:3000
```
- From the dashboard, you can configure:
- Filtering rules
- Client-specific settings
- DNS forwarding and upstream servers
- Traffic statistics and logs

