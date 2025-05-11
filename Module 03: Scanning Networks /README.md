# 🔍🌐Scanning Networks
Network scanning refers to a set of procedures used for identifying hosts, ports, and services in a network. Network scanning is one of the components of information gathering which can be used by an attacker to create a profile of the target organization. Attackers use tools such as **Nmap**, **Hping3**, **Metasploit**, and **NetScan** Tools Pro to perform network scanning. 
## Objectives of Network Scanning 
- To discover live hosts, IP address, and open ports of live hosts
- To discover operating systems and system architecture 
- To discover services running on hosts 
- To discover vulnerabilities in live hosts

# 🛠️Scanning Tools 
Scanning tools are used to scan and identify live hosts, open ports, running services on a target network, location info, NetBIOS info, and information about all TCP/IP and UDP open ports. The information obtained from these tools will help an ethical hacker in creating the profile of the target organization and scanning the network for open ports of the devices connected.
## Nmap 
🔗Source: [https://nmap.org]

Nmap (Network Mapper) is a open-source tool used for network discovery and security auditing. It also assists in the exploration of network hosts and services, providing information about open ports, operating systems, and other details.
### Command Syntax
```
nmap <option> <target>
```
## Hping3
🔗Source: [https://salsa.debian.org]

Hping3 is a command-line tool used by ethical hackers and penetration testers to test networks and firewalls by sending specially crafted packets. It's like an advanced version of ping that not only checks if a host is online, but also helps gather deep information about a target system. It can send different types of packets like TCP, UDP, and ICMP, which allows testers to scan for open ports, detect firewalls, guess the operating system of a target, and even send hidden data. Unlike regular tools, Hping3 can bypass some security filters, making it useful for advanced network testing or stealthy reconnaissance.
### Command Syntax & Examples
```
hping3 <option> <target>

hping3 -1 <target>                                # → Sends ICMP echo requests (like `ping`) to check if the host is up.
hping3 -A <target> -p <port>                      # → Sends TCP ACK packets to the specified port to test firewall filtering.
hping3 -2 <target> -p <port>                      # → Sends UDP packets to the specified port to check for open/closed UDP ports.
hping3 <target> -Q -p <port>                      # → Performs a TCP sequence number prediction test (used for spoofing attacks).
hping3 -S <target> -p <port> --tcp-timestamp      # → Sends SYN packets with TCP timestamp to help in OS fingerprinting.
hping3 -8 <Port_Range> -S <target> -v             # → Performs a SYN scan on a range of ports with verbose output.
hping3 -F -P -U <target> -p <port>                # → Sends TCP packets with FIN, PSH, and URG flags (Xmas scan technique).
hping3 -1 <target> --rand-dest -I eth0            # → Sends ICMP echo requests to random IPs on interface eth0 (network sweep).
hping3 -9 HTTP -I eth0                            # → Listens on interface eth0 and displays packets that contain the string "HTTP".
hping3 -S <target> -a <Spoof_IP> -p <port> --flood # → Sends a flood of SYN packets with spoofed IP to perform a DoS attack.
```
## Metasploit
🔗Source: [https://www.metasploit.com]

Metasploit is a powerful tool used in cybersecurity to find and test weaknesses in computer systems. It helps ethical hackers and security professionals perform penetration testing by automating the process of finding vulnerabilities and exploiting them in a controlled way. With Metasploit, users can mix and match different attack methods and payloads, making it flexible and effective for testing system defenses. It also helps create reports and even allows testing deeper parts of a network after gaining access.

## NetScanTools Pro 
🔗Source: [https://www.netscantools.com]

NetScanTools Pro is a tool used to collect detailed information about networks and devices. It helps users, including ethical hackers, find things like IP addresses, open ports, domain names, and email addresses. This information can be used to check for weaknesses or troubleshoot network issues. It combines many smaller tools into one program, making it easier to monitor and analyze both local and internet-connected systems.

## Some additional scanning tools are listed below: 
- sx 🔗Source: [https://github.com/v-byte-cpu/sx]
- RustScan 🔗Source: [https://github.com/bee-san/RustScan]
- MegaPing 🔗Source: [http://magnetosoft.com]
- SolarWinds®Engineer's Toolset 🔗Source: [https://www.solarwinds.com]
- PRTG Network Monitor 🔗Source: [https://www.paessler.com]

# 🖥️Host Discovery 
Host Discovery is the process of finding out which devices (hosts) are active and connected to a network. It's often the first step in network scanning or penetration testing, helping identify live systems that can be further analyzed or tested.
## Host Discovery Techniques 
Host discovery techniques can be adopted to discover the active/live hosts in the network.

```
nmap -sn -PR <target>        # → ARP Ping Scan: Sends ARP requests to detect live hosts.
nmap -sn -PU 53 <target>     # → UDP Ping Scan: Sends empty UDP packets to port 53 (DNS) to check if host is alive.
nmap -sn -PE <target>        # → ICMP Echo Ping Scan: Sends ICMP Echo Request (like "ping") to detect live hosts.
nmap -sn -PE -PS80 <target>  # → ICMP Echo Ping Sweep: Combines ICMP Echo with SYN ping to scan multiple hosts.
nmap -sn -PP <target>        # → ICMP Timestamp Ping Scan: Sends ICMP timestamp request to find responsive hosts.
nmap -sn -PM <target>        # → ICMP Address Mask Ping Scan: Sends ICMP address mask request to check for active hosts.
nmap -sn -PS80 <target>      # → TCP SYN Ping Scan: Sends TCP SYN to port 80 to determine if host is up.
nmap -sn -PA443 <target>     # → TCP ACK Ping Scan: Sends TCP ACK to port 443 to bypass firewalls and find live hosts.
nmap -sn -PO <target>        # → IP Protocol Ping Scan: Sends IP packets with different protocol numbers to detect live hosts.
```
> #### Note: -sn is the Nmap command to disable the port scan. Since Nmap uses ARP ping scan as the default ping scan, to disable it and perform other desired ping scans, you can use --disable-arp-ping.
> ```
> nmap -sn --disable-arp-ping -PE <target>
> ```

## Ping Sweep Tools
Ping sweep tools ping an entire range of network IP addresses to identify the live systems. The following are ping sweep tools that enable one to determine live hosts on the target network by sending multiple ICMP ECHO requests to various hosts on the network at a time.

- **Angry IP Scanner:** 🔗Source: [https://angryip.org]
- **SolarWinds Engineer’s Toolset:**  🔗Source: [https://www.solarwinds.com]
- **NetScanTools Pro:** 🔗Source: [https://www.netscantools.com]
- **Colasoft Ping Tool:** 🔗Source: [https://www.colasoft.com]
- **Advanced IP Scanner:** 🔗Source: [https://www.advanced-ip-scanner.com]
- **OpUtils:** 🔗Source: [https://www.manageengine.com]

# 🚪Port and Service Discovery
Port and Service Discovery is the process of finding which ports are open on a target system and what services are running on those ports. This helps ethical hackers or penetration testers understand what software or services are exposed to the network and potentially exploitable.

## Lists of common Ports and Services
```
================================================================================================================================================================================================================================================
Name		Port/Protocol		Description		|	Name		Port/Protocol		Description				|	Name		Port/Protocol		Description
====		=============		===========		|	====		=============		===========				|	====		=============		===========
echo		7/tcp, udp		echo			|	netbios-dgm     138/tcp, udp          	netbios datagram service		|	ntalk           518/udp               	sunos talkd
discard		9/tcp, udp		sink null		|	netbios-ssn     139/tcp, udp          	netbios session service			|	netnews         532/tcp, udp          	readnews
systat		11/tcp			users			|	imap            143/tcp, udp          	internet message access protocol	|	uucp            540/tcp, udp          	uucpd
daytime		13/tcp, udp 		daytime			|	sql-net         150/tcp, udp          	sql-net					|	klogin          543/tcp, udp          	kerberos login					
netstat		15/tcp, udp		netstat			|	sqlsrv          156/tcp, udp          	sql service				|	kshell          544/tcp, udp          	kerberos shell
qotd            17/tcp, udp          	quote			|	snmp            161/tcp, udp          	snmp					|	ekshell         545/tcp               	krcmd kerberos encrypted remote shell
chargen         19/tcp, udp          	ttytst source		|	snmp-trap       162/tcp, udp          	snmp-trap				|	pcserver        600/tcp               	ecd integrated pc board server
ftp-data        20/tcp               	ftp data transfer	|	cmip-man        163/tcp, udp          	cmip/tcp manager			|	mount           635/udp               	nfs mount service
ftp             21/tcp               	ftp command		|	cmip-agent      164/tcp, udp          	cmip/tcp agent				|	pcnfs           640/udp               	pc-nfs dos authentication
ssh             22/tcp               	secure shell		|	irc             194/tcp, udp          	internet relay chat			|	bwnfs           650/udp               	bw-nfs dos authentication
telnet          23/tcp               	telnet			|	at-rtmp         201/tcp, udp          	appletalk routing maintenance		|	flexlm          744/tcp, udp          	flexible license manager
smtp            25/tcp               	email server		|	at-nbp          202/tcp, udp          	appletalk name binding			|	kerberos-adm    749/tcp, udp          	kerberos administration
time            37/tcp, udp          	timeserver		|	at-3            203/tcp, udp          	appletalk				|	kerberos-master 751/tcp, udp          	kerberos authentication
rlp             39/tcp, udp          	resource location	|	at-echo         204/tcp, udp          	appletalk echo				|	krb_prop        754/tcp               	kerberos slave propagation
domain          53/tcp, udp          	domain name server	|	at-5            205/tcp, udp          	appletalk				|	applix          999/udp               	applixware
sql*net         66/tcp, udp          	Oracle SQL*net		|	at-zis          206/tcp, udp          	appletalk zone information		|	socks           1080/tcp, udp         	socks proxy
bootps          67/udp                	bootp server		|	at-7            207/tcp, udp          	appletalk				|	kpop            1109/tcp              	pop with kerberos
bootpc          68/udp                	bootp client		|	at-8            208/tcp, udp          	appletalk				|	ms-sql-s        1433/tcp, udp         	microsoft sql server
tftp            69/udp                	trivial file transfer	|	ipx             213/tcp, udp          	novell					|	ms-sql-m        1434/tcp, udp         	microsoft sql monitor
gopher          70/tcp                	gopher server		|	imap3           220/tcp, udp          	interactive mail access protocol v3	|	pptp            1723/tcp, udp         	pptp
finger          79/tcp                	finger			|	aurp            387/tcp, udp          	appletalk update-based routing		|	nfs             2049/tcp, udp         	network file system
www-http        80/tcp, udp           	www			|	netware-ip      396/tcp, udp          	novell netware over IP			|	eklogin         2105/tcp              	kerberos encrypted rlogin
www-https       443/tcp               	https			|	rmt             411/tcp, udp          	remote mt				|	rkninit         2108/tcp              	kerberos remote kinit
kerberos        88/tcp, udp           	kerberos		|	kerberos-ds     445/tcp, udp          	microsoft ds				|	kx              2111/tcp              	x over kerberos
pop2            109/tcp               	postoffice v.2		|	isakmp          500/udp               	isakmp/ike				|	kauth           2120/tcp              	remote kauth
pop3            110/tcp               	postoffice v.3		|	fcp             510/tcp               	first class server			|	lyskom          4894/tcp              	lyskom (conference system)
sunrpc          111/tcp, udp          	rpc 4.0 portmapper	|	exec            512/tcp               	bsd rexecd				|	sip             5060/tcp, udp         	session initiation protocol
auth/ident      113/tcp, udp          	authentication service	|	comsat/biff     512/udp               	notify users				|	x11             6000-6063/tcp, udp    	x window system
audionews       114/tcp, udp          	audio news multicast	|	login           513/tcp               	bsd rlogind				|	irc              6667/tcp              	internet relay chat
nntp            119/tcp               	usenet news		|	who             513/udp               	whod/rwhod				|
ntp             123/udp               	network time protocol	|	shell           514/tcp               	cmd bsd rshd				|	
netbios-ns      137/tcp, udp          	netbios name service	|	syslog          514/udp               	bsd syslogd				|
								|	printer         515/tcp, udp          	spooler bsd lpd				|
								|	talk            517/tcp, udp          	bsd talkd				|
```
Nmap Commands to Port and Service Discovery
```
# => TCP Connect/Full-Open Scan → Performs a full TCP three-way handshake
nmap -sT <target>

# => Stealth Scan (Half-Open Scan) → Sends SYN and waits for SYN-ACK (no full handshake)
nmap -sS <target>

# => Inverse TCP Flag Scan → Sends TCP packets with FIN, URG, and PSH flags to evade detection
nmap -sN <target>      # => TCP Null Scan
nmap -sF <target>      # => FIN Scan
nmap -sX <target>      # => Xmas Scan

# => TCP Maimon Scan → Exploits TCP stack behavior by sending FIN/ACK flagged packets
nmap -sM <target>

# => ACK Flag Probe Scan → Used to map firewall rulesets
nmap -sA <target>

# => TTL-Based ACK Flag Probe scanning → Reveals filtered vs unfiltered via TTL values (advanced script)
nmap -sA --ttl 128 <target>       # Adjust TTL as needed

# => Window-Based ACK Flag Probe scanning → Reveals stateful vs stateless filtering via TCP window size
nmap -sA --reason <target>

# => IDLE/IPID Header Scan → Stealth scan using a zombie host to avoid detection
nmap -sI <zombie_ip> <target>

# => UDP Scan → Sends UDP packets to detect open/filtered/closed UDP ports
nmap -sU <target>

# => SCTP INIT Scan → Performs an SCTP scan using INIT chunks (similar to TCP SYN)
nmap -sY <target>

# => SCTP COOKIE ECHO Scan → Sends COOKIE-ECHO chunks to detect open SCTP ports (more stealthy)
nmap -sZ <target>

# => SSDP and List Scan → SSDP is useful for IoT enumeration, list scan shows resolved hostnames
nmap -sL --script=ssdp-discover <target>

# => IPv6 Scan → Scans targets using IPv6 addresses
nmap -6 <ipv6-address>

# => Service Version Discovery → Detects running services and their versions
nmap -sV <target>
```
> #### Note: Replace <target> with the IP address or hostname of the system you want to scan. Replace <zombie_ip> with a suitable idle host for IPID scans.

# 🧠OS Discovery (Banner Grabbing/OS Fingerprinting)
OS Discovery (also known as Banner Grabbing or OS Fingerprinting) is the process of identifying the operating system running on a target machine during a scan.
- **Banner Grabbing:** Collects text (banners) shown by services like FTP, HTTP, or SSH, which often includes the OS name or version.
- **OS Fingerprinting:** Analyzes how a system responds to specific network traffic to guess its operating system (like Linux, Windows, etc.).

## Types of Banner Grabbing
1. **Active banner grabbing** means sending special or unusual network packets to a target computer to see how it responds. Every operating system (like Windows or Linux) handles these packets a bit differently because each has its own way of implementing network rules (TCP/IP stack). By looking at these responses and comparing them to a known database, we can guess what OS the target is using.
2. **Passive Banner Grabbing** is a way to find out the operating system of a device without directly sending any packets to it. Instead of scanning the device, it just watches (sniffs) the network traffic coming from the device and studies how it communicates. Different operating systems have unique ways of responding to network traffic, and passive tools use those small differences to guess the OS—quietly and without alerting the target. 🔗Source: [https://www.broadcom.com]

## TTL & Window size values for difference OS's
![CEH_Tools png](https://github.com/user-attachments/assets/b3257f8d-5996-42ba-8660-be0aa02cce97)

## OS Discovery using Wireshark 
🔗Source: [https://www.wireshark.org]

OS discovery using Wireshark works by capturing network traffic between your system and the target. When the target responds to your request, you can look at specific details in the response—like the TTL (Time To Live) and TCP Window Size—in the first TCP packet it sends back. Different operating systems use different default values for TTL and window size, so by comparing those values with known standards, you can guess which OS the target is using.

![WinOS](https://github.com/user-attachments/assets/de5cfe01-9036-4a1a-b0ec-7d31ac386017)

👉 For example, a TTL of 128 might suggest Windows, while 64 might suggest Linux.
## OS Discovery using Nmap & NSE Script
🔗Source: [https://nmap.org]
```
nmap -O <target>	# → Operating system detection
nmap -sC <target>	# → To run Nmap NSE Script
nmap -6 -O <target>	# → OS Discovery using IPv6 Fingerprinting
nmap --script <script> <target> 	# → Custom NSE Scipt
```
## OS Discovery using Unicornscan 
🔗Source: [https://sourceforge.net]
```
unicornscan -Iv <target_ip>
```
# 🕵️Scanning Beyond IDS and Firewall  
Though firewalls and IDSs can prevent malicious traffic (packets) from entering a network, attackers can manage to send intended packets to the target by evading an IDS or firewall through the following techniques:
## Packet Fragmentation
- Packet fragmentation refers to the splitting of a probe packet into several smaller packets (fragments) while sending it to a network
- It is not a new scanning method but a modification of the previous techniques
- The TCP header is split into several packets so that the packet filters are not able to detect what the packets are intended to do
```
nmap -sS -T4 -A -f -v <target>
```
## Source Routing
- As the packet travels through the nodes in the network, each router examines the destination IP address and chooses the next hop to direct the packet to the destination
- Source routing refers to sending a packet to the intended destination with a partially or completely specified route (without firewall-/IDS-configured routers) in order to evade an IDS or firewall
- In source routing, the attacker makes some or all of these decisions on the router
## Source Port Manipulation
- Source port manipulation refers to manipulating actual port numbers with common port numbers in order to evade an IDS or firewall 
- It occurs when a firewall is configured to allow packets from well-known ports like HTTP, DNS, FTP, etc. 
- Nmap uses the -g or --source-port options to perform source port manipulation
```
nmap -g 80 <target>
nmap --source-port 21 <target>
```
## IP Address Decoy
- IP address decoy technique refers to generating or manually specifying the IP addresses of decoys in order to evade an IDS or firewall 
- It appears to the target that the decoys as well as the host(s) are scanning the network 
- This technique makes it difficult for the IDS or firewall to determine which IP address was actually scanning the network and which IP addresses were decoys
### Decoy Scanning using Nmap 
Nmap has two options for decoy scanning: 
```
nmap -D RND: 10 [target] 			# → Generates a random number of decoys
nmap -D decoyl, decoy2, decoy3,... <target> 	# → Manually specify the IP addresses of the decoys
```
## IP Address Spoofing
- IP spoofing refers to changing the source IP addresses so that the attack appears to be coming from someone else 
- When the victim replies to the address, it goes back to the spoofed address rather than the attacker's real address 
- Attackers modify the address information in the IP packet header and the source address bits field in order to bypass the IDS or firewall
IP spoofing using Hping3:
```
Hping3 <target> -a <spoofed_IP>
```
## MAC Address Spoofing
- The MAC address spoofing technique involves spoofing a MAC address with the MAC address of a legitimate user on the network 
- Attackers use the --spoof-mac Nmap option to set a specific MAC address for the packets to evade firewalls
```
nmap -sT -Pn --spoof-mac 0 <target>		# → --spoof-mac 0 represents the randomization of the MAC address.
nmap -sT -Pn --spoof-mac <Vendor> <target>	# → --spoof-mac [vendor] represents the randomization of the MAC address based on the specified vendor (DELL, HP, CISCO, etc).
nmap -sT -Pn --spoof-mac <new MAC> <target>	# → --spoof-mac [new MAC] represents manually setting the MAC address.
```
## Creating Custom Packets
The attacker creates and sends custom packets to scan the intended target beyond the IDS/firewalls. Various techniques are used to create custom packets. Some of them are mentioned below:
### Creating Custom Packets by using Packet Crafting Tools 
Attackers create custom TCP packets to scan the target by bypassing the firewalls. Attackers use various packet crafting tools such as Colasoft packet builder [https://www.colasoft.com], NetScanTools Pro [https://www.netscantools.com], etc., to scan the target that is beyond the firewall. Packet crafting tools craft and send packet streams (custom packets) using different protocols at different transfer rates.
- Colasoft Packet Builder
🔗Source: [https://www.colasoft.com]

Colasoft Packet Builder is a tool that allows an attacker to create custom network packets and helps security professionals assess the network. The attacker can select a TCP packet from the provided templates and change the parameters in the decoder, hexadecimal, or ASCII editor to create a packet. In addition to building packets, Colasoft Packet Builder supports saving packets to packet files and sending packets to the network.

![Colasoft](https://github.com/user-attachments/assets/378d2182-9ea0-4486-bb50-07441e93e8a7)


There are three views in the Packet Builder: Packet List, Decode Editor, and Hex Editor.
- **Packet List** displays all the constructed packets. When you select one or more packets in Packet List, the first highlighted packet is displayed in both Decode Editor and Hex Editor for editing.
- In **Hex Editor**, the data of the packet are represented as hexadecimal values and ASCII characters; nonprintable characters are represented by a dot (".") in the ASCII section. You can edit either the hexadecimal values or the ASCII characters.
- **Decode Editor** allows the attacker to edit packets without remembering the value length, byte order, and offsets. You can select a field and change the value in the edit box.

For creating a packet, you can use the add or insert packet command in the Edit menu or the Toolbar to create a new packet.

## Randomizing Host Order
Attackers scan the number of hosts in the target network in random order to scan an intended target that is behind a firewall 

```
nmap --randomize-hosts <target>
```
## Sending Bad Checksums
Attackers send packets with bad or bogus TCP/UPD checksums to the intended target to avoid certain firewall rulesets 
```
nmap --badsum <target>
```
## Proxy Servers
Proxy server is an application that can serve as an intermediary for connecting with other computers.

### Proxy Tools 
Proxy tools are intended to allow users to surf the Internet anonymously by keeping their IP hidden through a chain of SOCKS or HTTP proxies. These tools can also act as HTTP, mail, FTP, SOCKS, news, telnet, and HTTPS proxy servers.
- **Proxy Switcher** 🔗Source: [https://www.proxyswitcher.com]

Proxy Switcher allows attackers to surf the Internet anonymously without disclosing their IP address. It also helps attackers to access various blocked sites in the organization. In addition, it avoids all sorts of limitations imposed by target sites.

![ProxySwitcher](https://github.com/user-attachments/assets/db3f1af7-7b45-4e28-9013-cb2a203f08a7)

- **CyberGhost VPN** 🔗Source: [https://www.cyberghostvpn.com]

CyberGhost VPN hides the attacker's IP and replaces it with a selected IP, allowing him or her to surf anonymously and access blocked or censored content. It encrypts the connection and does not keep logs, thus securing data.

![CyberGhostVPN](https://github.com/user-attachments/assets/f4f05732-e135-4c4a-b21b-f58bdd14f896)

Some additional proxy tools are listed below:
- **Burp Suite** [https://www.portswigger.net]
- **Tor** [https://www.torproject.org]
- **Hotspot Shield** [https://www.hotspotshield.com]
- **Proxifier** [https://www.proxifier.com]
- **IPRoyal Residential Proxy** [https://iproyal.com]

## Anonymizers
An anonymizer is a tool or service that hides your identity when you browse the internet. It works like a middleman between you and the website you’re visiting. Instead of the website seeing your real IP address, it sees the anonymizer’s address, which helps keep your activities private and lets you bypass internet restrictions. Anonymizers can also encrypt your data so your ISP can’t see what you're doing. People use anonymizers to stay anonymous online, but attackers might misuse them to hide their malicious actions.

Anonymizer tools use various techniques such as SSH, VPN, and HTTP proxies, which allow access to blocked or censored content on the Internet with advertisements omitted. 

- **Whonix** 🔗Source: [https://www.whonix.org]

Whonix is a desktop OS designed for advanced security and privacy. It mitigates the threat of common attack vectors while maintaining usability. Online anonymity is realized via fail-safe, automatic, and desktop-wide use of the Tor network. It consists of a heavily reconfigured Debian base that is run inside multiple virtual machines, providing a substantial layer of protection from malware and IP address leaks.

Some additional anonymizers are listed below:
- **Psiphon** [https://psiphon.ca]
- **TunnelBear** [https://www.tunnelbear.com]
- **Invisible Internet Project (I2P)** [https://geti2p.net]
- **Bright Data Proxy API** [https://brightdata.com]

### Censorship Circumvention Tools 
- **AstrillVPN:** AstrillVPN is a VPN software that enables attackers to bypass Internet censorship and access geo-blocked websites, apps, and services by hiding their IP and location. It offers data encryption and transmission technology and avoids logging traffic data and DNS queries to prevent tracking of browsing activity and metadata. 🔗Source: [https://www.astrill.com]
- **Tails:** Tails is a live OS that users can run on any computer from a USB stick or SD card. It uses state-of-the-art cryptographic tools to encrypt files, emails, and instant messaging. It allows attackers to use the Internet anonymously and circumvent censorship. It leaves no trace on the computer. 🔗Source: [https://tails.net]
- 

 

# 🛡️Network Scanning Countermeasures 
