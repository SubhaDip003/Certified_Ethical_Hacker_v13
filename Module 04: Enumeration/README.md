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
### net use utility

`net use` is a Windows command-line utility that allows users to connect to shared resources like network drives or printers over a network. Security professionals, ethical hackers, and penetration testers use `net use` during NetBIOS enumeration to discover and access shared folders or drives on target systems. By checking which shares are available and if they are accessible without authentication, they can identify potential weaknesses or misconfigurations that could allow unauthorized access to sensitive files or resources.
```
net use                                         # → Displays a list of all current network connections and mapped drives.
net use \\<ip_or_hostname>\share                # → Connects to a shared folder on a remote machine (authentication may be required).
net use \\<ip_or_hostname>\share /user:<user>   # → Connects to a share using a specific username.
net use Z: \\<ip_or_hostname>\share             # → Maps the remote share to drive letter Z:.
net use /delete Z:                              # → Disconnects the mapped drive Z:.
net use * /delete                               # → Disconnects all active network connections.
net use \\<ip_or_hostname>\IPC$ /user:<user>    # → Connects to the hidden IPC$ share (often used for enumeration or exploits).
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
SNMP (Simple Network Management Protocol) is a protocol used to manage and monitor network devices like routers, switches, servers, printers, and more. It allows network administrators to collect information about these devices, configure them, and detect issues in real-time. 

As a professional ethical hacker or penetration tester, your next step is to carry out SNMP enumeration to extract information about network resources (such as hosts, routers, devices, and shares) and network information (such as ARP tables, routing tables, device-specific information, and traffic statistics).

- Attackers use SNMP default community strings to extract information about a device
- Attackers enumerate SNMP to extract information about network resources, such as hosts, routers, devices, and shares, and network information, such as ARP tables, routing tables, and traffic

## SNMP Enumeration Tools
SNMP enumeration tools are used to scan a single IP address or a range of IP addresses of SNMP-enabled network devices to monitor, diagnose, and troubleshoot security threats.

### Enumerating SNMP using SnmpWalk 
🔗Source: [https://ezfive.com]

SnmpWalk is a command-line tool used to gather detailed information from network devices like routers, switches, printers, and servers using the SNMP (Simple Network Management Protocol). It works by walking through or querying the SNMP "tree" on a target device to retrieve data such as system information, running processes, network interfaces, and more.

In simple terms, SnmpWalk is like a scanner that asks a device, “What do you know?” and the device responds with everything it’s allowed to share—one piece of information after another. This is very useful for system administrators and attackers alike, as it can reveal a lot about how a device is configured and what it's doing, especially if SNMP is not secured properly.

📘 Glossary of Key OIDs:
---
| OID                  | Purpose                                                   |
| -------------------- | --------------------------------------------------------- |
| `1.3.6.1.2.1.1`      | System Information (sysName, sysDescr, sysLocation, etc.) |
| `1.3.6.1.2.1.2.2`    | Network Interfaces                                        |
| `1.3.6.1.2.1.4.20`   | IP Addresses                                              |
| `1.3.6.1.2.1.25.4.2` | Running Processes                                         |
| `1.3.6.1.2.1.25.6.3` | Installed Software                                        |
| `1.3.6.1.2.1.6.13`   | TCP Connections                                           |
---

```
# These snmpwalk commands are used to gather or change information from a device using SNMP:
# -v1 or -v2c: SNMP version
# -c public: Community string (like a password)
# <Target IP Address>: The device you’re targeting

snmpwalk -v1 -c public <Target IP Address>                		# → Get all SNMP info using SNMPv1
snmpwalk -v2c -c public <Target IP Address>               		# → Get all SNMP info using SNMPv2c
snmpwalk -v2c -c public <Target IP Address> hrSWInstalledName   	# → List installed software
snmpwalk -v2c -c public <Target IP Address> hrMemorySize        	# → Show memory size of the device
snmpwalk -v2c -c public <Target IP Address> <OID> <New Value>   	# → (Incorrect syntax) Not used to set values
snmpwalk -v2c -c public <Target IP Address> sysContact <New Value> 	# → **(Incorrect syntax) snmpwalk can't set values

snmpwalk -v2c -c public <Target IP Address>				# → Enumerates all available SNMP objects on the target (default OID).
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.1		# → Queries the "system" OID for system information (sysDescr, sysName, etc.).
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.25.1.1		# → Shows system uptime (host UCD-SNMP-MIB).
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.25.4.2		# → Enumerates running processes on the remote system.
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.25.6.3		# → Lists installed software (helpful for service discovery or vuln assessment).
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.4.1			# → Walks through the private enterprise-specific MIB tree.
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.6.13		# → Shows active TCP connections (like netstat via SNMP).
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.4.20		# → Shows IP addresses configured on interfaces.
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.2.2.1.2		# → Displays network interface names.
snmpwalk -v2c -c public -t 5 -r 2 <Target IP Address>			# → Customizes timeout and retries (useful for unstable targets).
snmpwalk -v1 -c public <Target IP Address>				# → Use SNMPv1 instead of v2c (older devices may only support v1).
snmpwalk -v2c -c private <Target IP Address>				# → Attempts walk with a different community string (if public fails).
snmpwalk -v2c -c public -O e <Target IP Address>			# → Output numeric OIDs instead of translated names (useful for scripting).
snmpwalk -v2c -c public -On -Oq <Target IP Address>			# → Minimalist output for parsing: numeric OIDs with only values.
snmpwalk -v2c -c public <Target IP Address> 1.3.6.1.2.1.1.6		# → Queries physical location of device (if configured).
snmpwalk -v2c -c public <Target IP Address> hrSWRunName			# → Enumerates human-readable process names using MIB labels (if MIBs are installed).
snmpwalk -v2c -c public -m ALL <Target IP Address>			# → Loads all available MIBs for best output (needs MIBs installed).
```
### Enumerating SNMP using Nmap 
🔗Source: [https://nmap.org]
```
nmap -sU -p 161 --script=snmp-processes <Target IP Address>		# → Lists running processes on the target
nmap -sU -p 161 --script=snmp-sysdescr <Target IP Address>		# → Retrieves system description (like OS info)
nmap -sU -p 161 --script=snmp-win32-software <Target IP Address>	# → Lists installed software on Windows systems
```
###  snmp-check (snmp_enum Module) 
🔗Source: [https://www.nothink.org]

snmpcheck is a tool used to gather information from devices on a network using the SNMP (Simple Network Management Protocol) service. It helps security testers or attackers extract valuable details like system information, network settings, running processes, open ports, and user accounts from a device that has SNMP enabled and misconfigured. The tool works by sending SNMP requests to a target and reading the responses, which can reveal sensitive data if SNMP is not properly secured. It's especially useful during enumeration in penetration testing.
```
snmp-check <Target IP Address>					# → Performs default enumeration using community string "public" on SNMPv1.
snmp-check -c private <Target IP Address>			# → Uses the community string "private" instead of the default "public".
snmp-check -v1 -c public <Target IP Address>			# → Forces SNMP version 1 explicitly for compatibility with older devices.
snmp-check -v2c -c public <Target IP Address>			# → Uses SNMP version 2c for better performance and more detailed results.
snmp-check -p 161 <Target IP Address>				# → Specifies a custom SNMP port (default is 161).
snmp-check -t <Target IP Address> -w				# → Enables verbose output, including raw SNMP request/response packets.
snmp-check -t <Target IP Address> -o output.txt			# → Saves the output to a text file for offline analysis.
snmp-check -t <Target IP Address> --os				# → Only queries OS-related information (like system name, uptime, etc.).
snmp-check -t <Target IP Address> --hardware			# → Extracts hardware details (CPU, memory, storage).
snmp-check -t <Target IP Address> --software			# → Lists installed software (if exposed).
snmp-check -t <Target IP Address> --processes			# → Lists currently running processes.
snmp-check -t <Target IP Address> --tcp-connections		# → Displays active TCP connections (like netstat over SNMP).
snmp-check -t <Target IP Address> --network-interfaces		# → Lists network interfaces and their statuses.
snmp-check -t <Target IP Address> --firewall-rules		# → Attempts to retrieve firewall or routing rules (depends on SNMP config).
snmp-check -t <Target IP Address> --users			# → Enumerates local users (if accessible).
snmp-check -t <Target IP Address> --routing-table		# → Displays routing table entries on the remote device.
snmp-check -t <Target IP Address> --all				# → Runs full enumeration (OS, processes, interfaces, users, etc.) – default behavior.
```
> #### 📘Notes:
> - snmp-check uses SNMPv1 and v2c, but does not support SNMPv3 (which is encrypted and authenticated).
> - Many switches, routers, printers, and IoT devices expose SNMP data if poorly configured.
> - The default community string is "public" – always try "private" and "admin" as well.
> - **⚡Pro Tip:** Use snmp-check first for quick high-level enumeration, then pivot to snmpwalk for deep OID-specific brute-forcing and onesixtyone for community string discovery.

### SoftPerfect Network Scanner 
🔗Source: [https://www.softperfect.com]

SoftPerfect Network Scanner is a powerful tool used to gather information about computers and devices on a network. It can find open ports, shared folders, running services, and detailed information using methods like SNMP, WMI, HTTP, SSH, and PowerShell. It can also ping devices, scan files, read registry entries, and monitor performance. The tool allows users to filter results and export them in formats like XML and JSON. It can detect IP ranges, resolve hostnames, check if specific ports are open, and even perform remote shutdowns or Wake-on-LAN. Attackers may misuse this tool to collect data about shared folders and other network devices.

![SoftPerfectNetworkScanner](https://github.com/user-attachments/assets/77c09ef0-277d-4b3f-b5e9-2cf1c82cfe40)

### The following are some additional SNMP enumeration tools:
- **Network Performance Monitor** [https://www.solarwinds.com]
- **OpUtils** [https://www.manageengine.com]
- **PRTG Network Monitor** [https://www.paessler.com]
- **Engineer’s Toolset** [https://www.solarwinds.com]

# 🗂️ LDAP Enumeration
LDAP (Lightweight Directory Access Protocol) is a protocol used to access and manage directory services like Active Directory. It works like a digital phonebook or company structure, storing organized information such as user names, emails, and departments. LDAP runs over TCP port 389 and uses a special format Basic Encoding Rules (BER) to exchange data between a client and a server. It often uses DNS to quickly find and respond to queries. If not secured properly, attackers can connect to LDAP and collect sensitive details like usernames, addresses, and server info without needing to log in, which they can then use for further attacks.

## Manual and Automated LDAP Enumeration
Attackers can use both manual and automated approaches for LDAP enumeration. Some of the commands that can be used for LDAP enumeration are as follows:
### Manual LDAP Enumeration
```
# Manual LDAP Enumeration using Python and ldap3 library:
# 1. Scan the target to check if LDAP (389) or LDAPS (636) is open using Nmap.
# 2. Install ldap3 library.
pip3 install ldap3

# 3. Open Python and connect to the LDAP server.
python3
>>> import ldap3
>>> server = ldap3.Server('Target_IP', port=389, get_info=ldap3.ALL)  # use_ssl=True for LDAPS
>>> connection = ldap3.Connection(server)
>>> connection.bind()  # Returns True if connection is successful

# 4. Get domain info and naming context.
>>> server.info

# 5. Search and list all directory entries.
>>> connection.search(search_base='DC=example,DC=com', search_filter='(&(objectClass=*))', search_scope='SUBTREE', attributes='*')
>>> connection.entries

# 6. Dump specific LDAP data like usernames and passwords.
>>> connection.search(search_base='DC=example,DC=com', search_filter='(&(objectClass=person))', search_scope='SUBTREE', attributes='userPassword')
>>> connection.entries
```
### Automated LDAP Enumeration
```
nmap -p 389 --script ldap-brute --script-args ldap.base='"cn=users,dc=CEH,dc=com"' <Target IP Address> 
```
## LDAP Enumeration Tools
There are many LDAP enumeration tools that access directory listings within Active Directory (AD) or other directory services. Using these tools, attackers can enumerate information such as valid usernames, addresses, and departmental details from different LDAP servers.
### Softerra LDAP Administrator 
🔗Source: https://www.ldapadministrator.com

Softerra LDAP Administrator is a powerful and user-friendly Windows application used to manage and browse LDAP (Lightweight Directory Access Protocol) directories. It provides a graphical interface that makes it easier for administrators, developers, and security professionals to connect to LDAP servers, view and edit directory objects, manage users and groups, and perform searches and queries. Instead of using command-line tools or writing code, you can interact with LDAP data visually, which simplifies tasks like troubleshooting, testing, and maintaining directory services such as Microsoft Active Directory or OpenLDAP.

![Softerra](https://github.com/user-attachments/assets/cfcefaa3-29d6-4c7c-aeb3-e80b69c4b676)

### ldapsearch 
Source: [https://linux.die.net]

ldapsearch is a command-line tool used to search and extract data from an LDAP directory, like Active Directory. It connects to the LDAP server, logs in (binds), and then performs a search based on the filters you give. If no filter is provided, it defaults to showing everything. You can choose what kind of attributes you want to see—like user details or system info. The results are shown in a readable format called LDIF. Attackers often use ldapsearch to find users and other directory information during an enumeration phase.
```
💡 Common Flags Breakdown:
-x → Simple bind (no SASL)
-h → Target host/IP
-H → Full URI (ldap:// or ldaps://)
-D → Bind DN (used for authenticated access)
-w → Password for bind DN
-b → Base DN (Distinguished Name) to start searching
-s base|one|sub → Scope: base, one-level, or full subtree
-LLL → Clean output without comments or version info
==========================================================================================================================================================================================
ldapsearch -x -h <Target IP Address> -s base						# → Basic anonymous LDAP query to check if the server is responding.
ldapsearch -x -h <Target IP Address> -s base namingcontexts				# → Lists base DNs (important to scope future searches).
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com"				# → Performs anonymous bind and retrieves entries under the given base DN.
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(objectClass=*)"		# → Full enumeration of all objects under the domain.
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(objectClass=person)"	# → Lists all user-type objects (useful for user enumeration).

ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(objectClass=group)"	# → Lists groups present in the directory.
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(cn=*)" cn			# → Extracts all common names.
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" -LLL dn			# → Clean output showing only DNs of objects (for scripting or chaining).
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(!(objectClass=computer))"	# → Filter out computer objects, list only human users/groups.
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(userAccountControl=512)"	# → Finds enabled user accounts in AD (512 = NORMAL_ACCOUNT).
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(adminCount=1)"		# → Lists privileged user accounts (often members of Domain Admins).
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(servicePrincipalName=*)"	# → Enumerates service accounts (used in Kerberoasting attacks).

ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(&(objectClass=person)(memberOf=CN=Domain Admins,CN=Users,DC=example,DC=com))"	# → Lists all domain admin users.
ldapsearch -x -H ldap://<Target IP Address> -D "CN=user,DC=example,DC=com" -w 'Password123' -b "dc=example,dc=com" "(objectClass=*)"		# → Authenticated LDAP bind for full directory enumeration.
ldapsearch -x -h <Target IP Address> -b "dc=example,dc=com" "(sAMAccountName=*)" sAMAccountName							# → Extracts usernames in Active Directory environments.
```
## The following are some additional LDAP enumeration tools:
- **AD Explorer** [https://docs.microsoft.com]
- **LDAP Admin Tool** [https://www.ldapsoft.com]
- **LDAP Account Manager** [https://www.ldap-account-manager.org]
- **LDAP Search** [https://securityxploded.com]

# ⏱️ NTP Enumeration
NTP (Network Time Protocol) is a protocol used to keep the clocks of computers and devices in sync over a network. It makes sure that all systems show the correct and same time by connecting to time servers. This is important for tasks like logging events, running scheduled jobs, or maintaining security across systems. NTP usually works over UDP port 123 and can adjust even tiny differences in system time.

The following are some pieces of information an attacker can obtain by querying an NTP server:
- List of hosts connected to the NTP server
- Clients’ IP addresses in the network, their system names, and OSs
- Internal IPs, if the NTP server is in the demilitarized zone (DMZ)

NTP enumeration commands such as `ntpdate`, `ntptrace`, `ntpdc`, and `ntpq` are used to query an NTP server for valuable information.

## Enumerate using ntpdate
`ntpdate` is a command-line tool used to quickly synchronize the system time with a remote Network Time Protocol (NTP) server. It sends a time request to the server and adjusts the local machine's clock based on the response. Security professionals use `ntpdate` during NTP enumeration to check if the NTP service on a target is active, reachable, and leaking system information like the server’s IP, time settings, or even the internal network time sources. This information can help in mapping the network or identifying potential misconfigurations.

### ntpdate parameters and their respective functions
![ntpdate](https://github.com/user-attachments/assets/94e333e2-20c5-430c-9de3-95343976d170)
```
sudo apt install ntpdate		# → Install

ntpdate -q <Target>			# → Queries the NTP server without setting the time; displays time offset and delay.
ntpdate -d <Target>			# → Debug mode; shows detailed NTP packet exchange and clock sync info.
ntpdate -u <Target>			# → Uses unprivileged ports (for bypassing firewall rules that block privileged ports).
ntpdate -q pool.ntp.org			# → Queries a public NTP pool server to get its current time and offset info.
ntpdate -s <Target>			# → Logs the time adjustment via syslog (useful for background system logs).
ntpdate -b <Target>			# → Forces time update via step (instead of gradual slew) when syncing system time.
ntpdate -q -t 10 <Target>		# → Sets the timeout to 10 seconds for the NTP request.
ntpdate -q -p 4 <Target>		# → Sends 4 NTP packets (default is 8); helps with analyzing response consistency.
ntpdate -q -a user:pass <Target>	# → Uses authentication (if required by target NTP server; rarely used in public).
ntpdate -q -v <Target>			# → Verbose output; displays more detailed clock data (requires patched version).

# Example of adjusting system time to match NTP server (must be run as root)
sudo ntpdate <Target>			# → Synchronizes system time with target NTP server.

# Example of chaining with grep to extract offsets or delay
ntpdate -q <Target> | grep offset	# → Filters the output to show only offset values (for scripting or monitoring).
```
## Enumerate using ntptrace
`ntptrace` is a command-line tool that shows the chain of Network Time Protocol (NTP) servers that a system uses to get the correct time. It traces the path from your system to the main time source, step by step, showing each NTP server in the chain and how accurate they are.

Security professionals use `ntptrace` for NTP enumeration to find and map out NTP servers connected to a target system. This helps them understand the time synchronization setup and identify misconfigured or vulnerable NTP servers, which could be exploited in certain attacks like spoofing or amplification.

Its syntax is as follows: 
```
ntptrace [-n] [-m maxhosts] [servername/IP_address]

-n 		# → Do not print host names and show only IP addresses; may be useful if a name server is down
-m  maxhosts 	# → Set the maximum number of levels up the chain to be followed
```
## Enumeration using ntpdc
`ntpdc` is a command-line tool used to interact with NTP (Network Time Protocol) servers. It allows users to send queries and commands to the server to get detailed status and configuration information. Security professionals use `ntpdc` for NTP enumeration to discover important details about a target system, such as its time settings, peers, and version. This information can help identify vulnerabilities or misconfigurations in the NTP service that could be exploited in a cyberattack.
### ntpdc parameters and their respective functions

![ntpdc](https://github.com/user-attachments/assets/5af4d6ce-38be-41ac-8191-8a27e08054ea)
```
ntpdc -n -c monlist <Target>      # → Retrieves the list of recent clients that connected to the NTP server (potential DDoS amplification vector).
ntpdc -n -c peers <Target>        # → Displays a list of peers the NTP server is connected to along with state and reachability.
ntpdc -n -c listpeers <Target>    # → Shows a summary of peers similar to 'peers' but in a more readable format.
ntpdc -n -c showpeer <Target>     # → Displays detailed information for a specific peer (requires additional peer address input).
ntpdc -n -c version <Target>      # → Retrieves the NTP software version running on the server.
ntpdc -n -c sysinfo <Target>      # → Displays system information including system peer, stratum, precision, and root distance.
ntpdc -n -c iostats <Target>      # → Provides input/output statistics of the server such as received packets and errors.
ntpdc -n -c reslist <Target>      # → Lists the server's restriction list (access control), helpful for understanding security posture.
ntpdc -n -c loopinfo <Target>     # → Shows loop filter information used in time correction (drift stats).
ntpdc -n -c kerninfo <Target>     # → Displays kernel timekeeping info including estimated errors and status.
ntpdc -n -c clockstat <Target>    # → Queries the reference clock’s status, useful when server is using hardware time source.
ntpdc -n -c showstats <Target>    # → Returns protocol statistics like packets sent, received, and bad formats.
ntpdc -n -c host <Target>         # → Sets the target host for subsequent commands (used in interactive mode).
ntpdc -n -c help                  # → Lists all available ntpdc commands with a short description for each.
```
## Enumerate using ntpq
`ntpq` is a command-line tool used to monitor and control Network Time Protocol (NTP) servers. Security professionals use `ntpq` for NTP enumeration because it can help them gather valuable information about the NTP server, such as its version, current time settings, connected peers, and server status. This information can reveal vulnerabilities, misconfigurations, or outdated versions that attackers might exploit. Since NTP runs on many systems by default, it becomes a useful target during network assessments or penetration tests.

### ntpq parameters and their respective functions
![ntpq](https://github.com/user-attachments/assets/8129c116-e2b1-44d7-bb7c-207197d235e7)
```
ntpq -p 10.10.10.10                    # → Displays a list of peers known to the NTP server, showing reachability, delay, offset, and jitter.
ntpq -c rv 10.10.10.10                 # → Retrieves system variables from the NTP server, including time, version, and stats.
ntpq -c "rv 0" 10.10.10.10             # → Displays detailed runtime variables for the NTP daemon itself.
ntpq -c peers 10.10.10.10              # → Same as `-p`, shows known peers and their sync stats.
ntpq -c assoc 10.10.10.10              # → Lists association IDs of peers; used with other queries to request specific peer data.
ntpq -c "readvar associd" 10.10.10.10  # → Reads peer variables for the given association ID.
ntpq -c monstat 10.10.10.10            # → Displays monitoring statistics; shows how many packets received, sent, dropped, etc.
ntpq -c lpassociations 10.10.10.10     # → Lists all available associations with more verbose details.
ntpq -c ifstats 10.10.10.10            # → Shows interface statistics including packet counts and errors.
ntpq -c sysinfo 10.10.10.10            # → Provides a summary of system info like system uptime, stratum, offset, and precision.
```
> #### Note: In many Linux distributions, the NTP daemon ntpd has been joined with Chrony, chronyd. Both the daemons synchronize the local system’s time with a remote time server.

## NTP Enumeration Tools
NTP enumeration tools are used to monitor the working of NTP and SNTP servers in the network and help in the configuration and verification of connectivity from the time client to the NTP servers. The following are some NTP enumeration tools:
- **Nmap** [https://nmap.org]
- **Wireshark** [https://www.wireshark.org]
- **udp-proto-scanner** [https://labs.portcullis.co.uk]
- **NTP Server Scanner** [http://www.bytefusion.com]
- **PRTG Network Monitor** [https://www.paessler.com]

# 📁 NFS Enumeration
NFS stands for Network File System. It is a protocol that allows computers to access and share files over a network as if they were on their own local drives. Security professionals perform NFS enumeration to find out what shared files or directories are available on a target system. This helps them check for weak permissions or misconfigurations that could allow unauthorized access to sensitive data. If NFS is not properly secured, attackers might use it to read, write, or even execute files on the target system.
- Common ports used by NFS are port 111 and 2049 tcp/udp

## NFS Enumeration Tools 
NFS enumeration tools scan a network within a given range of IP addresses or a single IP address to identify the NFS services running on it. These tools also assist in obtaining a list of RPC services using portmap, a list of NFS shares, and a list of directories accessible through NFS; further, they allow downloading a file shared through the NFS server. Attackers use tools such as RPCScan and SuperEnum to perform NFS enumeration.

### Enumerate using RPCScan 
🔗Source: [https://github.com/hegusung/RPCScan]

RPCScan is a tool used to scan systems that offer Remote Procedure Call (RPC) services, such as NFS. It helps identify which RPC services are running on a target machine and what ports they are using. Security professionals use RPCScan for NFS enumeration because NFS relies on RPC to function. By scanning for RPC services, they can discover active NFS services, gather information about shared directories, and check for misconfigurations that could lead to unauthorized access or exploitation.
```
python3 rpc-scan.py <host/host_range> --rpc			# → Listing RPC services
python3 rpc-scan.py <host/host_range> --mounts			# → Listing mountpoints
python3 rpc-scan.py <host/host_range> --nfs --recurse 3		# → Recursing listing of NFS shares
```
### Enumerate using SuperEnum
🔗Source: [https://github.com/p4pentest/SuperEnum]

SuperEnum is a tool used by security professionals to automate the process of service enumeration during penetration testing. It helps gather important information about services running on a target system. When it comes to NFS enumeration, SuperEnum is useful because it can quickly check for misconfigured NFS shares, list available exports, and try mounting them to see what files or directories can be accessed. This helps security professionals find weaknesses in NFS setups that attackers might exploit to access or modify sensitive files.

# ✉️ SMTP Enumeration
SMTP, or Simple Mail Transfer Protocol, is a communication protocol used to send emails between servers over the internet. Security professionals perform SMTP enumeration to gather information about valid email addresses, usernames, and server configurations on a target system. By interacting with the mail server, they can check which users exist, understand how the server handles email delivery, and identify potential vulnerabilities. This information helps in planning further attacks or strengthening security, depending on whether the person is an attacker or a defender.

Mail systems commonly use SMTP with POP3 and IMAP, which enable users to save messages in the server mailbox and download them from the server when necessary. SMTP uses mail exchange (MX) servers to direct mail via DNS. It runs on TCP port 25, 2525, or 587.

### SMTP provides the following three built-in commands:
---
	🔹VRFY: It is used to validate the user on the server.
	🔹EXPN: It is used to find the delivery address of mail aliases
	🔹RCPT TO: It points to the recipient’s address.
---
## SMTP Enumeration using Nmap 
🔗Source: [https://nmap.org]
```
nmap --script smtp-brute -p 25 <target>			# → To performs brute-force attack on SMTP authentication.
nmap --script smtp-commands -p 25 <target>		# → Lists supported SMTP commands, useful for fingerprinting.
nmap --script smtp-enum-users -p 25 <target>		# → Enumerates SMTP users by sending the VRFY command.
nmap --script smtp-ntlm-info -p 25 <target>		# → Extracts NTLM authentication information from SMTP.
nmap --script smtp-open-relay -p 25 <target>		# → Checks if the SMTP server allows open relay (can be used for spamming).
nmap --script smtp-strangeport -p <port> <target>	# → Detects SMTP services running on non-standard ports.
nmap --script smtp-vuln-cve2010-4344 -p 25 <target>	# → Detects a remote buffer overflow vulnerability in Exim.
nmap --script smtp-vuln-cve2011-1720 -p 25 <target>	# → Checks for Postfix SMTP server memory corruption vulnerability.
nmap --script smtp-vuln-cve2011-1764 -p 25 <target>	# → Detects a Denial of Service (DoS) vulnerability in Exim.
```
## SMTP Enumeration using Metasploit
```
# Enumerates valid email users via SMTP:
use auxiliary/scanner/smtp/smtp_enum
set RHOSTS <target_ip>
run

# Detects the SMTP server version for fingerprinting:
use auxiliary/scanner/smtp/smtp_version
set RHOSTS <target_ip>
run

# Checks if the server allows open relay (can be misused for spamming):
use auxiliary/scanner/smtp/smtp_open_relay
set RHOSTS <target_ip>
run

# Extracts NTLM authentication details from SMTP:
use auxiliary/scanner/smtp/smtp_ntlm_info
set RHOSTS <target_ip>
run

# Uses the VRFY command to validate user accounts:
use auxiliary/scanner/smtp/smtp_vrfy
set RHOSTS <target_ip>
run

# Performs brute-force attacks on SMTP authentication:
use auxiliary/scanner/smtp/smtp_brute
set RHOSTS <target_ip>
set USER_FILE <path_to_userlist>
set PASS_FILE <path_to_passlist>
run
```
## SMTP Enumeration Tools
SMTP enumeration tools are used to perform username enumeration. Attackers can use the usernames obtained from this enumeration to launch further attacks on other systems in the network. 
### NetScanTools Pro 
🔗Source: [https://www.netscantools.com]

NetScanTools Pro is a network information and diagnostic software used by security professionals to gather detailed information about networks, servers, and services. It includes many tools for tasks like pinging, port scanning, DNS lookups, and more. Security professionals use NetScanTools Pro for SMTP enumeration because it allows them to connect to mail servers and interact with them using SMTP commands. This helps them identify valid email addresses, server configurations, and possible vulnerabilities in the mail service that could be used for further attacks like spoofing or spamming.

![NETScanToolProForSMTP](https://github.com/user-attachments/assets/894671f3-5662-4fb2-bcde-f3639fbfd40e)

### smtp-user-enum 
🔗Source: [https://pentestmonkey.net]

`smtp-user-enum` is a command-line tool used to find valid usernames on an SMTP (Simple Mail Transfer Protocol) mail server. Security professionals use this tool during SMTP enumeration to check if the server reveals whether a specific email address or username exists. This helps identify valid user accounts, which can then be used in further attacks like brute-force or phishing. It works by sending commands to the mail server and analyzing the responses to see which usernames are accepted or rejected.

mtp-user-enum has the following options:
---
- **-m n:** Maximum number of processes (default: 5)
- **-M mode:** Specify the SMTP command to use for username guessing from among EXPN, VRFY, and RCPT TO (default: VRFY)
- **-u user:** Check if a user exists on the remote system
- **-f addr:** Specify the from email address to use for "RCPT TO" guessing (default: user@example.com)
- **-D dom:** Specify the domain to append to the supplied user list to create email addresses (default: none)
- **-U file:** Select the file containing usernames to check via the SMTP service
- **-t host:** Specify the server host running the SMTP service
- **-T file:** Select the file containing hostnames running the SMTP service
- **-p port:** Specify the TCP port on which the SMTP service runs (default: 25)
- **-d:** Debugging output
- **-t n:** Wait for a maximum of n seconds for the reply (default: 5)
- **-v:** Verbose
- **-h:** Help message
---
```
smtp-user-enum -M VRFY -U users.txt -t <target_ip>        	# → Uses VRFY command to enumerate users from list on target SMTP server.
smtp-user-enum -M EXPN -U users.txt -t <target_ip>            	# → Uses EXPN command to expand mailing lists or validate users.
smtp-user-enum -M RCPT -U users.txt -t <target_ip>           	# → Uses RCPT TO command to check valid recipients.
smtp-user-enum -M VRFY -u alice -t <target_ip>                 	# → Enumerates a single user (alice) using VRFY.
smtp-user-enum -M VRFY -U users.txt -t <target_ip> -p 587      	# → Enumerates users via VRFY on non-standard SMTP port 587.
smtp-user-enum -M VRFY -U users.txt -t <target_ip> -s 25       	# → Forces SMTP HELO handshake on port 25 before enumeration.
smtp-user-enum -M VRFY -U users.txt -t <target_ip> -v          	# → Verbose mode showing detailed response from SMTP server.
smtp-user-enum -M VRFY -U users.txt -t <target_ip> --delay 2   	# → Adds 2 seconds delay between requests to evade IDS/IPS.
smtp-user-enum -M VRFY -U users.txt -t <target_ip> -x 5        	# → Stops after 5 invalid user responses (failsafe).
```

# 🌐 DNS Enumeration
DNS zone transfer is a process where a DNS server shares its zone file (a database of domain names and IP addresses) with a backup server for redundancy. However, if this setting is not properly secured, attackers can take advantage of it. By pretending to be a legitimate client, an attacker can request this zone file from the DNS server. If the server allows it, the attacker can get valuable information like hostnames, IP addresses, and usernames of the target domain. This process is called DNS zone transfer enumeration. Tools like `nslookup`, `dig`, or `DNSRecon` are used to try this. If the server is secure, the request will be denied; otherwise, it may give away sensitive internal network details.

## Dig Utility
`dig`, which stands for Domain Information Groper, is a command-line tool used to query DNS servers and gather detailed information about domain names. Security professionals, ethical hackers, and penetration testers use `dig` during DNS enumeration to collect data like IP addresses, mail servers, name servers, and other DNS records. This helps them understand how a domain is structured, identify potential vulnerabilities, and discover internal systems or subdomains that may be exposed to the internet. It’s a powerful and reliable tool for gathering DNS information quickly and accurately.
```
dig example.com				           # → Performs a standard DNS lookup for A record (default).
dig example.com ANY			           # → Queries all available DNS records (A, MX, TXT, NS, etc.).
dig example.com MX			           # → Retrieves the mail exchange (MX) records of the domain.
dig example.com NS			           # → Gets the authoritative name servers for the domain.
dig example.com SOA			           # → Displays Start of Authority record including primary NS, email, and serial number.
dig example.com TXT			           # → Retrieves TXT records (commonly used for SPF, DKIM, etc.).
dig example.com CNAME		                   # → Shows the canonical name record for alias domains.
dig example.com A +short		           # → Returns only the IPv4 address of the domain (clean output).
dig example.com AAAA +short	                   # → Gets the IPv6 address of the domain.
dig @8.8.8.8 example.com		           # → Queries a specific DNS server (Google DNS in this case) for the domain.
dig -x 93.184.216.34			           # → Performs a reverse DNS lookup (PTR) for an IP address.
dig example.com +trace		                   # → Traces the path of DNS resolution from root servers to the domain.
dig +noall +answer example.com	                   # → Displays only the final answer section of the response.
dig example.com AXFR @ns1.example.com	           # → Attempts a DNS Zone Transfer using specified nameserver.
dig @ns1.example.com example.com AXFR	           # → Alternate syntax for zone transfer attempt.
dig example.com +nssearch		           # → Checks each authoritative nameserver for SOA record consistency.
dig example.com +multi +nocomments +noquestion	   # → Outputs compact multicolumn result, suppressing comments and query section.
```
## nslookup Command 
🔗Source: [https://docs.microsoft.com]

`nslookup` is a command-line tool used to query Domain Name System (DNS) servers and get information about domain names and IP addresses. Security professionals, ethical hackers, and penetration testers use `nslookup` during DNS enumeration to find out details about a target domain, such as its IP address, mail servers, and name servers. This helps them understand the target’s network structure and identify possible weaknesses. It's a simple yet powerful tool for gathering publicly available DNS information during the information-gathering phase of an assessment.
```
nslookup google.com	# → Basic forward DNS lookup to resolve domain to IP.

nslookup                # → Launches interactive nslookup shell for advanced queries.
server <dns_ip>         # → (inside interactive mode) Sets the DNS server to query.
set type=any            # → (inside interactive mode) Queries for all available DNS record types.
set type=mx             # → (inside interactive mode) Queries Mail Exchange (MX) records for domain.
set type=ns             # → (inside interactive mode) Queries Name Server (NS) records for domain.
set type=txt            # → (inside interactive mode) Queries TXT records, useful for SPF/DKIM info.
set type=soa            # → (inside interactive mode) Gets the Start of Authority (SOA) record.
ls -d domain.com        # → (inside interactive mode, if zone transfer is allowed) Lists all domain records via DNS zone transfer.

# → (inside interactive mode) Gets A record (IPv4 address) of the domain.
set type=a                                   
google.com              

# → (inside interactive mode) Gets AAAA record (IPv6 address) of the domain.
set type=aaaa                                
google.com              

ls domain.com > output.txt	# → (inside interactive mode) Saves the zone transfer output to a file.
exit                            # → Exits the interactive nslookup shell.
```
💡 Tip: To attempt DNS zone transfer from the command line directly (non-interactive), use:
```
nslookup -type=any domain.com <dns_server_ip>    # → Non-interactive query for all record types from a specific DNS server.

nslookup                                        # → Start interactive mode for zone transfer:
> server <dns_server_ip>
> ls -d domain.com                              # → Attempts DNS zone transfer (AXFR).
```
## DNSRecon
🔗Source: [https://github.com/darkoperator/dnsrecon]

DNSRecon is a powerful Python-based tool used by security professionals, ethical hackers, and penetration testers to gather detailed information about DNS records of a target domain. It helps in performing DNS enumeration by identifying hostnames, IP addresses, name servers, mail servers, and performing zone transfer checks. DNSRecon automates various DNS queries and can find misconfigurations or exposed data that could help attackers in mapping out the target’s network. It is commonly used during the information gathering phase of a penetration test to uncover valuable details about the domain’s structure and possible attack points.
```
dnsrecon -h                                       # → Displays the help menu with all available options and usage guidance.
dnsrecon -d example.com                           # → Basic DNS enumeration for the domain using default records (NS, A, AAAA, MX, etc.).
dnsrecon -d example.com -t std                    # → Performs a standard record enumeration (A, AAAA, MX, NS, SOA, SRV, TXT).
dnsrecon -d example.com -t brt                    # → Performs a brute-force of subdomains using the built-in wordlist.
dnsrecon -d example.com -t axfr                   # → Attempts a DNS zone transfer on all identified nameservers.
dnsrecon -d example.com -n 8.8.8.8                # → Uses a custom nameserver (Google DNS here) for queries.
dnsrecon -d example.com -t srv                    # → Attempts to enumerate common SRV (Service) records (VoIP, AD, etc.).
dnsrecon -d example.com -t zonewalk               # → Attempts DNSSEC zone walking if NSEC records are available.
dnsrecon -d example.com -t rvl                    # → Performs reverse lookup of IP ranges based on the domain's records.
dnsrecon -d example.com -t goo                    # → Uses Google search for domain name harvesting.
dnsrecon -d example.com -t snoop                  # → Performs cache snooping against DNS servers (if they allow it).
dnsrecon -d example.com -a                        # → Performs a full sweep: standard enumeration, zone transfer, reverse lookup, Google scraping, SRV, cache snooping, and brute-force.
dnsrecon -d example.com -j output.json            # → Outputs results in JSON format for integration with other tools or analysis.
dnsrecon -d example.com -t std -c output.csv      # → Saves standard enumeration results to a CSV file.

dnsrecon -d example.com -t axfr -n ns1.example.com # → Attempts zone transfer specifically against ns1.example.com.
dnsrecon -d example.com -D /path/to/wordlist.txt -t brt  # → Performs brute-force subdomain enumeration using a custom wordlist.
```
## DNSSEC Zone Walking
DNSSEC Zone Walking is a method used to gather hidden DNS records from a domain that has DNSSEC enabled but not properly configured. DNSSEC is meant to secure DNS by using digital signatures to verify DNS data, but older versions like NSEC can accidentally expose a list of all domain records. Security professionals, ethical hackers, and penetration testers perform DNSSEC Zone Walking during DNS enumeration to find out internal hostnames, services, and network structure of the target domain. This helps them understand what parts of the system are exposed and could be at risk, especially if attackers use the same method to plan attacks.
### DNSSEC Zone Walking Tools
DNSSEC zone walking tools are used to enumerate the target domain’s DNS record files. These tools can also perform zone enumeration on NSEC and NSEC3 record files and further use the gathered information to launch attacks such as denial-of-service (DoS) attacks and phishing attacks. 

#### LDNS
🔗Source: [https://www.nlnetlabs.nl] 

`ldns-walk` is a command-line tool used to perform DNSSEC zone walking. It tries to list all the DNS records in a domain by exploiting a weakness in older DNSSEC configurations that use NSEC records. Security professionals, ethical hackers, and penetration testers use `ldns-walk` to discover hidden subdomains, hostnames, and services within a DNS zone. This helps them map out the target’s network structure during assessments and identify areas that may be vulnerable to attacks.
```
ldns-walk example.com                         # → Attempts a DNSSEC zone walk of 'example.com' using NSEC records.
ldns-walk -v example.com                      # → Verbose output; displays each DNS record retrieved during the walk.
ldns-walk -f output.txt example.com           # → Saves the walked DNS records into 'output.txt' for offline analysis.
ldns-walk -d example.com                      # → Shows only domain names (without full resource record details).
ldns-walk -z example.com                      # → Displays zone output format compatible with zone files (includes TTL and class).
ldns-walk -t MX example.com                   # → Filters and displays only MX records during the zone walk.
ldns-walk -t A -t AAAA example.com            # → Retrieves only A and AAAA records while walking the DNSSEC zone.
ldns-walk -S example.com                      # → Performs a strict walk; halts on any error (useful for accurate recon).
ldns-walk -n 8.8.8.8 example.com              # → Uses Google DNS (8.8.8.8) instead of default resolver for the zone walk.
ldns-walk -k /path/to/trust-anchor.key example.com  # → Verifies DNSSEC using a specific trust anchor file.
```
As shown in the screenshot, attackers use the following query to enumerate a target domain iana.org using the DNS server 8.8.8.8 to obtain DNS record files:`ldns-walk @<IP of DNS Server> <Target domain>`

![DNSSEC zone walking](https://github.com/user-attachments/assets/a29c6ff5-eccd-485e-99e3-148b5d674c39)

## DNS Enumeration using OWASP Amass
🔗Source: [https://github.com/owasp-amass/amass]

OWASP Amass is an advanced open-source tool used for gathering information about domain names and related assets during security testing. Security professionals, ethical hackers, and penetration testers use Amass for DNS enumeration to discover subdomains, map network infrastructure, and find exposed services of a target organization. It helps them identify potential attack surfaces by collecting data from public sources, DNS records, and other internet databases in an automated and efficient way.
```
amass enum -passive -d <Target Domain> -src        # → Performs passive subdomain enumeration and shows the source of each discovery.
amass db -dir amass4owasp -list                    # → Lists all domains stored in the local Amass database under the specified directory.
amass viz -d3 -dir amass4owasp                     # → Generates and serves a D3.js-based interactive graph visualization of the discovered domain data.

amass enum -active -d <Target Domain> -brute -w /usr/share/wordlists/amass/all.txt   		# → Performs active enumeration with brute force using a custom wordlist.
amass track -config /root/amass/config.ini -dir amass4owasp -d <Target Domain> -last 2   	# → Tracks differences in subdomains discovered across the last 2 runs using a custom config and data directory.
```
### Some Others amass Commands for DNS Enumeration
```
amass enum -d example.com                          # → Performs passive and active subdomain enumeration on example.com.
amass enum -d example.com -passive                 # → Performs passive-only enumeration; avoids active probing (stealthier).
amass enum -d example.com -active                  # → Enables active reconnaissance including DNS brute forcing and probing.
amass enum -d example.com -brute                   # → Performs brute-force DNS enumeration using a wordlist.
amass enum -d example.com -min-for-recursive 2     # → Filters out names without enough recursive DNS support.
amass enum -d example.com -r 8.8.8.8,1.1.1.1       # → Uses specified recursive DNS resolvers for name resolution.
amass enum -d example.com -src                     # → Displays the data source for each discovered name.
amass enum -d example.com -ip                      # → Prints discovered subdomains with associated IP addresses.
amass enum -d example.com -asn                     # → Adds ASN information (Autonomous System Number) for discovered IPs.
amass enum -d example.com -o subdomains.txt        # → Outputs discovered subdomains to a file named subdomains.txt.
amass enum -df domains.txt                         # → Performs enumeration on all domains listed in the file domains.txt.
amass enum -d example.com -w wordlist.txt -brute   # → Uses a custom wordlist to brute-force subdomains.
amass intel -d example.com                         # → Performs intelligence gathering such as discovering related domains and netblocks.
amass track -d example.com                         # → Compares results from different runs to track changes in discovered assets.
amass db -names -d example.com                     # → Lists all names discovered for the domain from the local Amass database.
amass viz -d3 -g                                   # → Launches a local graph-based visualization (D3) of the enumeration results.
```
## DNS Enumeration Using Nmap
```
nmap --script=broadcast-dns-service-discovery <Target Domain>     # → Discovers services using DNS-SD (Bonjour/mDNS) on the local network via broadcast.
nmap -T4 -p 53 --script dns-brute <Target Domain>                 # → Performs brute-force DNS subdomain enumeration using a built-in wordlist.
nmap -Pn -sU -p 53 --script=dns-recursion <Target>                # → Checks if the DNS server allows recursive queries to external domains (may be vulnerable to DNS amplification).
```
### Some Others Nmap commands for DNS Enumeration
```
nmap -p 53 <target>                                    # → Checks if DNS (UDP port 53) is open on the target.
nmap -sU -p 53 <target>                                # → Performs a UDP scan on port 53 to detect DNS services.
nmap -sV -p 53 <target>                                # → Attempts version detection on DNS service.
nmap -sU -p 53 --script=dns-recursion <target>         # → Checks if DNS server allows recursive queries (may be abused for amplification).
nmap -T4 -p 53 --script=dns-brute <target>             # → Performs brute-force DNS subdomain enumeration using a wordlist.
nmap --script=dns-zone-transfer <target>               # → Attempts a DNS zone transfer (AXFR) from the target DNS server.
nmap --script=dns-nsid -p 53 <target>                  # → Queries for the DNS NSID (Name Server Identifier) option to fingerprint the DNS server.
nmap --script=dns-service-discovery <target>           # → Attempts to enumerate DNS SRV records to identify common services on the domain.
nmap --script=broadcast-dns-service-discovery          # → Discovers services via multicast DNS (mDNS) on the local network.
nmap -sU -p 53 --script=dns-check-zone <target>        # → Checks zone configuration for common misconfigurations and security issues.

nmap --script=dns-brute --script-args dns-brute.domain=example.com <target>  		# → Brute-forces subdomains of example.com using custom domain input.
nmap --script=dns-srv-enum --script-args 'dns-srv-enum.domain=example.com' <target>  	# → Enumerates common DNS SRV records for given domain.
nmap --script=dns-cache-snoop --script-args='dns-cache-snoop.domains={example.com,www.example.com}' <target>  # → Checks if DNS server is caching responses (can be used for info leak).
```
## DNS Security Extensions (DNSSEC) Enumeration using Nmap
```
nmap -sU -p 53 --script dns-nsec-enum --script-args dns-nsec-enum.domains=eccouncil.org <target>   # → Uses the dns-nsec-enum script to enumerate DNS records by exploiting NSEC record chains on UDP port 53, targeting the eccouncil.org domain.

nmap -p 53 --script=dns-nsec-enum <target>               # → Enumerates DNS zone records using NSEC-walking (if zone-walking is possible via DNSSEC).
nmap -p 53 --script=dns-nsec3-enum <target>              # → Attempts to enumerate DNS zone records protected by NSEC3 (less effective than NSEC).
nmap -p 53 --script=dns-check-zone <target>              # → Checks for misconfigurations in DNS zone including DNSSEC-related issues.
nmap -p 53 --script=dns-zone-transfer <target>           # → Attempts a zone transfer (AXFR); helpful in DNSSEC testing if zone transfer is permitted.
nmap -p 53 --script=dns-recursion,dns-nsec-enum <target> # → Checks for recursion support and performs NSEC-based enumeration if possible.
nmap -p 53 --script=dns-nsec-enum --script-args='dns-nsec-enum.domains={example.com}' <target>  # → Performs targeted NSEC zone-walking on specified domain.
```
## The following are some of the additional DNS enumeration tools:
- **Knock** [https://github.com/guelfoweb/knock]
- **Raccoon** [https://github.com/evyatarmeged/Raccoon]
- **Subfinder** [https://github.com/projectdiscovery/subfinder]
- **Turbolist3r** [https://github.com/fleetcaptain/Turbolist3r]

# 🧪 Other Enumeration Techniques
## IPsec Enumeration
IPsec is a common technology used to secure communication in VPNs, either between two networks or between a remote user and a network. It protects data using features like Encapsulating Security Payload (ESP), Authentication Header (AH), and Internet Key Exchange (IKE). Most IPsec VPNs rely on a protocol called Internet Security Association Key Management Protocol 
(ISAKMP) to manage security settings and keys. Security professionals or attackers can scan for ISAKMP on UDP port 500 using tools like Nmap to check if a VPN gateway is active and gather related information.
### IPsec Enumeration using Nmap
```
nmap -sU -p 500 <target_ip>                                # → Scans for IKE (Internet Key Exchange) service on UDP port 500 (used by IPsec).
nmap -sU -p 500 --script ike-version <target_ip>           # → Detects the IKE version (IKEv1 or IKEv2) supported by the IPsec VPN server.
nmap -sU -p 500 --script ike-scan <target_ip>              # → Attempts to discover IKE hosts, supported transforms, and key exchange parameters.
nmap -sU -p 500,4500 <target_ip>                           # → Scans for both IKE (500) and NAT-T (4500) ports used in IPsec VPN setups.
nmap -sU -p 500 --script ike-fingerprint <target_ip>       # → Attempts to fingerprint the IPsec VPN implementation and configuration details.

nmap -sU -p 500 --script ike-scan --script-args=ike-scan.sendcookie=true <target_ip>  	# → Sends IKEv2 cookies to bypass DoS protection and enumerate transforms.
nmap -sU -p 500 --script ike-version --script-args=ike-force=yes <target_ip>   		# → Forces IKE version detection even if the service does not respond properly.
```
### IPsec Enumeration using ike-scan
🔗Source: [https://github.com/royhills/ike-scan]

`ike-scan` is a tool used to discover and gather information about VPN systems that use the IPsec protocol with IKE (Internet Key Exchange). Security professionals, ethical hackers, and penetration testers use `ike-scan` to find out if IKE services are running on a system, what kind of authentication and encryption methods they support, and whether the system leaks any useful information. This helps them understand how secure or vulnerable a VPN setup might be before attackers can exploit any weaknesses.
```
ike-scan <target_ip>                                	# → Sends IKE packets to detect VPN servers; shows IKE responder if found.
ike-scan -M <target_ip>                             	# → Performs Main Mode scan; enumerates IKE responder and its supported transforms.
ike-scan -A <target_ip>                             	# → Performs Aggressive Mode scan; attempts to capture hash of the VPN pre-shared key.
ike-scan -M --trans=0,1,2,3 <target_ip>              	# → Scans using custom transform set to test for supported encryption/auth algorithms.
ike-scan -A --id=examplegroup <target_ip>           	# → Sends Aggressive Mode request with specified group name to provoke a hash response.
ike-scan -A --id=examplegroup --pskcrack <target_ip> 	# → Captures Aggressive Mode PSK hash in format compatible with pskcrack tool.
ike-scan --sport=500 --dport=500 -M <target_ip>     	# → Specifies source and destination ports for Main Mode scanning (default is 500).
ike-scan -M -n 5 <target_ip>                         	# → Sends 5 IKE requests (retries) per target to improve scan reliability.
ike-scan -A -v <target_ip>                           	# → Enables verbose mode for Aggressive Mode scan; shows payload details.
ike-scan -A --multiline <target_ip>                 	# → Displays response data in multi-line format for better readability.
ike-scan --showbackoff --nodns <target_ip>          	# → Disables DNS lookups and shows retry backoff behavior during scan.
```
## VoIP Enumeration 
VoIP is a modern technology that allows people to make voice or video calls over the Internet instead of using traditional phone lines or public switched telephone network (PSTN). It uses a protocol called Session Initiation Protocol (SIP) to manage these calls, which usually runs on  UDP/TCP ports 2000, 2001, 5060, and 5061. Because VoIP works over the Internet, it can be targeted by hackers using tools like Svmap or Metasploit. Through VoIP enumeration, attackers can gather sensitive information such as VoIP gateway/servers, IP-private branch exchange (PBX) systems, and User-Agent IP addresses and user extensions of client software (softphones) or VoIP phones. This information can then be used to launch attacks such as call hijacking, fake caller ID, listening in on calls, or sending spam calls.

### VoIP Enumeration using svmap
🔗Source: [https://github.com/EnableSecurity/sipvicious/wiki/SVMap-Usage]

`svmap` is a tool that is part of the SIPVicious suite, which is used to scan for SIP (Session Initiation Protocol) devices on a network. SIP is commonly used in VoIP (Voice over IP) systems for voice communication. Security professionals, ethical hackers, and penetration testers use `svmap` to find VoIP phones, servers, or gateways by sending SIP requests and identifying which systems respond. This helps them check for exposed or vulnerable VoIP devices that attackers might target in order to eavesdrop, hijack calls, or access internal phone systems.

Attackers use Svmap to perform the following:
- Identify SIP devices and PBX servers on default and non-default ports
- Scan large ranges of networks
- Scan one host on different ports for an SIP service on that host or multiple hosts on multiple ports
- Ring all the phones on a network simultaneously using the INVITE method
```
svmap 192.168.1.0/24                       # → Scans the subnet to identify live SIP (VoIP) devices using default port 5060.
svmap -v 192.168.1.0/24                    # → Enables verbose output; shows more details about each discovered SIP device.
svmap -p 5060 192.168.1.0/24               # → Specifies custom SIP port (default is 5060); useful if SIP service is running on non-standard ports.
svmap -r 1000 192.168.1.0/24               # → Limits rate to 1000 packets per second; helpful to avoid detection or network saturation.
svmap -o results.txt 192.168.1.0/24        # → Saves the output of the scan to a file named results.txt.
svmap -v -p 5061 192.168.1.0/24            # → Scans for SIP devices over TLS (commonly used on port 5061).
```
### VoIP Enumeration using Metasploit
```
# Scans for open SIP ports (UDP 5060) on the target network:
use auxiliary/scanner/sip/options
set RHOSTS <target_ip_range>
set THREADS 10
run

# Enumerates valid SIP usernames by sending SIP REGISTER requests:
use auxiliary/scanner/sip/enumerator
set RHOSTS <target_ip>
set USER_FILE /path/to/userlist.txt
set THREADS 10
run

# Attempts to brute-force SIP user credentials via REGISTER requests:
use auxiliary/scanner/sip/sip_brute
set RHOSTS <target_ip>
set USERNAME <sip_user>
set PASS_FILE /path/to/passlist.txt
run

# Identifies SIP endpoints and gathers SIP banner information:
use auxiliary/scanner/sip/sip_options
set RHOSTS <target_ip>
run

# Tests for SIP INVITE message handling (VoIP DoS and fuzzing potential):
use auxiliary/fuzzers/sip/invite
set RHOSTS <target_ip>
run

# Sends crafted INVITE messages to discover active calls or devices:
use auxiliary/voip/sip_invite_spoof
set RHOSTS <target_ip>
set RPORT 5060
set FROM <spoofed_user>
set TO <target_user>
run

# Checks for SIP digest authentication and leaks in the challenge response:
use auxiliary/voip/sip_digest_leak
set RHOSTS <target_ip>
set USERNAME <known_user>
run
```
## RPC Enumeration
The remote procedure call (RPC) is a technology used for creating distributed client/server programs. RPC allows clients and servers to communicate in distributed client/server programs. It is an inter-process communication mechanism, which enables data exchange between different processes. In general, RPC consists of components such as a client, a server, an endpoint, an endpoint mapper, a client stub, and a server stub, along with various dependencies. 

RPC uses a special service called the portmapper, which runs on port 111 and keeps track of all available RPC services. Security professionals and attackers perform RPC enumeration to discover which services are available and if any of them have security weaknesses. If the RPC ports are open and unprotected, attackers might find vulnerable services that can be exploited.
### RPC Enumeration using Nmap
```
nmap -sV -p 111 <target_ip>                                   # → Scans port 111 (rpcbind) to detect RPC services and versions.
nmap -p 111 --script=rpcinfo <target_ip>                      # → Queries rpcbind to list registered RPC programs and versions.
nmap -p 111 --script=rpc-grind <target_ip>                    # → Enumerates registered RPC services via the rpc.grind procedure.
nmap -p 111 --script=rpc-loc <target_ip>                      # → Attempts to locate specific RPC services on the target.
nmap -p 111 -sU --script=rpc-stat <target_ip>                 # → Retrieves RPC statistics from the target (UDP).
nmap -p 111 -sT --script=rpcdump <target_ip>                  # → Dumps RPC information over TCP.
nmap -p 111 -sV --script=rpc-auth <target_ip>                 # → Checks for RPC authentication weaknesses or misconfigurations.
nmap -p 111 --script=default,safe -sV <target_ip>             # → Runs default and safe scripts including RPC enumeration and version detection.
nmap -p 111 -sV --script=rpcinfo,rpc-grind,rpc-loc <target_ip> # → Combined advanced enumeration of RPC services and versions.
```
Also you can use **NetScanTool Pro** [https://www.netscantools.com] for RPC Enumeration 

![rpc](https://github.com/user-attachments/assets/cab5cb99-326b-46dc-9aff-31317da2d36a)

## Unix/Linux User Enumeration 
One of the important steps for enumeration is to perform Unix/Linux user enumeration.
Unix/Linux user enumeration provides a list of users along with details such as the username, host name, and start date and time of each session

The following command-line utilities can be used to perform Unix/Linux user enumeration.
### rusers
🔗Source: [https://github.com/wageningen/RUsers]

`rusers` is a Unix/Linux command-line tool that shows which users are currently logged in on a remote system that has the rstatd or rusersd service running. Ethical hackers and penetration testers use rusers during user enumeration to discover active usernames on a target network. This helps them identify potential accounts to investigate or attempt access, especially when looking for weak or misconfigured systems that allow remote access without proper security controls.
```
The options are as follows:
-a: Gives a report for a machine even if no users are logged in
-h: Sorts alphabetically by host name
-l: Gives a longer listing similar to the who command
-u: Sorts by the number of users
-i: Sorts by idle time

rusers <target_ip>            # → Lists users logged in on remote machines via the rusersd service.
rusers -l <target_ip>         # → Shows detailed user information including idle time and login time.
rusers -a <target_ip>         # → Lists all users including those on hosts that are currently down.
rusers -h <target_ip>         # → Displays only hostnames with logged in users.
rusers -u <target_ip>         # → Shows host uptime information (some implementations).
rusers -n <target_ip>         # → Displays numerical addresses instead of resolving hostnames.
rusers -l -n <target_ip>      # → Detailed user list with IPs instead of hostnames.
rusers -al <target_ip>        # → Combines all options to list all users with full details.
```
### rwho
🔗Source: [https://github.com/grawity/rwho]

`rwho` is a command-line tool in Unix/Linux systems that shows which users are currently logged in to the local network, along with information like their login time and machine name. Security professionals, ethical hackers, and penetration testers use rwho for user enumeration because it helps them discover active users and systems on the network, which can reveal potential targets for further analysis or exploitation. It’s useful for mapping the environment during the early stages of a security assessment.
```
rwho                                       # → Lists all users currently logged into the network via rwhod.
rwho -a                                    # → Displays all users logged in, including those on hosts that have been idle for more than an hour.
rwho -h                                    # → Prints only hostnames that have users logged in.
rwho -u                                    # → Shows the uptime of each host along with logged-in users.
rwho | grep <username>                     # → Filters the rwho output to locate a specific user on the network.
rwho | awk '{print $1, $2, $6}'            # → Extracts and displays user, host, and idle time from rwho output.
rwho | sort -k6                            # → Sorts the output based on idle time (6th column).
rwho | cut -d ' ' -f1 | sort | uniq        # → Lists unique usernames found across the network via rwho.
rwho | grep -v "idle" | wc -l              # → Counts the number of currently active (non-idle) users across the network.
rwho -a | grep -E 'tty[0-9]+'              # → Extracts terminal information of logged-in users.
```
### finger
🔗Source: [https://github.com/bketelsen/finger]

finger displays information about system users such as the user’s login name, real name, terminal name, idle time, login time, office location, and office phone numbers.
```
finger <username>@<target_ip>                                 # → Queries the specified user on the remote system using the Finger service (port 79).
finger @<target_ip>                                           # → Enumerates all currently logged-in users on the remote system if allowed by the service.
finger -l <username>@<target_ip>                              # → Provides a long format output with more detailed information about the specified user.
finger -m <username>@<target_ip>                              # → Matches the exact username (useful when partial names return multiple entries).
finger -s <username>@<target_ip>                              # → Displays short user info such as login name, terminal, and idle time (useful for quick enumeration).
finger -p <username>@<target_ip>                              # → Suppresses plan and project files in the output (limits information leakage).
finger -f <username>@<target_ip>                              # → Disables printing of the header line (can help in scripting output parsing).
finger -q <username>@<target_ip>                              # → Quiet mode – prints minimal info (useful when trying to avoid detection).
finger -l <username>@<target_ip> | grep -i 'plan\|project'    # → Extracts and inspects potential sensitive info from user's .plan or .project files.
finger -l <username>@<target_ip> > enum_output.txt            # → Saves detailed enumeration info to a file for offline analysis or reporting.
```
> #### 🛡️ Note: The Finger service (port 79) is largely deprecated and rarely enabled on modern systems due to security risks, but if available, it can be a powerful tool for OSINT and internal recon.

## SMB Enumeration
SMB (Server Message Block) is a network protocol used for sharing files, printers, and other resources between computers, especially in Windows environments. Security professionals, ethical hackers, or penetration testers perform SMB enumeration to gather valuable information like shared folders, usernames, and system details from a target system. This helps them identify potential vulnerabilities or misconfigurations that could be exploited during a security assessment.

SMB runs directly on TCP port 445 or via the NetBIOS API on UDP ports 137 and 138 and TCP ports 137 and 139. 

Attackers can also use SMB enumeration tools such as **Nmap**, **SMBMap**, **enum4linux**, **nullinux**, **SMBeagle** and **NetScanTool Pro** to perform a directed scan on the SMB service running on port 445.

### SMB Enumeration Using Nmap
```
nmap -p 445 <target_ip>                                               # → Checks if SMB port 445 is open.
nmap -p 139 <target_ip>                                               # → Checks if SMB over NetBIOS (port 139) is open.
nmap -sV -p 139,445 <target_ip>                                       # → Detects SMB service versions on ports 139 and 445.
nmap --script=smb-os-discovery -p 445 <target_ip>                     # → Enumerates OS information via SMB.
nmap --script=smb-protocols -p 445 <target_ip>                        # → Enumerates supported SMB protocols (e.g., SMBv1, SMBv2, SMBv3).
nmap --script=smb-security-mode -p 445 <target_ip>                    # → Checks SMB security settings such as signing and authentication.
nmap --script=smb2-security-mode -p 445 <target_ip>                   # → Retrieves SMB2 security mode configuration.
nmap --script=smb2-capabilities -p 445 <target_ip>                    # → Lists supported SMB2 capabilities like encryption, leasing, etc.
nmap --script=smb-enum-shares -p 445 <target_ip>                      # → Enumerates available SMB shares (including hidden/admin shares).
nmap --script=smb-enum-users -p 445 <target_ip>                       # → Attempts to enumerate SMB users.
nmap --script=smb-enum-groups -p 445 <target_ip>                      # → Enumerates local groups from the target via SMB.
nmap --script=smb-enum-domains -p 445 <target_ip>                     # → Attempts to enumerate Windows domains.
nmap --script=smb-ls --script-args share=IPC$ -p 445 <target_ip>      # → Lists contents of the IPC$ share if accessible.
nmap --script=smb-brute -p 445 <target_ip>                            # → Performs brute-force username/password guessing against SMB.
nmap --script=smb-check-vulns -p 445 <target_ip>                      # → Checks for known SMB vulnerabilities (MS08-067, MS17-010, etc).
nmap --script=smb-vuln-ms17-010 -p 445 <target_ip>                    # → Checks specifically for EternalBlue (MS17-010) vulnerability.
nmap --script=smb-vuln-ms08-067 -p 445 <target_ip>                    # → Checks for MS08-067 vulnerability in Windows SMB.
nmap --script=smb-vuln-cve2009-3103 -p 445 <target_ip>                # → Detects CVE-2009-3103 vulnerability in SMB2.
nmap --script=smb-vuln-* -p 445 <target_ip>                           # → Runs all SMB vulnerability detection scripts.
nmap -p 139,445 --script=default,safe,vuln -sV <target_ip>            # → Runs default, safe, and vulnerability scripts for SMB services.
nmap --script "smb-*" -p 139,445 <target_ip>                          # → Runs all available SMB enumeration scripts.
```
> #### 💡 Pro Tip: You can append -Pn to skip host discovery or -n to skip DNS resolution for faster scans when needed.

### Using SMBMap
```
smbmap -H <target_ip>                                              # → Lists SMB shares on the target host (basic enumeration).
smbmap -H <target_ip> -u <user> -p <password>                      # → Authenticated enumeration using valid credentials.
smbmap -H <target_ip> -u <user> -p ''                              # → Attempts to authenticate with a blank password (null sessions).
smbmap -H <target_ip> -u '' -p ''                                  # → Tries anonymous login to enumerate accessible shares.
smbmap -H <target_ip> -u <user> -p <password> -d <domain>          # → Authenticated scan with domain-specified credentials.
smbmap -H <target_ip> -u <user> -p <password> --shares             # → Lists available shares and their access levels.
smbmap -H <target_ip> -u <user> -p <password> --depth 5            # → Recursively enumerates directories within shares up to 5 levels deep.
smbmap -H <target_ip> -u <user> -p <password> -R                   # → Recursively lists directories and files in shares.
smbmap -H <target_ip> -u <user> -p <password> -r <share_name>      # → Lists contents of a specific share.
smbmap -H <target_ip> -u <user> -p <password> -r <share> --depth 3 # → Enumerates a specific share with directory depth of 3.
smbmap -H <target_ip> -u <user> -p <password> -R | grep -i ".txt"  # → Searches for .txt files in all accessible shares.
smbmap -H <target_ip> -u <user> -p <password> --download           # → Downloads files the user has access to from shares.
smbmap -H <target_ip> -u <user> -p <password> --upload <file>      # → Uploads a local file to writable shares.
smbmap -H <target_ip> -u <user> -p <password> --all                # → Displays all options including shares, recursion, and permissions.
smbmap -H <target_ip> -u <user> -p <password> --log smbmap.log     # → Logs all output to a file for documentation and offline analysis.

smbmap -H <target_ip> -u <user> -p <password> --execute 'cmd.exe /c whoami' 			# → Executes a command on the remote system (if permissions allow).
smbmap -H <target_ip> -u <user> -p <password> -R | grep -i "password" 				# → Looks for potentially sensitive files like password files.
smbmap -H <target_ip> -u <user> -p <password> --upload <file> --dir <remote_path> 		# → Uploads to a specific directory on the share.
smbmap -H <target_ip> -u <user> -p <password> -r <share> --download --target <directory> 	# → Downloads from a specific share to a target local directory.
```
> #### 🛡️ Tip: SMBMap is incredibly useful for lateral movement and privilege escalation in post-exploitation scenarios.
### Using enum4linux
```
enum4linux <target_ip>                                        # → Performs basic SMB enumeration (users, shares, OS info, etc.) on the target.
enum4linux -U <target_ip>                                     # → Enumerates users via SMB (RID cycling, SAMR, and NetUserEnum).
enum4linux -S <target_ip>                                     # → Enumerates shared resources (SMB shares) on the target.
enum4linux -P <target_ip>                                     # → Enumerates password policy settings from the target.
enum4linux -G <target_ip>                                     # → Enumerates groups defined on the target system.
enum4linux -N <target_ip>                                     # → Performs NetBIOS information enumeration.
enum4linux -L <target_ip>                                     # → Enumerates domain/workgroup information and server listings.
enum4linux -a <target_ip>                                     # → Runs all enumeration modules (users, shares, group, OS info, etc.) — most comprehensive.
enum4linux -u <username> -p <password> <target_ip>            # → Authenticated enumeration using valid SMB credentials.
enum4linux -d <domain> -u <user> -p <pass> <target_ip>        # → Domain-authenticated enumeration if part of a domain environment.
enum4linux -r <target_ip>                                     # → RID cycling to brute-force user/group SIDs on the target (if guest access allowed).
enum4linux -A <target_ip>                                     # → Same as -a but skips NetBIOS share enumeration (faster full sweep).
enum4linux -o output.txt <target_ip>                          # → Outputs the enumeration results to a specified file for later analysis.
```
> #### 🛡️Tip: Use -a or -A for the most thorough scan, but for stealth or segmented enumeration, invoke specific flags like -U or -S.
