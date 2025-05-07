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
# 🧠OS Discovery (Banner Grabbing/OS Fingerprinting) 
# 🕵️Scanning Beyond IDS and Firewall  
# 🛡️Network Scanning Countermeasures 
