# 🖥️ System Hacking
System hacking is the process of gaining unauthorized access to computer systems to steal data, control the system, or cause damage. Ethical hackers and penetration testers perform system hacking in a legal and controlled way to find weaknesses before real attackers do. This helps organizations fix security issues and protect their systems from being hacked by malicious users.

# 🔑 Gaining Access
Gaining access in system hacking means breaking into a computer or system by using stolen passwords, exploiting software bugs, or tricking users. The goal is to take control of the system so the hacker can view, change, or steal data. It's one of the key steps in hacking after finding system weaknesses.

## Cracking Passwords
Explanation of the three Microsoft authentication mechanisms:

1. **Security Accounts Manager (SAM) Database**: This is a database on Windows systems that stores usernames and hashed passwords for local user accounts. It’s used to verify login attempts on the same computer. The SAM file is stored at `%SystemRoot%\system32\config\SAM` in Windows systems, and Windows mounts it in the registry under the `HKEY_LOCAL_MACHINE\SAM` registry hive. It stores LM or NTLM hashed passwords.


2. **NTLM Authentication**: NTLM (NT LAN Manager) is an older Windows authentication method that uses a challenge-response system to prove your identity without sending your password directly. It’s less secure and more vulnerable to attacks.

3. **Kerberos Authentication**: A modern and secure authentication method that uses tickets and a trusted third party (Key Distribution Center) to verify identities. It’s faster and more secure than NTLM, and it's the default in most Windows networks today.

---
![NTLMHash](https://github.com/user-attachments/assets/743328ba-8306-4a27-afa1-bbfe76b902b5)
---

## Tools to Extract the Password Hashes 
The following tools can be used to extract the password hashes from the target system:

### pwdump7 
🔗Source: [https://www.tarasco.org]

pwdump7 is an application that dumps the password hashes (one-way functions or OWFs) from NT’s SAM database. pwdump extracts LM and NTLM password hashes of local user accounts from the Security Account Manager (SAM) database. This application or tool runs by extracting the binary SAM and SYSTEM file from the filesystem, and then extracts the hashes. One of the most powerful features of pwdump7 is that it is also capable of dumping protected files. Pwdump7 can also extract passwords offline by selecting the target files. The use of this program requires administrative privileges on the remote system. 

![pwdump7](https://github.com/user-attachments/assets/644fde34-1834-4459-8d0f-ccdf27b8c018)

### Some of the additional tools to extract password hashes are as follows:
- **Mimikatz** [https://github.com/ParrotSec/mimikatz]
- **DSInternals** [https://github.com/MichaelGrafnetter/DSInternals]
- **hashcat** [https://hashcat.net]
- **PyCrack** [https://github.com/saurabhwadekar/pycrack]
> #### Note: The use of the above tools requires administrative privileges on the remote system.

## Password Spraying Attack
Password spraying is a type of brute force attack which involves a malicious actor attempting to use the same password on multiple accounts before moving on to try another one.
### The following are some additional password-spraying attack tools:
- **thc-hydra** [https://github.com/vanhauser-thc/thc-hydra]
- **Metasploit** [https://www.metasploit.com]
- **Rubeus** [https://github.com/GhostPack/Rubeus]
- **adfsbrute** [https://github.com/ricardojoserf/adfsbrute]
- **CrackMapExec** [https://github.com/byt3bl33d3r/CrackMapExec]

# 📶 Escalating Privileges

# ♻️ Maintaining Access

# 🧹 Clearing Logs
