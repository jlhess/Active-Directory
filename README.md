# Active Directory: Creating a Deliberately Vulnerable Environment for Security Testing
This repository documents the creation of a weak AD environment for educational and security research purposes. The goal is to simulate common misconfigurations and vulnerabilities found in poorly secured AD environments, providing a semi-realistic playground for white-box penetration testing and attack analysis, where all relevant information about the environment is known beforehand.

# Environment
Windows 2022 Server as Domain Controller </br>
Windows 11 Workstations (2)

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

<b>CrackMapExec</b><br>
- Used for lateral movement, credential validation, and enumeration of AD environments.<br>
- Exploits weak passwords and misconfigurations to gain unauthorized access.<br>

<b>BloodHound</b><br>
- Maps AD relationships to identify attack paths.<br>
- Demonstrates how attackers escalate privileges or move laterally using misconfigured permissions.<br>

<b>Impacket</b><br>
- Provides tools for various AD exploits, such as SMB connections, Kerberos attacks, and credential dumping.
