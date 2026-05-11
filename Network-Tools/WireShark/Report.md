## Wireshark Installation and Setup

# Part 1: Download and Install Wireshark

## **Step 1: Update Package Lists**

```bash
sudo apt update
```

Updated the Debian package repository information before installing Wireshark.

 ## **Step 2: Install Wireshark**

Screenshot 2 – Installing Wireshark

```
sudo apt install wireshark
```

Installed Wireshark and all required dependencies using the Debian package manager.

## **Step 3: Add User to the Wireshark Group**

Screenshot 3 – Adding User Permissions

```
sudo usermod -aG wireshark $USER
```

Added the current user to the wireshark group to allow packet capture without running as root.

