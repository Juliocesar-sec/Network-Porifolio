## Wireshark 

**What Is Wireshark?**

 Wireshark is a free, open-source packet sniffer and protocol analyzer developed by Gerald Combs in 1998 (originally called Ethereal) and maintained by a global community of contributors.

It works by placing a network interface into promiscuous mode, allowing it to capture all packets passing through that interface — not just those addressed to the local machine. The captured packets are then decoded and displayed in a human-readable format, broken down by protocol layers.

Wireshark supports hundreds of protocols including:

- TCP / UDP / IP — core transport and network layer protocols
- HTTP / HTTPS — web traffic
- DNS — domain name resolution
- DHCP — dynamic IP address assignment
- ARP — address resolution between IP and MAC addresses
- FTP / SSH / Telnet — file transfer and remote access protocols
- ICMP — ping and network diagnostics

Wireshark runs on Windows, macOS, and Linux, making it accessible across all major operating system environments.

---

## About This Tool

 Wireshark is the world's most widely used open-source network protocol analyzer. It allows technicians, administrators, and security professionals to capture and inspect network traffic in real time — essentially letting you see exactly what is happening inside a network at the packet level.

 This document exists because understanding Wireshark is a fundamental milestone for any IT professional working with networks. Whether you are troubleshooting a connectivity issue, diagnosing a slow application, or learning how protocols work in practice, Wireshark gives you direct visibility into the data flowing through your network.

Now, back to the core question: why does Wireshark matter? Because after working with network protocols, packet analysis, and traffic inspection, we can report that:

- Network problems are far easier to diagnose when you can see the actual traffic, not just symptoms.
- Protocol analysis builds a deeper understanding of TCP/IP, DNS, HTTP, and other foundational technologies.
- Wireshark bridges the gap between theoretical networking knowledge and real-world troubleshooting.
- Security investigations often begin with packet captures — Wireshark is where patterns become visible.
- Filtering and reading packet data is a skill that directly supports roles in networking, support, and cybersecurity.
- Many certification exams and professional environments expect familiarity with packet-level analysis.

That said, a few important things about Wireshark and its use:

- Capturing traffic on networks you do not own or have permission to monitor is illegal and unethical — always capture only on authorized systems.
- Wireshark shows raw data, so understanding protocols is necessary to interpret results correctly.
- It is a diagnostic tool, not a fix — it helps identify the problem, but the solution still requires human analysis.
- Packet captures can contain sensitive information such as credentials or private data — handle captures responsibly.
- Wireshark works best when combined with solid networking fundamentals like TCP/IP and the OSI model.

Our vision is that Wireshark is not just a tool — it is a learning environment. Every packet capture is an opportunity to see networking concepts in action, making abstract protocols concrete and measurable.

---

## What Does Wireshark Do?

Wireshark performs several core functions essential to network analysis:

**Packet Capture**

Wireshark captures live network traffic from a selected interface (Ethernet, Wi-Fi, loopback, etc.) in real time. Each captured unit of data is called a packet, and Wireshark records every detail including source, destination, protocol, timing, and payload.

**Packet Inspection**

Every captured packet can be expanded to reveal its full structure across protocol layers — from the Ethernet frame at the bottom to the application data at the top. This follows the OSI model, making Wireshark an excellent hands-on tool for understanding how layers interact.

**Display Filtering**

Wireshark provides a powerful filtering language to isolate exactly the traffic you need. Examples:





