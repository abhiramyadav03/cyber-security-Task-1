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
The screenshots included in this repository show the output of each scan performed during the task.
* Host Discovery
* Basic Port Scan
* Scan Without Ping
* Service Version Detection
* OS Detection
* Aggressive Scan
* SMB Enumeration
 ---

What I Learned
* How to discover live hosts on a network.
* How to identify open TCP ports.
* How to detect running services and their versions.
* The basics of operating system detection.
* How Nmap NSE scripts can be used for information gathering.
* The importance of performing reconnaissance before any security assessment.
---
Conclusion
This task helped me understand the fundamentals of network reconnaissance using Nmap. By performing different scan types in a virtual lab, I gained practical experience with host discovery, port scanning, service detection, operating system identification, and basic enumeration. This hands-on practice improved my understanding of how network scanning is used during security assessments.
