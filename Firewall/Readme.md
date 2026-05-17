#  FIREWALL 

![Firewall](https://img.shields.io/badge/Firewall-Network%20Protection-red?style=for-the-badge&logo=pfsense&logoColor=white)
![pfSense](https://img.shields.io/badge/pfSense-Security%20Gateway-212121?style=for-the-badge&logo=pfsense&logoColor=white)
![UFW](https://img.shields.io/badge/UFW-Uncomplicated%20Firewall-orange?style=for-the-badge&logo=ubuntu&logoColor=white)
![iptables](https://img.shields.io/badge/iptables-Linux%20Firewall-blue?style=for-the-badge&logo=linux&logoColor=white)

**What is a Firewall?**

A firewall is a security system, implemented through software, hardware, or both, designed to control network traffic by allowing or blocking connections according to predefined security rules.

It acts as a protective barrier between trusted systems and external networks, monitoring data as it enters or leaves a device or infrastructure.

This technology exists because modern computer networks are constantly exposed to unwanted traffic, unauthorized access attempts, malware, and malicious activity. A firewall helps reduce these risks by enforcing controlled communication policies.

Now, back to firewalls. Why are they considered one of the most fundamental components of network security? Because after decades of real-world use across servers, companies, and personal systems, we can report that:

* Firewalls help prevent unauthorized access to systems and services.
* They allow administrators to control which ports, protocols, and applications can communicate.
* They reduce exposure to malicious traffic and automated attacks.
* They provide visibility into network activity through logging and monitoring.
* They are essential for both enterprise infrastructure and personal devices.
* They work as a first layer of defense in cybersecurity architectures.
* They help enforce security policies consistently across networks.

That said, a few important things about firewalls:

* A firewall does not make a system automatically secure; it is one part of a larger security strategy.
* Incorrect firewall rules can accidentally block legitimate traffic or expose services unintentionally.
* Firewalls can operate at different layers of the network stack depending on their design and complexity.
* Modern systems may use both software firewalls and dedicated hardware appliances together.
* Security rules should be regularly reviewed and updated as network requirements evolve.

A useful way to understand a firewall is to imagine it as a gatekeeper or security guard for your network.

👉 **It works like a “bouncer” or gatekeeper for your network:**

It decides who can enter Decides who can leave Filters what is safe versus what is suspicious:

* Who can enter
* Who can leave
* Which traffic is safe
* Which traffic appears suspicious or unauthorized

Our vision is that understanding firewalls should start with understanding traffic control itself. Network security is not only about blocking connections, but about deciding clearly and intentionally how systems are allowed to communicate.

---

##  Importance in IT and Cybersecurity

A firewall is considered one of the first and most important layers of defense in modern IT infrastructure. Its primary role is to control how systems communicate with external networks, reducing unnecessary exposure and enforcing security policies.

In both enterprise and personal environments, firewalls help protect devices, services, and sensitive data from unauthorized access and malicious traffic.

Main functions include:

```
.🔐 Block unauthorized access;
.🌍 Control internet traffic;
.🛡️ Reduce the attack surface;
.📊 Monitor suspicious activity;
.🚫 Prevent exploitation of ports and services.
```
These protections are essential because many attacks begin through exposed network services, misconfigured ports, or unrestricted traffic.

That said, a firewall should not be viewed as a complete security solution by itself. It works best when combined with:

* System updates
* Strong authentication
* Network monitoring
* Antivirus and endpoint protection
* Secure configuration practices

👉 **Without a firewall, a system or network becomes significantly more exposed to unauthorized connections, automated scans, and external attacks.**

---

##  DNS / Name Resolution (Port 53/tcp)

 **What is DNS?**

DNS (Domain Name System) is a core internet service responsible for translating human-readable domain names into IP addresses that computers can understand and use for communication.

For example:
```bash
google.com → 142.250.x.x
```
This process allows users to access websites and online services using simple names instead of memorizing numerical IP addresses.

DNS exists because modern networks are built around machine-level addressing, while humans naturally prefer readable and recognizable names.

Now, back to DNS. Why is it considered one of the most essential parts of the internet? Because after decades of global internet usage, we can report that:

* DNS makes the internet easier and more practical for humans to use.
* It allows websites and services to change IP addresses without requiring users to remember new numbers.
* It enables scalable communication across billions of devices and services.
* It helps route traffic efficiently between users and online resources.
* It supports modern services such as websites, email systems, cloud platforms, and streaming applications.
* Nearly every internet connection depends on DNS resolution before communication begins.
* Without DNS, internet navigation would become significantly more difficult and less accessible.
  
That said, a few important things about DNS:

* DNS does not store websites themselves; it only helps locate them.
* DNS queries are usually one of the first steps performed when accessing an online service.
* Slow or misconfigured DNS servers can affect browsing performance and connectivity.
* DNS can also become a target for attacks, monitoring, or traffic manipulation if not secured properly.
* Modern systems may use encrypted DNS technologies to improve privacy and security.

A simple way to understand DNS is to imagine it as the phonebook of the internet.

It takes a name people understand:
```
google.com
```
and translates it into a machine-readable address:
```
142.250.x.x
```
Our vision is that understanding networking starts with understanding how systems locate each other. DNS exists because communication on the internet depends on translating human-friendly names into precise network destinations.

⚠️**Common DNS Security Threats:**

DNS is a critical part of internet infrastructure, which also makes it a frequent target for attackers. When DNS is misconfigured or not properly secured, it can be exploited in different ways to redirect traffic, leak sensitive data, or amplify attacks.

**DNS Spoofing / Cache Poisoning**

Attackers manipulate or corrupt DNS responses so that users are redirected to malicious or fake websites without realizing it.

This type of attack works by injecting false DNS records into a resolver’s cache, causing future requests to return incorrect IP addresses.

→ Attackers manipulate DNS responses to redirect victims to malicious sites.
Impact:

* Users may be redirected to phishing sites
* Credentials can be stolen
* Legitimate services may be impersonated

***DDoS Amplification***

→ DNS servers are abused to amplify attacks against third parties.DNS servers can be abused to increase the scale of Distributed Denial of Service (DDoS) attacks.

Attackers send small queries that trigger much larger responses, which are then directed toward a victim system.

Impact:

* Massive traffic overload on target systems
* Service downtime or instability
* Infrastructure resource exhaustion

***Unauthorized Zone Transfer***

→ Leakage of the entire domain structure and internal records.Zone transfers are used to copy DNS records between servers. If improperly secured, attackers can request full zone transfers and obtain the entire DNS structure of a domain.

This may expose internal naming conventions and infrastructure details.

Impact:

* Exposure of internal hostnames and services
* Mapping of network architecture
* Increased risk of targeted attacks

DNS security is important because DNS operates as a foundational lookup system for almost all internet communication. If compromised, it can silently redirect, expose, or disrupt large parts of network activity without immediately obvious signs.

***🛡️ Protection with Firewall:***

Firewalls can play an important role in reducing DNS-related attacks by controlling how DNS traffic is allowed, restricted, and monitored within a network.

Because DNS is a fundamental service used in almost every internet request, securing it helps prevent redirection attacks, data leaks, and abuse of network infrastructure.

***Allow DNS traffic only to trusted servers***

A firewall can be configured to permit DNS queries only to known and trusted DNS resolvers (for example, internal company servers or reputable public resolvers).

This reduces the risk of:

* Malicious DNS redirection
* Unauthorized resolvers intercepting queries
* Data leakage through unknown DNS servers

***Block unnecessary external queries***

Firewalls can restrict outbound DNS traffic so that internal devices cannot freely query any external DNS server.

This helps prevent:

* Devices bypassing security policies
* Malware using external DNS for communication
* Hidden or unauthorized DNS tunneling

***Monitor for anomalous DNS traffic***

Firewall logging and inspection features can be used to detect unusual DNS behavior, such as:

* Excessive DNS requests in a short time
* Queries to suspicious or unknown domains
* Repeated failed lookups
* Unusual outbound DNS destinations
  
  This kind of monitoring helps identify early signs of:

* DNS tunneling attempts
* Compromised devices
* Misconfigured systems or malicious activity
  
A properly configured firewall does not just block threats, it also provides visibility. In the case of DNS, this visibility is critical for detecting abnormal patterns before they escalate into larger security incidents.

---

##  REMOTE ACCESS

***What is Encrypted Remote Access (SSH)?***

SSH is a secure protocol that lets you remotely connect to a server or computer over the internet or a network.
It creates an encrypted tunnel between your device (client) and the remote server. This means:
```
. Everything you type (commands, passwords during setup, file transfers) is encrypted.

. Attackers who intercept the traffic (e.g., on public Wi-Fi or by eavesdropping) cannot read your data or steal your credentials easily.
```
Unlike Telnet (port 23), which sends everything in plain text (very dangerous), SSH protects your session with strong encryption (like AES).

***Why do we use it?***

System administrators, developers, and IT professionals use SSH to:
```
. Manage Linux/Unix servers remotely;
. Run commands;
. Transfer files securely (with SCP or SFTP);
. Troubleshoot and maintain systems from anywhere.
```
***Why You Must Be Careful When Using SSH***

Even though SSH is encrypted and considered secure, it is one of the most attacked services on the internet. Here's why you still need to be very careful:
```
. Brute-force attacks: Hackers constantly scan the internet for servers with port 22 open and try thousands of username/password combinations automatically.

. If misconfigured, SSH can become a gateway for attackers to take full control of your server (install malware, steal data, use it for further attacks, or ransomware).

. Weak passwords, exposed ports, or poor key management are common reasons servers get hacked.

. Once an attacker logs in as a privileged user, they can do almost anything on that machine.
```
Bottom line: SSH is safe only if configured properly. Default settings are often not secure enough for exposure to the public internet.

***How to Use SSH Correctly and Securely (Best Practices)***

Here’s a clear, practical guide to using SSH the right way:

***1. Never use passwords for login (if possible)***
```
. Use SSH Key Authentication instead.
. Generate a key pair (private key on your computer, public key on the server).
. This is much stronger than any password.
```
***2. Disable password authentication completely***

In the server’s SSH config file (/etc/ssh/sshd_config), set:
```
PasswordAuthentication no
PubkeyAuthentication yes
```
***3.Disable direct root login***
```
PermitRootLogin no
```
(Always log in as a normal user, then use sudo when needed.)

***4. Restrict access with a firewall***
```
. Do not open port 22 to the entire internet.
. Use IP whitelisting: Allow SSH only from your home IP, office IPs, or trusted addresses.
. Better option: Put SSH behind a VPN — never expose it directly to the public internet.
```
***5.Change the default port (optional but helpful)***

Change from 22 to something like 2222 or 2244 to reduce automated bot scans.

***6. Add extra layers of security:***
```
. Enable Fail2Ban or similar tools to automatically block repeated failed login attempts.
. Use two-factor authentication (2FA/MFA) with tools like Google Authenticator.
. Set idle timeout: Automatically disconnect inactive sessions.
. Keep your SSH software updated.
```
***7. Protect your private key:***
```
. Never share your private key.
. Use a strong passphrase to protect it.
. Store it securely (not in cloud sync folders without protection).
```
***8. General rules:***
```
. Follow the principle of least privilege: Give users only the access they need.
. Monitor SSH logs regularly for suspicious activity.
. For high-security environments, use advanced tools like Teleport, Bastion hosts, or Zero Trust solutions instead of direct SSH.
```

***⚠️ Risks:***

Brute-force attacks
Weak passwords
Poor key management

***🛡️ Protection:***

Block unrestricted external access
Use IP whitelisting
Prefer key-based authentication (instead of passwords)

```
🔸 23/tcp – Telnet (Insecure 🚨)
```
Does not use encryption

***⚠️ Risks:***

Credentials sent in plain text
Session hijacking

***🛡️ Protection:***

 ❌ Block completely in the firewall
Replace with SSH
```
🔸 5900/tcp – VNC
```
Graphical remote desktop access

### ⚠️ Risks:

Weak passwords
No encryption (in older versions)

***🛡️ Protection:***

Use over VPN
Restrict by IP
Enable encryption

* You can learn more about this lab here:
  
```
https://github.com/Juliocesar-sec/cybersecurity-learning-portfolio/tree/main/labs/ssh-lab

```
---

##  FILE SHARING

File sharing services are commonly used in networks to transfer data between systems, but they are also frequent targets for attackers due to exposed ports and legacy protocols.

Proper firewall configuration and service hardening are essential to reduce exposure.

🔸 **21/tcp – FTP (File Transfer Protocol)**

FTP is an older file transfer protocol used to upload and download files between clients and servers.

⚠️ Risks:

* Clear-text authentication (username and password are not encrypted)
* Data transmitted without encryption
* Vulnerable to credential interception
* Common target for automated malware uploads and brute-force attacks

🛡️ Protection:

* Avoid FTP whenever possible
* Use SFTP (SSH File Transfer Protocol) instead
* Block public access to port 21 using firewall rules
* Restrict access to trusted internal networks only
* Disable anonymous login if FTP must be used

🔸 **445/tcp – SMB** (Highly Critical 🚨)

SMB (Server Message Block) is used for Windows file sharing, printer sharing, and network resource access.

It is a powerful protocol but also one of the most frequently exploited services in enterprise and home networks.

 ⚠️ Risks:

* High exposure to ransomware attacks (e.g., lateral movement across networks)
* Remote code execution vulnerabilities in outdated SMB versions
* Credential theft and pass-the-hash attacks
* Network-wide propagation of malware
* Exposure of shared files and system resources if misconfigured

🛡️ Protection:

* Block SMB (port 445) from public internet access
* Disable SMBv1 (legacy and insecure version)
* Restrict SMB access to trusted internal networks only
* Use firewall rules to limit host-to-host communication
* Enable SMB encryption (SMBv3 where possible)
* Regularly patch operating systems and services
  
File sharing services should never be exposed directly to the internet without strict controls. In most secure environments, they are tightly restricted, monitored, and only accessible within controlled network segments.

🔸 **2049/tcp – NFS (Network File System)**

NFS (Network File System) is a protocol used mainly in Linux/Unix environments to share directories across a network, allowing remote systems to mount and access file systems as if they were local.

It is widely used in servers, virtualization environments, and internal infrastructure where centralized storage is required.

 ⚠️ Risks:
 
* Unauthorized directory access if exports are misconfigured
* Exposure of sensitive files to unintended hosts
* Privilege escalation through weak permission settings
* Network sniffing or interception in poorly secured environments
* Potential lateral movement if an attacker gains access to shared mounts
 
🛡️ Protection:

* Restrict access by IP address or trusted subnets only
* Properly configure /etc/exports with strict permissions
* Use root_squash to prevent root-level remote privileges
* Avoid exporting sensitive directories unnecessarily
* Use firewall rules to block external access to port 2049
* Monitor mount activity and access logs regularly

  NFS is highly efficient for internal file sharing, but it must be tightly controlled. In secure environments, it is typically restricted to internal networks only, with strict export rules and firewall filtering to prevent unauthorized access.
  
  ---

#  DATABASES

Database services are critical components of modern applications. They store structured and unstructured data used by websites, applications, and internal systems. Because they often contain sensitive information, they must be tightly secured and never exposed unnecessarily.

```bash
🔸 3306 – MySQL
🔸 5432 – PostgreSQL
🔸 6379 – Redis
🔸 27017 – MongoDB
```

These ports correspond to widely used database systems:

* MySQL → relational database system
* PostgreSQL → advanced relational database system
* Redis → in-memory key-value store
* MongoDB → NoSQL document database

 ⚠️ **Common Risks:**
 
* Databases exposed directly to the internet
* Weak or default passwords
* Missing or misconfigured authentication
* Unauthorized remote connections
* Data leakage or full database dumps
* Brute-force attacks on database credentials
* Misconfigured access control rules

When databases are exposed, attackers often scan for open ports and attempt automated exploitation.

***🛡️ Protection:***

* Never expose database ports publicly on the internet
* Allow access only from:
  1- Internal network segments
  2- Trusted application servers
  3- Secure VPN connections
* Configure firewall rules to block all external access by default
* Enforce strong authentication and role-based access control
* Disable remote root or admin access where possible
* Regularly update database software to patch vulnerabilities
* Monitor logs for unusual queries or connection attempts
  
Database security follows a simple principle: if a database does not need to be public, it should never be reachable from the public internet. Most secure architectures place databases in private networks behind firewalls, accessible only through controlled application layers.

  ---

##  SYSTEM SERVICES

System services often run in the background to support networking, device discovery, and remote procedure calls. While useful in internal environments, many of these services can become security risks if exposed externally.

Proper firewall configuration is essential to ensure these services remain accessible only where they are actually needed.

🔸 **111/tcp – rpcbind**

rpcbind is a service used by Remote Procedure Call (RPC) systems to map network services to ports. It is commonly found in Unix/Linux environments and is often associated with NFS and legacy distributed systems.

 ⚠️ Risks:

Service enumeration
Exposure of internal information

🛡️ Protection:

Block external access
Allow only trusted hosts

 **UDP / NETWORK DISCOVERY.**

 Network discovery protocols are used to automatically detect devices and services on a local network. While convenient, they are not designed for exposure to untrusted networks.

🔸 **1900/udp – SSDP / UPnP**

SSDP (Simple Service Discovery Protocol) is part of UPnP (Universal Plug and Play), used for automatic device discovery and configuration.

⚠️ Risks:

* DDoS amplification attacks
* External device and service exposure
* Unauthorized network discovery
* Misuse of open UPnP services on routers or IoT devices

🛡️ Protection:

* Disable UPnP when it is not strictly required
* Block UDP port 1900 at the network edge (firewall/router)
* Avoid exposing SSDP services to the internet
* Regularly audit network devices that enable UPnP



🔸 5353/udp – mDNS (Multicast DNS)

mDNS is used for local network name resolution and service discovery without a central DNS server. It is commonly used in home networks and local device ecosystems.

⚠️ Risks:

* Local network information leakage
* Device and service enumeration
* Potential spoofing or rogue responses
* Exposure of hostnames and internal services

🛡️ Protection:

* Restrict mDNS traffic to local network only
* Block UDP 5353 on public or untrusted networks
* Segment networks to limit broadcast scope
* Monitor for unusual multicast traffic patterns

System discovery and RPC services are designed for convenience in trusted environments, not for open network exposure. In secure network designs, they are typically restricted to internal segments, filtered by firewalls, and disabled when not required.

---

# 🧠 IMPORTANT SUMMARY

👉  **In cybersecurity, the golden rule is:**

```bash
“If it doesn’t need to be open → it should be closed.”
```

The firewall helps you:

Reduce exposure
Control critical ports
Prevent automated attacks

🛡️ **GENERAL BEST PRACTICES**

1 .🔒 Principle of least privilege

2 .🌐 Use VPN for remote access

3 .🚫 Block all unnecessary ports

4 .🔑 Use strong authentication

5 .📊 Monitor logs continuously
