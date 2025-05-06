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
# 🚪Port and Service Discovery
# 🧠OS Discovery (Banner Grabbing/OS Fingerprinting) 
# 🕵️Scanning Beyond IDS and Firewall  
# 🛡️Network Scanning Countermeasures 
