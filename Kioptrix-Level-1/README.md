# Kioptrix Level 1 — Penetration Testing Lab

## Overview

This project documents a hands-on penetration testing assessment performed against **Kioptrix: Level 1**, an intentionally vulnerable virtual machine provided by **VulnHub**.

The assessment was performed in an isolated lab environment using Kali Linux and followed a structured penetration testing methodology from reconnaissance through exploitation, post-exploitation, and remediation.

## Objective

The objective of this assessment was to:

- Identify the target system
- Discover exposed services and ports
- Enumerate running services
- Identify known vulnerabilities
- Exploit a viable vulnerability
- Obtain root-level access
- Validate the impact of the compromise
- Document security recommendations

## Lab Environment

| Item | Details |
|---|---|
| Target | Kioptrix Level 1 |
| Platform | VulnHub |
| Attacker Machine | Kali Linux |
| Assessment Type | Black-box |
| Network | Isolated Lab Environment |
| Objective | Obtain root-level access |

## Methodology

The assessment followed these phases:

1. Pre-Engagement
2. Reconnaissance
3. Scanning & Enumeration
4. Vulnerability Identification
5. Exploitation
6. Post-Exploitation
7. Reporting & Remediation

## Tools Used

- Nmap
- Nikto
- smbclient
- Searchsploit / Exploit-DB
- Metasploit Framework
- Kali Linux

## Reconnaissance

The target was discovered on the local lab network using network reconnaissance techniques.

The identified target was:

`10.124.239.63`

## Scanning & Enumeration

A full TCP port scan was performed using Nmap to identify open ports and running services.

The assessment identified services including:

- SSH
- HTTP
- HTTPS
- RPC
- SMB

The target was running several outdated software versions.

## Web Server Assessment

Nikto was used to assess the web server and identify outdated components and configuration weaknesses.

The assessment identified:

- Outdated Apache
- Outdated mod_ssl
- Outdated OpenSSL
- HTTP TRACE enabled
- Directory indexing
- Expired SSL certificate

## SMB Enumeration

SMB enumeration identified:

**Samba 2.2.1a**

The Samba version was investigated using Searchsploit.

The assessment identified the **trans2open** vulnerability associated with:

**CVE-2003-0201**

## Exploitation

The identified Samba vulnerability was tested in the isolated lab environment using the Metasploit Framework.

The relevant Metasploit module was:

`exploit/linux/samba/trans2open`

After configuring the target and payload, exploitation successfully resulted in an interactive shell.

## Root Access

The obtained shell was verified using:

`whoami`

The result confirmed:

`root`

This demonstrated that successful exploitation resulted in root-level access to the vulnerable machine.

## Post-Exploitation

After obtaining root access, post-exploitation activities were performed to demonstrate the impact of the compromise.

Activities included:

- Verifying root privileges
- Reviewing the filesystem
- Reviewing the `/root` directory
- Reviewing system mail
- Examining information accessible with root privileges

## Key Findings

### 1. Vulnerable Samba Service

Samba 2.2.1a was identified as vulnerable to the trans2open remote buffer overflow.

**CVE:** CVE-2003-0201

**Impact:** Root-level remote compromise in the lab environment.

### 2. Outdated Web Stack

The target was running legacy versions of Apache, mod_ssl and OpenSSL.

### 3. Legacy SSH Configuration

The target was running an outdated OpenSSH version with SSHv1 support.

### 4. Web Server Misconfiguration

HTTP TRACE and directory indexing were enabled.

### 5. Expired SSL Certificate

An expired SSL certificate was identified during the web server assessment.

## Remediation Recommendations

- Upgrade Samba to a supported version.
- Restrict SMB access at the network layer.
- Disable legacy SMB protocols.
- Upgrade Apache to a supported version.
- Upgrade OpenSSL and mod_ssl.
- Disable SSHv1 and use SSHv2.
- Replace expired SSL/TLS certificates.
- Disable HTTP TRACE.
- Disable directory indexing.
- Maintain regular security patching and vulnerability management.



This project was performed exclusively against an intentionally vulnerable **VulnHub Kioptrix Level 1** virtual machine in an isolated laboratory environment.

The techniques documented in this repository are provided for authorized security testing, education, and cybersecurity training purposes.
