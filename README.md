Cyber Security Task 1 – Nmap Network Scanning

Overview
In this task, I explored the basics of network scanning using Nmap on a virtual lab environment created with **VMware Workstation**. I used a Kali Linux machine to scan an Ubuntu system connected to the same network. The goal of this task was to understand how Nmap works, identify live hosts, discover open ports, detect running services, and perform basic enumeration.

Lab Setup
* Attacker Machine:** Kali Linux
* Target Machine:** Ubuntu
* Virtualization:** VMware Workstation
* Tool Used:** Nmap 7.99

Commands I Used
1. Host Discovery
```bash
nmap -sn 192.168.x.x/24
```
This command was used to identify active devices on my local network without scanning ports. It helped me find which systems were online.
---
2. Basic Port Scan
```bash
nmap 192.168.x.x
```
I used this command to scan the target machine for open TCP ports. It showed the commonly open ports and the services running on them.
---
3. Scan Without Ping
```bash
nmap -Pn 192.168.x.x
```
This scan treats the target as online even if it does not respond to ping requests. It is useful when ICMP is blocked by a firewall.
---
4. Service Version Detection

```bash
nmap -sV 192.168.x.x
```
This command identified the versions of services running on the open ports. It provided more detailed information about the target system.
---
5. OS Detection
```bash
nmap -O 192.168.x.x
```
I used this command to identify the operating system of the target machine based on TCP/IP fingerprinting.
---
6. Aggressive Scan
```bash
nmap -A 192.168.x.x
```
This command combines OS detection, version detection, default NSE scripts, and traceroute. It provides a more complete picture of the target.
---
7. SMB Enumeration
```bash
nmap --script smb-os-discovery 192.168.x.x
```
This NSE script was used to gather SMB-related information such as the operating system, NetBIOS name, and workgroup details.
---
Screenshots

The following screenshots show the commands executed and the results obtained during the network scanning task.

* Host Discovery
Host discovery scan to identify active devices on the local network.

* Basic Port Scan
Basic TCP port scan to identify open ports on the target host.

* Scan Without Ping
Performed a scan without host discovery to scan the target directly.

* Service Version Detection
Detected the services running on open ports along with their versions.

* OS Detection
Attempted to identify the operating system of the target machine.

* Aggressive Scan
Performed an aggressive scan that combines OS detection, version detection, script scanning, and traceroute.

* SMB Enumeration
Used an NSE script to collect SMB-related information such as the operating system, NetBIOS name, workgroup, and SMB service details.

* Wireshark Packet Capture
Captured and analyzed the network traffic generated during the Nmap scan using Wireshark. The capture shows TCP SYN packets, responses from the target host, and other packets exchanged during the scanning process. This helped me understand how Nmap performs port scanning at the packet level.

What I Learned
* How to discover active hosts on a network.
* How to identify open TCP ports.
* How to detect running services and their versions.
* How operating system detection works in Nmap.
* How to use NSE scripts for SMB information gathering.
* How to analyze Nmap-generated network traffic using Wireshark.
* The importance of reconnaissance before performing a security assessment.

Conclusion

This task helped me understand how to use Nmap for different types of network scanning in a virtual lab environment. I learned how to discover live hosts, identify open ports, detect running services and operating systems, and gather SMB information using NSE scripts. I also used Wireshark to observe the packets generated during the scan, which gave me a better understanding of how Nmap communicates with the target machine. Overall, this project improved my practical knowledge of network reconnaissance and basic security assessment techniques.
