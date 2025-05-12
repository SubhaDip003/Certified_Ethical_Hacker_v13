 # 🧩 Enumeration
Enumeration is the process of actively gathering more detailed information about a target system, network, or application after initial reconnaissance. It involves extracting information such as usernames, system names, network shares, services, and other data that can help an attacker or penetration tester move forward in exploiting vulnerabilities.

## Techniques for Enumeration 
The following techniques are used to extract information about a target.
- Extract **usernames from email addresses** since they follow the format **"username@domainname"**.
- Use **default usernames and passwords** from manufacturer lists if users haven’t changed them.
- **Brute force Active Directory** by using error messages during login to identify valid usernames and then crack passwords.
- Perform a **DNS Zone Transfer** to collect domain and IP details if the DNS server isn't configured securely.
- Extract **Windows user groups** if the attacker already has a valid user account in the system.
- Use **SNMP (Simple Network Management Protocol)** to guess community strings and extract usernames.
- Use **SNMP queries** to map out network resources and the network structure.

Services and TCP/UDP ports that can be enumerated include the following. 
---

**Port 53 (TCP/UDP): Domain Name System (DNS)**
Used for resolving domain names. UDP is default; TCP is used for large responses. Attackers may exploit it via malware.

**Port 135 (TCP/UDP): Microsoft RPC Endpoint Mapper**
Helps clients find RPC services. Vulnerable to DoS attacks if not secured.

**Port 137 (UDP): NetBIOS Name Service (NBNS)**
Used for name resolution in Windows systems. Can be attacked to get system names and IPs.

**Port 139 (TCP): NetBIOS Session Service**
Used for file and printer sharing in Windows. Vulnerable if misconfigured; can allow unauthorized access.

**Port 445 (TCP/UDP): SMB over TCP**
Used for direct file and printer sharing without NetBIOS. Attackers may exploit for remote access.

**Port 161 (UDP): Simple Network Management Protocol (SNMP)**
Used to monitor and manage network devices. Attackers use it to gather device info.

**Port 389 (TCP/UDP): Lightweight Directory Access Protocol (LDAP)**
Used for accessing directory services like user and group data.

**Port 2049 (TCP): Network File System (NFS)**
Used to access files over a network as if they are local. Can be exploited for remote access.

**Port 25 (TCP): Simple Mail Transfer Protocol (SMTP)**
Used for sending emails. Attackers may use it to gather info or spam.

**Port 162 (TCP/UDP): SNMP Trap**
Used to send alerts from SNMP agents to managers.

**Port 500 (UDP): ISAKMP/IKE**
Used in VPNs to manage encryption keys and security settings.

**Port 22 (TCP): SSH/SFTP**
SSH is used for secure remote access; SFTP is for secure file transfers. Attackers may brute-force logins.

**Port 3268 (TCP/UDP): Global Catalog Service**
Used by Microsoft systems to search directory data across domains.

**Port 5060/5061 (TCP/UDP): Session Initiation Protocol (SIP)**
Used for starting voice/video calls. 5060 is for unencrypted, 5061 for encrypted communication.

**Port 20/21 (TCP): File Transfer Protocol (FTP)**
Used for file transfers. Attackers may sniff credentials or brute-force access.

**Port 23 (TCP): Telnet**
Used for remote management. Sends data in plain text, so it’s vulnerable to attacks.

**Port 69 (UDP): Trivial File Transfer Protocol (TFTP)**
Used for simple file transfers like firmware updates. Can be exploited to install malware.

**Port 179 (TCP): Border Gateway Protocol (BGP)**
Used by ISPs for routing traffic. Misconfigurations may lead to major routing attacks.

---


# 🖧 NetBIOS Enumeration 
# 📡 SNMP Enumeration
# 🗂️ LDAP Enumeration 
# ⏱️ NTP Enumeration
# 📁 NFS Enumeration
# ✉️ SMTP Enumeration
# 🌐 DNS Enumeration
# 🧪 Other Enumeration Techniques
