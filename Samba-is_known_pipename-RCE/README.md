# Samba is_known_pipename() RCE

## CTF Overview
- **Category:** Network Exploitation / SMB
- **Difficulty:** Medium
- **Target:** Authorized lab environment
- **Vulnerability:** CVE-2017-7494
- **Tools:** Nmap, SearchSploit, Metasploit Framework

## Objective
Identify and exploit the vulnerable Samba service in the designated CTF environment.

## Methodology
1. **Reconnaissance:** Enumerated open ports and service versions using Nmap.
2. **Vulnerability Identification:** Identified the Samba vulnerability using SearchSploit.
3. **Exploitation:** Used the relevant Metasploit module in the authorized lab.
4. **Post-Exploitation:** Verified the shell privileges.
5. **Flag Capture:** Retrieved the CTF flag.

## Root Cause
The vulnerability allows remote code execution when the required Samba share and configuration conditions are met.

## Remediation
- Upgrade Samba to a fixed version.
- Restrict guest and anonymous write access to SMB shares.
- Avoid exposing writable shares.
- Run services with least privilege.
- Restrict SMB access using firewall rules.

## Evidence
See the screenshots and full report in this folder.

## Disclaimer
This write-up is for educational purposes and authorized CTF/lab environments only.
