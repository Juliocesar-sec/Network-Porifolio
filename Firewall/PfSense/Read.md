Here's the clean, natural, and well-formatted English translation:

---

🔥 **pfSense – Practical Guide (README)**

📌 **What is pfSense?**

pfSense is an open-source firewall and router based on FreeBSD.  

👉 It is used for:

- Protecting networks  
- Controlling traffic  
- Creating VPNs  
- Monitoring network activity  

It can run on:

- Physical servers  
- Virtual machines (VMs)  
- Dedicated appliances  

🎯 **Why Use pfSense?**

- 🛡️ Advanced enterprise-grade firewall  
- 🌐 User-friendly web interface  
- 🔐 Excellent VPN support (OpenVPN, IPsec, WireGuard)  
- 📊 Real-time monitoring  
- 🔌 Package system (Snort, Squid, pfBlockerNG, etc.)  

🧠 **Basic Concepts**

**🔹 Interfaces**

- **WAN** → Internet connection  
- **LAN** → Internal network  
- **OPT** → Optional interfaces (DMZ, VLANs, guest networks, etc.)  

**🔹 Firewall Rules**  
Rules are applied per interface.  

👉 Common examples:
- Allow LAN → Internet  
- Block WAN → LAN (default behavior)  

**🔹 NAT (Network Address Translation)**  
Allows multiple internal devices to share a single public IP address.

⚙️ **Main Features**

🔐 **Stateful Firewall**  
- Tracks the state of connections  
- Automatically allows legitimate return traffic  

🌐 **VPN**  
- Secure remote access  
- Site-to-site connections between offices  

📡 **IDS/IPS (via packages)**  
- Detects attacks  
- Blocks intrusions  

📊 **Monitoring**  
- Detailed logs  
- Real-time traffic graphs  
- Connection statistics and alerts  

🚀 **Installation (Quick Summary)**

1. Download the ISO from the official website  
2. Install on a physical machine or virtual machine  
3. Configure interfaces (WAN/LAN)  
4. Access the web interface:

```
https://192.168.1.1
```

🔐 **Recommended Initial Setup**

1. Change the default password  
   - Default user: **admin**  

2. Configure DNS  
   - Use trusted DNS servers (e.g., Cloudflare 1.1.1.1 or Google 8.8.8.8)  

3. Update the system  
   - Always keep pfSense up to date  

🛡️ **Basic Security Rules**

🔸 **Block everything from WAN** (Default rule – very important)  
🔸 **Allow LAN → Internet** (So internal users can browse normally)  
🔸 **Port Forwarding** (Open specific ports)  
   Example: Expose an internal web server  
   - WAN port 80 → Internal server IP  

🌐 **Security Based on Critical Ports**

🔸 **DNS (53)**  
   - Allow only to trusted DNS servers  
   - Avoid open resolvers  

🔸 **SSH (22)**  
   - Restrict by IP or  
   - Prefer using VPN instead of direct exposure  

🔸 **Telnet (23)**  
   - ❌ **Block completely**  

🔸 **SMB (445)**  
   - ❌ **Never expose on WAN**  

🔸 **Databases (3306, 5432, etc.)**  
   - ❌ Only allow from internal network or VPN  

🔸 **UPnP (1900/udp)**  
   - ⚠️ Disable whenever possible  

📁 **Advanced Features**

🔹 **VLANs**  
   - Network segmentation (e.g., IT, Guests, IoT)  

🔹 **Captive Portal**  
   - Login page for public Wi-Fi  

🔹 **Traffic Shaping (QoS)**  
   - Bandwidth control and prioritization  

🔹 **High Availability (HA)**  
   - Failover between two pfSense devices  

📦 **Useful Packages**

- **Snort / Suricata** → IDS/IPS  
- **pfBlockerNG** → IP blocking and ad blocking  
- **Squid** → Web proxy and caching  
- **OpenVPN / WireGuard** → VPN solutions  

📊 **Monitoring and Logs**

- Firewall logs  
- Traffic graphs per interface  
- Active connections  
- System alerts  

⚠️ **Important Warnings**

- ❗ A wrong configuration can take down your entire network  
- ❗ Exposing ports incorrectly is extremely risky  
- ❗ Always make backups of your configuration  

🧠 **Best Practices**

- 🔒 Principle of least privilege  
- 🌐 Use VPN for remote access  
- 🚫 Minimize open ports  
- 📊 Monitor logs constantly  
- 🔄 Keep the system updated regularly  

🔄 **pfSense vs UFW vs IPTABLES**

| Feature              | pfSense                  | UFW                    | IPTABLES                  |
|----------------------|--------------------------|------------------------|---------------------------|
| Graphical Interface  | ✅ Yes                   | ❌ No                  | ❌ No                     |
| Ease of Use          | ⭐⭐⭐⭐⭐ (Very Easy)      | ⭐⭐⭐⭐⭐                | ⭐⭐ (Advanced)            |
| Power / Flexibility  | ⭐⭐⭐⭐⭐ (Enterprise)     | ⭐⭐⭐ (Medium)         | ⭐⭐⭐⭐⭐ (Maximum)         |
| Best For             | Full networks, companies| Single servers         | Advanced Linux servers    |

🧾 **Summary**

pfSense is a complete solution for:

- 🔥 Enterprise-grade firewall  
- 🌐 Routing  
- 🔐 VPN  
- 🛡️ Advanced threat protection  

👉 Ideal for:

- Companies  
- Cybersecurity labs  
- Advanced home labs  

🧑‍💻 **Author**  
Introductory guide for studies in Networking, Security, and Infrastructure.

---

Would you like me to create a combined comparison guide for **iptables + UFW + pfSense** or explain any specific section (like how to set up VPN or port forwarding in pfSense) in more detail? Just let me know!
