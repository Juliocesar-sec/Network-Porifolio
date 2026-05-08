

# 🔥 **IPTABLES – Practical Guide (README)**

📌 **What is IPTABLES?**

iptables is a command-line tool in Linux used to configure firewall rules in the kernel (Netfilter).  

It allows you to control:

- Incoming traffic (**INPUT**)  
- Outgoing traffic (**OUTPUT**)  
- Routed traffic (**FORWARD**)

# 🧠 **Basic Concepts**

**🔹 Tables**  
Tables define the type of processing:

- **filter** → Access control (most commonly used)  
- **nat** → Network Address Translation (NAT)  
- **mangle** → Packet modification  

**🔹 Chains**

- **INPUT** → Packets destined for the host itself  
- **OUTPUT** → Packets leaving the host  
- **FORWARD** → Packets passing through the host (acting as a router)  

**🔹 Targets (Actions)**

- **ACCEPT** → Allow the traffic  
- **DROP** → Silently discard the packet  
- **REJECT** → Block and send a response  
- **LOG** → Log the event  

# ⚙️ **Rule Structure**

```bash
iptables -A [CHAIN] -p [PROTOCOL] --dport [PORT] -j [ACTION]
```

**Example:**

```bash
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

This allows SSH connections.

# 🚀 **Essential Commands**

**List rules:**

```bash
iptables -L -v -n
```

**Flush (clear) all rules:**

```bash
iptables -F
```

**Set default policies:**

```bash
iptables -P INPUT DROP
iptables -P OUTPUT ACCEPT
iptables -P FORWARD DROP
```

# 🔐 **Basic Security Rules**

1. **Allow loopback** (very important)

```bash
iptables -A INPUT -i lo -j ACCEPT
```

2. **Allow established and related connections**

```bash
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```

3. **Allow SSH (port 22)**

```bash
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

4. **Drop everything else**

```bash
iptables -A INPUT -j DROP
```

# 🌐 **Practical Examples with Critical Ports**

**🔸 Block Telnet (port 23)**

```bash
iptables -A INPUT -p tcp --dport 23 -j DROP
```

**🔸 Allow HTTP and HTTPS**

```bash
iptables -A INPUT -p tcp --dport 80 -j ACCEPT
iptables -A INPUT -p tcp --dport 443 -j ACCEPT
```

**🔸 Block external SMB (port 445)**

```bash
iptables -A INPUT -p tcp --dport 445 -s 192.168.0.0/16 -j ACCEPT
iptables -A INPUT -p tcp --dport 445 -j DROP
```

**🔸 Limit SSH attempts (anti brute-force)**

```bash
iptables -A INPUT -p tcp --dport 22 -m limit --limit 3/min -j ACCEPT
```

# 🛡️ **Best Practices**

- 🔒 Default policy = **DROP**  
- 🌍 Never expose unnecessary services  
- 🧠 Use IP whitelisting whenever possible  
- 🔑 Avoid password authentication (use SSH keys instead)  
- 📊 Monitor logs regularly (`/var/log/syslog` or `journalctl`)

💾 **Saving Rules**

**Debian/Ubuntu:**

```bash
iptables-save > /etc/iptables/rules.v4
```

**Restore rules:**

```bash
iptables-restore < /etc/iptables/rules.v4
```

⚠️ **Important Warnings**

- A single mistake can lock you out of your server  
- Always keep an alternative access method (console, KVM, or cloud recovery)  
- Test rules carefully before applying them in production  

📚 **Modern Alternatives**

- **nftables** → Official successor to iptables  
- **ufw** → Simplified interface (Ubuntu)  
- **firewalld** → Used in CentOS/RHEL and Fedora  

🧾 **Summary**

iptables is a powerful tool for:

- Access control  
- Attack mitigation  
- Protecting critical services  

👉 **Golden Rule:**  
**“Allow only what is necessary. Block everything else.”**
