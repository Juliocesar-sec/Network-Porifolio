# pfSense Installation on Oracle VirtualBox

**Portfolio Practice Report**  
**Student:** Juliocesar-sec
**Date:** April 11, 2026  
**Objective:** Install pfSense Community Edition (CE) 2.8.1 as a virtual machine using Oracle VirtualBox to use it as a firewall/router.

---

## Installation Step-by-Step

### Step 1 – Creating the Virtual Machine
![Creating the Virtual Machine](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_1.png)

We started the **“Create Virtual Machine”** wizard in Oracle VirtualBox Manager.  
- VM Name: `PfSens&`  
- Selected ISO: `netgate-installer-v1.1.1-RELEASE-amd64.iso`  
- Type/Subtype: **Other / Other/Unknown** (VirtualBox did not automatically detect pfSense).  
- Destination folder: `/home/debian/VirtualBox VMs`

### Step 2 – Operating System Configuration
![Operating System Configuration](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_2.png)

In the second step of the wizard, we manually configured the OS:  
- **Type**: BSD  
- **Subtype**: FreeBSD  
- **Version**: FreeBSD (64-bit)  

We clicked **Finish** to complete the virtual machine creation.

### Step 3 – Project Folder Organization
![Project Folder Organization](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_3.png)
We created a folder named **“PfSense”** inside `/home/debian/Pictures/` to organize the report screenshots.

### Step 4 – Hardware Configuration 
![Hardware Configuration](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_4.png)

In the **Hardware** step:  
- RAM: **4096 MB** (4 GB)  
- Processors: **1 CPU**  

In the **Virtual Hard Disk** step:  
- We created a new virtual disk of **21.06 GB**.

### Step 5 – Configuration Summary 
![Configuration Summary](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_5.png)
Final screen of the wizard showing the complete VM summary.  
We clicked **Finish** to create the virtual machine.

### Step 6 – Creating the Host-only Network 
![Creating the Host-only Network](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_6.png)
We created a **Host-only** network (`vboxnet0`) with the range `192.168.56.1/24` and DHCP enabled.  
This network will allow direct communication between the Debian host and the pfSense VM.

### Step 7 – Initial Network Configuration (NAT) 
![Initial Network Configuration](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_7.png)
In the VM settings (still powered off):  
- **Adapter 1** was set to **NAT** (required for the installer to download packages).

### Step 8 – Changing to Host-only Network 
![Changing to Host-only Network ](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_8.png)
We changed **Adapter 1** to **Host-only Adapter** (`vboxnet0`).  
This configuration allows access to pfSense directly via the `192.168.56.0/24` network.

### Step 9 – Starting the VM 
![Starting the VM](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_9.png)
We started the virtual machine. The pfSense loader appeared with the message “Welcome to Netgate pfSense Plus”.

### Step 10 – License Acceptance 
![License Acceptance](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_10.png)
**Copyright and Distribution Notice** screen.  
We clicked **[Accept]** to continue.

### Step 11 – Installer Main Menu 
![Installer Main Menu](https://github.com/Juliocesar-sec/Firewall/blob/ff5c6de879f8ae0ab43a9c7e1bdc2c00191844fd/PfSense/installation/ScreenShot/Screenshot_11.png)
Netgate Installer main menu:  
We selected **Install pfSense** and confirmed with **OK**.

### Steps 12 to 16 – Interface Assignment and Configuration

- We assigned the virtual interfaces (`em0` and `em1`) as WAN and LAN.
![em0 and em1](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_12.png)

- Configured WAN as DHCP client.
![Configured WAN as DHCP client](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_13.png)

- Configured LAN as Static (initially `192.168.1.1/24`, later changed).
![Configured LAN as Static](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_14.png)

- Confirmed the final interface assignment.
![Confirmed the final interface assignment](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_15.png)

### Step 17 – Installing CE Version
![Installing CE Version](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_17.png)
Since there was no pfSense Plus subscription, we selected **Install CE** (Community Edition).

### Step 18 – Version Selection 
![Version Selection](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_18.png)
We selected version **2.8.1 – Current Stable Version**.

### Step 19 – Installation Completion 
![Installation Completion](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_19.png)
The installation finished successfully, showing the message:  
**“pfSense Post Installation setup … done.”**

### Step 20 – Removing the ISO
![Removing the ISO](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_20.png)
We attempted to eject the virtual ISO. Due to an error, we used the **Force Unmount** option.

### Step 21 – Shutting Down the VM
![Shutting Down the VM](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_21.png)
The VM was paused and then powered off using the **Power off the machine** option.

### Step 22 – pfSense Console After Boot 
![pfSense Console After Boot](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_22.png)
The VM rebooted successfully and displayed the classic pfSense 2.8.1 console menu.

### Step 23 – LAN Interface Configuration via Console
![LAN Interface Configuration via Console](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_23.png)
We selected option **2** (Set interface(s) IP address) and configured the **LAN (em1)** interface with:  
**`192.168.56.2/24`**

### Step 24 – Advanced LAN Configuration 
![Advanced LAN Configuration](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_24.png)
- Subnet mask: `/24`  
- Enabled **DHCP Server** on LAN  
- DHCP range: `192.168.56.100` to `192.168.56.200`  
- Disabled IPv6 DHCP

### Step 25 – Configuration Confirmation
![Configuration Confirmation](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_25.png)
The console confirmed the changes:  
**IPv4 LAN address set to 192.168.56.2/24**  
WebConfigurator URL: `https://192.168.56.2`

### Step 26 – Accessing the WebConfigurator
![Accessing the WebConfigurator](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_26.png)
On the Debian host browser, we accessed `https://192.168.56.2` and logged in with default credentials:  
- **Username**: `admin`  
- **Password**: `pfsense`

### Step 27 – Starting the Setup Wizard
![Starting the Setup Wizard](https://github.com/Juliocesar-sec/Firewall/blob/4f3c24b188d0d6eda1c92cc87af06f2fdea8d8a4/PfSense/installation/ScreenShot/Screenshot_27.png)
pfSense automatically launched the **Setup Wizard**, displaying a welcome message and a security warning to change the default password as soon as possible.

---

## Conclusion

The installation of pfSense 2.8.1 Community Edition was successfully completed in Oracle VirtualBox.  
The virtual machine is fully operational, with the LAN interface configured at `192.168.56.2/24`, DHCP server active, and access to the WebConfigurator via the browser.

**Next Steps:**
- Change the default `admin` password
- Complete the Setup Wizard
- Configure firewall rules and NAT
- Perform connectivity and routing tests

**Status:** ✅ Installation and basic configuration completed successfully.
