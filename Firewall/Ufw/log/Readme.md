
## Ufw-colorlog

***🛡️ Advanced UFW Color Log***

A lightweight utility that transforms technical UFW (Uncomplicated Firewall) logs into a colorful, easy-to-audit real-time feed in your Debian/Ubuntu terminal.

***✨ What does this script do?***

The UFW Color Log automates the configuration of detailed system logging and creates a smart alias that filters and colors terminal output according to event severity:
```
-🔴 Red: Intrusion attempts, blocked packets (BLOCK, DENIED, DROP).
-🚨 Critical Alert: Highlights attempts on sensitive ports (SSH, RDP, FTP, SQL).
-🔵 Blue: Successfully allowed connections (ALLOW).
-🟡 Yellow: Quick identification of source IPs (SRC).
-⚪ Gray: Other kernel informational events.
```
## 🚀 How to install on your Debian/Ubuntu

Just follow the three steps below in your terminal:

***1. Clone and prepare***
```bash
git clone https://github.com/Juliocesar-sec/ufw-colorlog.git
cd ufw-colorlog
chmod +x ufw-colorlog.sh
```
***2. Run the installer***

The script will enable full UFW logging, install the ccze colorizer, and configure the alias in your .bashrc.
```bash
./ufw-colorlog.sh
```
***3. Activate the changes***

To make the command work immediately in the current terminal session, run:
```bash
source ~/.bashrc
```
## 🛠️ How to use

After installation, you no longer need long commands. Just type:
```bash
ufw-colorlog
```
Note: Since the script reads Kernel logs (journalctl -k), it will request your sudo password to ensure data security.

***📋 System requirements***

```
Operating System: Debian, Ubuntu (or derivatives)
Firewall: UFW installed and enabled (sudo ufw enable)
Dependencies: ccze (installed automatically by the script) and awk
```
