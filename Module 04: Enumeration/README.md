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
SNMP (Simple Network Management Protocol) is a protocol used to manage and monitor network devices like routers, switches, servers, printers, and more. It allows network administrators to collect information about these devices, configure them, and detect issues in real-time. 

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
# ✉️ SMTP Enumeration
# 🌐 DNS Enumeration
# 🧪 Other Enumeration Techniques
