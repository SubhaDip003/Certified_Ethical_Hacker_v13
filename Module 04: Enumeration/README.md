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
Used for sending emails. Attackers may use it to gather info or spam. Below table lists some commands used by SMTP and their respective syntaxes.

![SMTP](https://github.com/user-attachments/assets/7a966ffd-faab-46b2-909a-ae0dc7a57b67)


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
NetBIOS (Network Basic Input/Output System) is a communication service that allows computers on a local network to identify and talk to each other. It was originally developed for Windows systems and helps in sharing files, printers, and other resources over a network. NetBIOS works by assigning names to devices and allowing them to connect using these names instead of IP addresses. It is commonly used in older networks and operates over ports like 137, 138, and 139. However, because it's not very secure, modern networks often replace it with more secure protocols. 

NetBIOS uses UDP port 137 (name services), UDP port 138 (datagram services), and TCP port 139 (session services). Attackers usually target the NetBIOS service because it is easy to exploit and run on Windows systems even when not in use.

Attackers use NetBIOS enumeration to obtain the following:
- The list of computers that belong to a domain
- The list of shares on the individual hosts in a network
- Policies and password

## NetBIOS Name List
![NetBIOS Name List](https://github.com/user-attachments/assets/728b719c-6340-4531-aef8-59067ec0784f)
> #### Note: Microsoft does not support NetBIOS name resolution for IPv6

## NetBIOS Enumeration Tools
NetBIOS enumeration tools explore and scan a network within a given range of IP addresses and lists of computers to identify security loopholes or flaws in networked systems. These tools also enumerate operating systems (OSs), users, groups, Security Identifiers (SIDs), password policies, services, service packs and hotfixes, NetBIOS shares, transports, sessions, disks and security event logs, etc.

### Nbtstat Utility 
🔗Source: [https://learn.microsoft.com]

The Nbtstat utility is a command-line tool in Windows that helps you troubleshoot and view NetBIOS (Network Basic Input/Output System) over TCP/IP connections. It shows information about networked computers, such as their NetBIOS names and IP addresses. You can use Nbtstat to check active connections, see name resolution issues, or clear the NetBIOS name cache. It's mainly used to gather details about nearby Windows systems in a local network.

### Some nbtstat commands:
```
nbtstat -n                     	# → Lists local NetBIOS names registered on your system (local machine NetBIOS table).
nbtstat -R                    	# → Purges and reloads the remote cache name table from the LMHOSTS file.
nbtstat -c                     	# → Displays the contents of the NetBIOS name cache (recently resolved names).
nbtstat -s                     	# → Lists NetBIOS sessions table showing all open sessions with remote hosts.
nbtstat -a 10.10.10.5          	# → Enumerates the NetBIOS names registered by a remote machine with IP 10.10.10.5.
nbtstat -A 10.10.10.5          	# → Same as -a, but uses an IP address instead of a hostname.
nbtstat -a TARGET              	# → Replaces TARGET with the NetBIOS name of a remote system to enumerate its table.
nbtstat -r                     	# → Shows name resolution statistics using broadcast and WINS.
nbtstat -RR                    	# → Forces a release and refresh of your NetBIOS name with the WINS server.
nbtstat -S                     	# → Lists current NetBIOS sessions with IP addresses (like `-s` but with IPs not names).
<interval> 			# → Re-displays selected statistics, pausing at each display for the number of seconds specified in Interval
-?				# → Display Help
```
### NetBIOS Enumerator
🔗Source: [https://nbtenum.sourceforge.net]

NetBIOS Enumerator is a tool or program used to collect information from systems that use the NetBIOS protocol, mainly on Windows networks. It helps gather details like computer names, shared folders, user accounts, and network services running on a remote machine.

Attackers and security professionals use NetBIOS enumerators to identify weaknesses in a network. If a system allows null sessions (unauthenticated access), the enumerator can extract a lot of information without needing a username or password. This information can then be used to plan further attacks or to secure the network by identifying what data is being exposed.

In simple terms, a NetBIOS Enumerator is like a scanner that helps find out what a Windows computer is sharing on the network, often without logging in.

![NetBIOS Enumerator](https://github.com/user-attachments/assets/4808f32e-ae38-4c09-b42c-e442f95c35a4)

### Nmap 
🔗Source: [https://nmap.org]

Attackers use the Nmap Scripting Engine (NSE) for discovering NetBIOS shares on a network. The NSE nbstat script allows attackers to retrieve the target’s NetBIOS names and MAC addresses. By default, the script displays the name of the computer and the logged-in user. However, if the verbosity is turned up, it displays all names related to that system.

### Some nmap Command for NetBIOS Enumeration:
```
nmap -sU -p 137 <target>				# → Sends a UDP probe to port 137 to check for NetBIOS Name Service (NBNS) – basic discovery of NetBIOS services.
nmap -sU --script nbstat -p 137 <target>		# → Uses the `nbstat` NSE script to enumerate NetBIOS names (hostname, user, domain, MAC) from the target via UDP.
nmap -p 139,445 --open <target>				# → Scans TCP ports 139 (NetBIOS session) and 445 (SMB) to check if NetBIOS/SMB services are open.
nmap -p 139,445 --script smb-os-discovery <target>	# → Retrieves OS information, computer name, domain, and NetBIOS name using SMB/NetBIOS.
nmap --script smb-enum-shares -p 139,445 <target>	# → Lists SMB shares over NetBIOS; identifies readable/writeable shares including ADMIN$, IPC$.
nmap --script smb-enum-users -p 139,445 <target>	# → Enumerates SMB/NetBIOS users on the target system.
nmap --script smb-enum-groups -p 139,445 <target>	# → Enumerates SMB groups (useful in Windows Active Directory environments).
nmap --script smb-enum-processes -p 445 <target>	# → Lists running processes on the target via SMB/NetBIOS (if access is allowed).
nmap --script smb-enum-sessions -p 445 <target>		# → Shows active sessions on SMB (e.g., other users connected via SMB).
nmap --script smb-security-mode -p 445 <target>		# → Determines the security mode of SMB/NetBIOS (e.g., if null sessions are allowed).
nmap --script smb2-security-mode -p 445 <target>	# → Queries SMBv2 to get its security settings (like signing required, guest access, etc.).
nmap --script smb-protocols -p 445 <target>		# → Detects SMB/NetBIOS versions supported by the remote host (e.g., SMBv1, SMBv2, SMBv3).
nmap --script smb2-capabilities -p 445 <target>		# → Shows what capabilities SMBv2 supports (e.g., large MTU, encryption, etc.).

nmap --script "smb* and not intrusive" -p 139,445 <target>			# → Runs all non-intrusive SMB scripts (for safe initial enumeration).
nmap -Pn -n -p 137,139,445 -sS --script nbstat,smb-os-discovery <target>	# → Stealth SYN scan with NetBIOS enumeration for faster, low-profile scanning.

nmap -p 137,139,445 --script nbstat,smb-os-discovery,smb-enum-shares,smb-enum-users <target>	# → Combines multiple useful NetBIOS and SMB scripts in a single scan.
```
### The following are some additional NetBIOS enumeration tools:
- **Global Network Inventory** [https://magnetosoft.com]
- **Advanced IP Scanner** [https://www.advanced-ip-scanner.com]
- **Hyena** [https://www.systemtools.com]
- **Nsauditor Network Security Auditor** [https://www.nsauditor.com]

## Enumerating User Accounts 
🔗Source: [https://learn.microsoft.com]

Enumerating user accounts using the PsTools suite helps in controlling and managing remote systems from the command line. The following are some commands for enumerating user accounts.

### PsTools
PsTools is a suite of command-line utilities developed by Mark Russinovich that allows you to manage local and remote Windows systems. It includes various tools for tasks such as executing processes remotely, viewing system information, managing files, and controlling services. The tools in the PsTools suite include:

- **PsExec** - Execute processes remotely. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psexec] 
- **PsFile** - Show files opened remotely. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psfile]
- **PsGetSid** - Display the SID of a computer or user. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psgetsid]
- **PsInfo** - List information about a system. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psinfo]
- **PsPing** - Measure network performance. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psping]
- **PsKill** - Kill processes by name or process ID. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/pskill]
- **PsList** - List detailed information about processes.🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/pslist]
- **PsLoggedOn** - See who's logged on locally and via resource sharing. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psloggedon]
- **PsLogList** - Dump event log records. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psloglist]
- **PsPasswd** - Change account passwords. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/pspasswd]
- **PsService** - View and control services. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psservice]
- **PsShutdown** - Shut down and optionally reboot a computer. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/psshutdown]
- **PsSuspend** - Suspend processes. 🔗Source: [https://learn.microsoft.com/en-us/sysinternals/downloads/pssuspend]
- **PsUptime** - Show how long a system has been running since its last reboot. (PsUptime's functionality has been incorporated into **PsInfo**)

To use PsTools, you simply download the suite, and you don't need to install any client software on the remote systems. You can run the tools by typing their name followed by any command-line options you want. For complete usage information, you can specify the "-?" command-line option.

## Enumerating Shared Resources Using Net View 
The Net View utility is a command-line tool in Windows that is used to display a list of computers, shared resources (like folders or printers), or domains on a network. It helps users see what other devices are connected and what they are sharing. This is useful for network administrators or attackers during enumeration to identify accessible systems and resources on a network. The command commonly used is net view, and when followed by a computer name (like net view \\computername), it shows the shared folders and printers on that specific system. It can be used in the following ways.
```
net view                             # → Lists all visible computers in the current domain or network.
net view \\10.10.10.5                # → Lists all shared resources (folders, printers) on the remote host 10.10.10.5.
net view /domain                     # → Lists all available domains in the network.
net view /workgroup                  # → Lists all workgroups (for non-domain environments).
net view \\TARGET-PC /all            # → Shows detailed shared resource info (only works on older systems).
net use \\10.10.10.5\ShareName       # → Attempts to connect to a shared resource.

net use                              # → Lists all current SMB connections to remote shares.
net use * /delete                    # → Disconnects all active SMB share sessions.
net view /network:nw                 # → Used in older NetWare networks to show shares (legacy).
net config workstation               # → Displays the computer's NetBIOS name and domain/workgroup info.
net config server                    # → Shows the server service configuration and shared resource settings.
net share                            # → Lists local shares hosted by the current system.
net share ShareName                  # → Displays details about a specific local share.

net use \\10.10.10.5\ShareName /user:Administrator  	# → Connects to a share using specific credentials.
net share NewShare=c:\folder /grant:everyone,full  	# → Creates a new share and gives full access to everyone (use with caution).
```
# 📡 SNMP Enumeration

# 🗂️ LDAP Enumeration 
# ⏱️ NTP Enumeration
# 📁 NFS Enumeration
# ✉️ SMTP Enumeration
# 🌐 DNS Enumeration
# 🧪 Other Enumeration Techniques
