# Active Directory: Creating a Deliberately Vulnerable Environment for Security Testing
This repository documents the creation of a weak AD environment for educational and security research purposes. The goal is to simulate common misconfigurations and vulnerabilities found in poorly secured AD environments, providing a semi-realistic playground for white-box penetration testing and attack analysis, where all relevant information about the environment is known beforehand.

# Environment
Windows 2022 Server as Domain Controller </br>
Windows 11 Workstations (2)<br>
Kali Linux as Attack Box

# Features
<b>Weakened Password Policies:</b></br>
- Disables password complexity (PasswordComplexity = 0).</br>
- Sets minimum password length to 1 character.</br>
- Demonstrates the risks of poor password hygiene.

<b>Over-Privileged Accounts:</b></br>
- Administrative users with unnecessary domain-wide privileges.</br>
- Low-privilege users granted local admin rights on multiple machines.

<b>Misconfigured Group Memberships:</b></br>
- Users added to groups that don’t align with the principle of least privilege.

# Tools Used
<b>PowerShell</b><br>
- Automates the setup and management of the AD environment.<br>
- Creates users, groups, and applies misconfigurations (e.g., weak password policies).<br>
- Scripts used found in code directory. 

<b>CrackMapExec</b><br>
- Used for lateral movement, credential validation, and enumeration of AD environments.<br>
- Exploits weak passwords and misconfigurations to gain unauthorized access.<br>

<b>BloodHound</b><br>
- Maps AD relationships to identify attack paths.<br>
- Demonstrates how attackers escalate privileges or move laterally using misconfigured permissions.<br>

<b>Impacket</b><br>
- Provides tools for various AD exploits, such as SMB connections, Kerberos attacks, and credential dumping.

# Attack Outputs and Visuals
<h3>CrackMapExec</h3>
<b>Bruteforce Passwords</b><br><br>
<img src="https://i.imgur.com/UJ4KuV3.png" height="60%" width="60%" alt="Bruteforce Passwords"/><br>
<b>Extract Password Policy</b><br><br>
<img src="https://imgur.com/az5qlOY.png" height="60%" width="60%" alt="Password Policy"/>
<h3>Impacket</h3>
<b>Shell on DC and Displaying Priviliges for Local Admin Account</b><br><br>
<img src="https://imgur.com/KcXq7zO.png" height="60%" width="60%" alt="Shell"/>
<h3>Bloodhound</h3>
<b>Mapping Shortest Path to Domain Admins</b><br><br>
<img src="https://imgur.com/aDcCd0h.png" height="60%" width="60%" alt="Domain Admins"/><br>
<b>Principals with DCSync Rights</b><br>
<img src="https://imgur.com/vPeczit.png" height="60%" width="60%" alt="DCSync Rights"/><br>
