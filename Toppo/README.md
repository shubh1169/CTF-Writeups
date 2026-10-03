# Toppo — VulnHub Boot-to-Root

## Overview

This write-up documents my penetration-testing practice on the **Toppo VulnHub virtual machine** in an isolated lab environment.

The objective was to enumerate the target, obtain initial access, escalate privileges, and achieve root access.

## Target Information

* **Machine:** Toppo
* **Platform:** VulnHub
* **Environment:** Isolated Lab
* **Attacking Machine:** Kali Linux
* **Target:** Toppo VM

## Attack Methodology

The assessment followed these stages:

1. Host Discovery
2. Port and Service Enumeration
3. Web Enumeration
4. Directory Discovery
5. Sensitive File Discovery
6. SSH Initial Access
7. SUID Enumeration
8. Privilege Escalation
9. Root Access

## Attack Chain

```text
Host Discovery
      ↓
Nmap Port Scan
      ↓
Web Enumeration
      ↓
Gobuster Directory Discovery
      ↓
/admin/ Directory
      ↓
notes.txt
      ↓
SSH Access
      ↓
SUID Python 2.7
      ↓
Privilege Escalation
      ↓
Root Access
```

## Tools Used

* arp-scan
* Nmap
* Gobuster
* SSH
* Linux privilege-enumeration techniques

## Proof of Exploitation

Screenshots documenting the major stages of the attack are available in the [`screenshots`](./screenshots/) directory.

### Key Evidence

* Target discovery
* Open-port enumeration
* Web directory discovery
* Sensitive file discovery
* SSH access
* SUID Python discovery
* Root access
* Flag capture

## Full Report

The complete penetration-testing report is available here:

**[Toppo CTF Penetration Testing Report](./Toppo_CTF_Report.pdf)**

## Disclaimer

This assessment was performed against an intentionally vulnerable VulnHub machine in an authorized isolated laboratory environment for cybersecurity education and practice.
