# 🔥 FIREWALL 🔥

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

## 🌐 DNS / Name Resolution (Port 53/tcp)

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

⚠️**Risks:**

* DNS Spoofing / Cache Poisoning

→ Attackers manipulate DNS responses to redirect victims to malicious sites.
DDoS Amplification

→ DNS servers are abused to amplify attacks against third parties.
Unauthorized Zone Transfer

→ Leakage of the entire domain structure and internal records.

***🛡️ Protection with Firewall:***

Allow DNS traffic only to trusted servers
Block unnecessary external queries
Monitor for anomalous DNS traffic

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
## 📁 FILE SHARING

```bash
🔸 21/tcp – FTP
```

***⚠️ Risks:***

Clear-text login
Malware uploads

***🛡️ Protection:***

Avoid → use SFTP instead
Block public access
```
🔸 445/tcp – SMB (Highly Critical 🚨)
```
 ⚠️ **Risks:**

Ransomware (e.g., WannaCry)
Remote Code Execution (RCE)

***🛡️ Protection:***

# ❌ Never expose to the internet

Allow only on internal networks
```
🔸 2049/tcp – NFS
```
 ⚠️ **Risks:**

Unauthorized directory access
Privilege escalation

***🛡️ Protection:***

Restrict by IP
Configure exports properly

# 🗄️ DATABASES

```bash
🔸 3306 – MySQL
🔸 5432 – PostgreSQL
🔸 6379 – Redis
🔸 27017 – MongoDB
```
 ⚠️ **Common Risks:**

Databases exposed to the internet
Weak passwords
Lack of authentication

***🛡️ Protection:***

❌ Never make them public

Allow access only from internal network or VPN
Firewall should block everything by default

## ⚙️ SYSTEM SERVICES

```
🔸 111/tcp – rpcbind
```

 ⚠️ **Risks:**

Service enumeration
Exposure of internal information

***🛡️ Protection:***

Block external access
Allow only trusted hosts
```
📡 UDP / NETWORK DISCOVERY.
🔸 1900/udp – SSDP / UPnP
```

⚠️ **Risks:**

DDoS amplification
Device exposure

***🛡️ Protection:***

Disable UPnP when possible
Block at the network edge
```
🔸 5353/udp – mDNS
```
**⚠️ Risks:**

Local information leakage
Spoofing

***🛡️ Protection:***

Limit to local network only
Block on public networks


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
