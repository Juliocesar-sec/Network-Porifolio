
## 🔥 UFW – Practical Guide (README)

📌 **What is UFW?**

UFW (Uncomplicated Firewall) is a tool that simplifies the use of iptables on Linux.  

👉 **It was created to make firewall configuration easier, especially on distributions like Ubuntu.**

🎯 **Why Use UFW?**

- ✅ Much simpler than iptables  
- ⚡ Quick and easy configuration  
- 🔐 Ideal for servers and desktops  
- 📦 Already installed on many Linux distributions  

⚙️ **Basic Concepts**

UFW works with simple rules:

- **allow** → permit traffic  
- **deny** → block traffic silently  
- **reject** → block and send a response  
- **limit** → limit connections (anti brute-force)  

# 🚀 Essential Commands

**Enable the firewall:**

```bash
sudo ufw enable
```

**Disable the firewall:**

```bash
sudo ufw disable
```

**Check status:**

```bash
sudo ufw status verbose
```

## 🔐 Recommended Initial Configuration

Set default policies:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

👉 **This means:**
- Block everything trying to enter  
- Allow everything going out  

## 🛡️ Basic Rules

**Allow SSH (port 22)**

```bash
sudo ufw allow 22/tcp
```

**Allow HTTP/HTTPS**

```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

**Block Telnet (port 23)**

```bash
sudo ufw deny 23/tcp
```

**Allow DNS**

```bash
sudo ufw allow 53
```

## 🌐 Security-Focused Examples (Based on Critical Ports)

**🔸 SSH (22) – Protect against brute-force**

```bash
sudo ufw limit 22/tcp
```

**🔸 SMB (445) – Allow only on local network**

```bash
sudo ufw allow from 192.168.0.0/16 to any port 445
sudo ufw deny 445
```

**🔸 FTP (21) – Avoid exposure**

```bash
sudo ufw deny 21/tcp
```

**🔸 Database (e.g., MySQL 3306)**

```bash
sudo ufw allow from 192.168.0.10 to any port 3306
```

## 📍 Rules by IP

**Allow a specific IP:**

```bash
sudo ufw allow from 192.168.1.100
```

**Block a specific IP:**

```bash
sudo ufw deny from 10.0.0.5
```

## 🔍 Rule Management

**List rules with numbers:**

```bash
sudo ufw status numbered
```

**Delete a rule:**

```bash
sudo ufw delete [number]
```

# 📊 Logs

**Enable logging:**

```bash
sudo ufw logging on
```

Logs are stored in:

```bash
/var/log/ufw.log
```

⚠️ **Important Warnings**

- ❗ Always allow SSH **before** enabling UFW  
- ❗ You can lock yourself out of remote access if configured incorrectly  
- ❗ Always test in a controlled environment first  

🧠 **Best Practices**

- 🔒 Use a restrictive default policy  
- 🌐 Avoid exposing services directly to the internet  
- 🔑 Use VPN for sensitive access  
- 📉 Keep the number of open ports to a minimum  
- 📊 Monitor logs frequently  

### 🔄 UFW vs IPTABLES

| Feature          | UFW                  | IPTABLES                  |
|------------------|----------------------|---------------------------|
| Ease of Use      | ⭐⭐⭐⭐⭐ (Very Easy)   | ⭐⭐ (Advanced)            |
| Control Level    | Medium               | Advanced                  |
| Best For         | Simple / Quick setups| Advanced / Professional   |

### 📚 Extra Useful Commands

**Reset everything:**

```bash
sudo ufw reset
```

**Allow a range of ports:**

```bash
sudo ufw allow 1000:2000/tcp
```

**Allow on a specific interface:**

```bash
sudo ufw allow in on eth0 to any port 22
```

# 🧾 Summary

UFW is ideal for:

- 🖥️ Quick firewall administration  
- 🔐 Basic to intermediate protection  
- 🚀 Fast and secure server deployments  

👉 **Golden Rule:**  
**“Open only what is necessary — everything else should remain blocked.”**

