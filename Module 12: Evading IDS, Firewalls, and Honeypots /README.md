# 🛡️ IDS, Firewalls, and Honeypots 
Ethical hackers should understand the function, role, placement, and design of firewalls, IDS, and IPS, as well as how attackers evade these security measures. This section provides an overview of these concepts.

## Intrusion Detection System (IDS)
**Intrusion Detection System (IDS)** is a security tool that monitors network traffic to detect and alert about suspicious or malicious activities. It continuously watches incoming and outgoing data, looking for patterns that match known attacks. When it finds something suspicious, it alerts security teams.

There are two types:

* **Passive IDS** only detects and alerts about threats.
* **Active IDS (IPS)** detects and also blocks the threats in real time.

IDS helps protect networks from breaches by identifying threats early.

### Main Functions of IDS

* **Monitors for Security Violations:**
  IDS checks systems or networks to spot unauthorized access or misuse by analyzing security policy violations.

* **Acts Like a Packet Sniffer:**
  It captures data packets traveling across communication channels like TCP/IP to inspect what’s happening in the network.

* **Analyzes Captured Packets:**
  After capturing, it carefully examines the packets to detect any signs of malicious or suspicious behavior.

* **Raises Alerts on Intrusions:**
  When it detects something unusual or harmful, it quickly alerts the administrator to take action.

### Where IDS resides in the network
**IDS (Intrusion Detection System)** is usually placed near the firewall to monitor suspicious traffic. It can be set **outside the firewall** to watch incoming threats or **inside the firewall**, especially near the **DMZ**, to catch internal attacks. The best practice is to use both—one **before** and one **after** the firewall—for layered security.

Before setting it up, it's important to study the **network layout**, understand how data moves, and identify **critical areas** that attackers might target. Once placed, the IDS should be properly configured to give the best protection.

<img width="748" height="278" alt="image" src="https://github.com/user-attachments/assets/9f22194b-6002-4d88-89e4-f0f55594b061" />

### How an IDS Works
* **Traffic Monitoring:**
  IDS uses **sensors** to scan network data and check for known **malicious signatures**. Some advanced IDS can also detect **suspicious behavior**, not just exact matches.

* **Signature Match Action:**
  If a match is found, the IDS may take action like **terminating connections**, **blocking IPs**, **dropping packets**, or **alerting admins**.

* **Anomaly Detection:**
  If no signature matches, the IDS checks for **unusual traffic patterns** (anomalies) that might indicate an attack.

* **Packet Forwarding:**
  If the traffic is clean (no match and no anomaly), the **IDS lets the packet pass** through to the network.

<img width="766" height="488" alt="image" src="https://github.com/user-attachments/assets/41c6cbd9-2b6c-4bd3-b1a9-41ffb1c18e52" />

---
## Intrusion Prevention System (IPS) 
**Intrusion Prevention System (IPS)** is a security tool that not only detects attacks but also actively blocks them. Unlike IDS, which only watches and alerts, IPS sits directly in the network path and monitors traffic in real time. It uses pre-set rules to automatically stop suspicious activity before it reaches the target. IPS helps protect against both external threats and internal risks, like insider attacks or unauthorized network access, adding a strong extra layer of defense behind the firewall.

Some of the actions that an IPS is meant to perform are as follows:
- Generate alerts if any abnormal traffic is detected in the network
- Continuously record real-time logs of network activities
- Block and filter malicious traffic
- Detect and eliminate threats quickly, as it is placed inline in the operational network
- Identify threats accurately without generating false positives

### Classification of IPS:
Like IDS, IPS are also classified into two types:
- Host-based IPS
- Network-based IPS

### Advantages of IPS over IDS: 
- Unlike IDS, IPS can block as well as drop illegal packets in the network
- IPS can be used to monitor activities occurring in a single organization
- IPS can prevent the occurrence of direct attacks in the network by controlling the amount of network traffic

<img width="761" height="222" alt="image" src="https://github.com/user-attachments/assets/33832773-ec73-4d6a-8a3e-2ddfc44c8776" />

---
## How an IDS Detects an Intrusion? 
An IDS uses three methods to detect intrusions in the network. 

### Signature Recognition
**Signature Recognition**, also called misuse detection, is a technique used in intrusion detection systems (IDS) to identify known attacks by matching network traffic with predefined attack patterns, or "signatures." These signatures are carefully designed to detect attacks without interrupting normal traffic.

It works well for **known threats**, but can generate **false positives** if normal packets match attack patterns. As more signatures are added to improve detection, it can slow down system performance and use more bandwidth. Also, small changes in attack code can bypass detection, requiring new signatures. Despite these challenges, signature-based IDS is still widely used and effective when properly configured and monitored.

### Anomaly Detection
**Anomaly Detection** is a security technique that identifies unusual behavior in a system, unlike signature-based detection that looks for known threats. It works by comparing current activity to a model of normal behavior. If something doesn’t match, it’s flagged as a possible attack.

The main challenge is building an accurate model of "normal" traffic, since real network activity can be unpredictable. Sometimes, harmless irregularities are mistaken for threats. That’s why anomaly detection works best when tailored to specific networks.

### Protocol Anomaly Detection
**Protocol Anomaly Detection** is a technique used to spot unusual or suspicious network traffic by checking if it follows the standard rules of known protocols. Since most protocols have fixed structures and behaviors, any traffic that breaks these rules could mean there’s a cyberattack or a system misconfiguration. It helps in identifying hidden threats early by watching for unexpected behavior.

**Working of a protocol anomaly detector:**
* **Baseline Behavior:**
  First, the system learns what *normal* network traffic looks like — including the usual structure, sequence, timing, and content of packets.

* **Anomaly Identification:**
  It continuously monitors traffic and flags anything that doesn’t match the baseline — like strange packet formats, out-of-order sequences, slow responses, or protocol misuse.

* **Detection Rules:**
  It uses a set of predefined rules based on protocol standards and typical behavior to decide what counts as an anomaly and when to raise an alert.

---
## General Indications of Intrusions 
Intrusion attempts on networks, systems, or file systems can be identified by following some general indicators: 

### File System Intrusions
By observing system files, the presence of an intrusion can be identified. System files record the activities of the system. Any modification or deletion of the file attributes or the file itself is a sign that the system has been a target of an attack:

* **Unknown Files/Programs:** New or unfamiliar files may indicate an attacker has placed malicious tools on the system.

* **Privilege Escalation:** Attackers may change file permissions after gaining admin access — e.g., changing files from read-only to write.

* **File Attribute Changes:** Sudden changes in file size, ownership, or permissions are warning signs of compromise.

* **Rogue SUID/SGID Files:** Unexpected SUID or SGID files (which can give elevated privileges) may point to unauthorized access.

* **Strange File Names:** Files with odd names, unknown extensions, or double extensions (e.g., `file.txt.exe`) can be suspicious.

* **Missing Files:** Legitimate files disappearing is often a sign of malicious activity or tampering.

* **Disk Space Issues:** Unexplained drop in storage space could mean hidden or unauthorized files are being stored.

* **System Lag or Crashes:** Abnormal behavior like slow performance or frequent crashes may be caused by malicious processes.

* **Bandwidth Drain:** If an attacker is using your system to attack others, it can consume significant bandwidth and slow down the network.

### Network Intrusions 
Similarly, general indications of network intrusions include: 
* **High Bandwidth Usage:**
  A sudden spike in data usage may indicate large-scale data theft or DoS activity.

* **Service Probing:**
  Continuous scanning of your devices shows someone is trying to find weak points to attack.

* **Unknown IP Connection Attempts:**
  If you see access requests from outside your network, it could be an intruder trying to break in.

* **Multiple Failed Logins:**
  Repeated login attempts from unknown sources may signal a brute-force attack.

* **Heavy Log Generation:**
  A flood of log entries could mean attempted DoS/DDoS attacks or other unusual activity.

* **Unexpected Network Changes:**
  Unauthorized changes to firewall or network settings may mean the attacker has gained access.

* **System Slowness or Crashes:**
  Intrusion can overload your network and crash systems with too much traffic.

* **Strange Outbound Traffic:**
  If your network is connecting to suspicious or malicious websites, it might be compromised.

### System Intrusions 
Similarly, general indications of system intrusions include: 
* **Short or Incomplete Logs:**
  Attackers may delete or modify logs to hide their actions.

* **Slow System Performance:**
  Malware or attacker tools can consume system resources, slowing things down.

* **Missing or Misconfigured Logs:**
  Logs may be missing or have incorrect permissions to prevent detection.

* **Modified System Files:**
  Key system or config files may be altered to gain control or persistence.

* **Strange Text or Graphics:**
  Unexpected messages or visual glitches may indicate tampering.

* **Missing Audit Records:**
  Gaps in accounting data can suggest attacker activity.

* **Unexpected Reboots or Crashes:**
  System instability can result from malicious software.

* **Unknown Running Processes:**
  Suspicious or unfamiliar programs could be attacker tools.

* **Antivirus/IDS Alerts:**
  Security tools may detect signs of compromise.

* **Unauthorized Software:**
  New apps that weren’t installed by users or admins are a red flag.

* **Strange Files or Artifacts:**
  Shell history, temp files, or leftover attack tools may remain on the system.

---
## Types of Intrusion Detection Systems 
Types of Intrusion Detection Systems There are two types of intrusion detection systems:

### Network-Based Intrusion Detection Systems 
**Network-Based Intrusion Detection Systems (NIDS)** are tools that monitor all incoming network traffic to detect suspicious or malicious activity. They inspect each data packet in detail, generate alerts based on threats at the IP or application level, and log harmful activity. Unlike host-based systems, NIDS are placed across the network (like at routers) and work in **promiscuous mode** to catch threats like **DoS attacks**, **port scans**, or hacking attempts. They also assign a **threat level** to help security teams stay alert and respond quickly.

<img width="613" height="294" alt="image" src="https://github.com/user-attachments/assets/1039dab3-e20b-429a-b29e-9d430120f6ed" />

### Host-Based Intrusion Detection Systems 
**Host-Based Intrusion Detection Systems (HIDS)** monitor the behavior of individual systems like desktops or servers. They are useful for detecting unauthorized actions, such as file changes or insider threats, by focusing on what’s happening locally on the machine. HIDS is especially strong on Windows systems but also available for UNIX. Although effective, they are less common due to the system resources they consume while tracking all events on a host.

<img width="722" height="363" alt="image" src="https://github.com/user-attachments/assets/248c71ee-8c32-443f-8e76-9c5f28f63339" />

---
## Types of IDS Alerts 
An IDS generates four types of alerts: True Positive, False Positive, False Negative, and True Negative. 

* **True Positive (Attack - Alert):**
  The IDS correctly detects an actual attack and raises an alert. This is the expected and accurate behavior.

* **False Positive (No Attack - Alert):**
  The IDS raises an alert, but there’s no real attack. It mistakes normal activity as malicious, which can lead to unnecessary panic or alert fatigue.

* **False Negative (Attack - No Alert):**
  The IDS fails to detect an actual attack. This is dangerous because threats go unnoticed and can cause damage.

* **True Negative (No Attack - No Alert):**
  The IDS correctly identifies normal activity and stays silent. This means the system is working properly without unnecessary alerts.

---
## Firewall 
A **firewall** is a security system—either hardware or software—that located at the gateway between a private network and a public network like the Internet. Its main job is to monitor and filter incoming and outgoing traffic based on predefined security rules. It blocks unauthorized access while allowing safe communication.

Firewalls can filter traffic by **IP address, port, or protocol type** and perform **security checks** at checkpoints. They log all access attempts, alert admins of suspicious activity, and can even detect intruders trying to access the network. When properly set up, a firewall acts like a security guard, only letting in traffic that meets the rules and protecting private network resources from external threats.

<img width="752" height="215" alt="image" src="https://github.com/user-attachments/assets/ed108dc0-bcee-48a7-8bf6-ed21460dbfc0" />

---
## Firewall Architecture 
The firewall architecture consists of the following elements: 

### Bastion Host
**Bastion Host** is a special computer set up to protect a network from external attacks. It acts as a secure bridge between the internet and the internal network. All incoming and outgoing traffic passes through it. It has two interfaces: one connects to the public internet, and the other connects to the private intranet, allowing controlled and secure access to internal systems.

<img width="430" height="180" alt="image" src="https://github.com/user-attachments/assets/71c62b9d-5fcc-4e26-8d6e-09b25b6f7f00" />

### Screened Subnet
A **Screened Subnet**, also known as a **DMZ (Demilitarized Zone)**, is a separate, protected network placed between the public Internet and a private internal network. It's created using a **three-homed firewall**, where one connection goes to the Internet, one to the DMZ, and one to the internal network. The DMZ handles public requests (like web servers), but keeps the internal network hidden and secure.

This setup allows users to access public services without risking the private network. However, if the single firewall is hacked, both the DMZ and internal network are at risk. A more secure approach is to use **two firewalls**—one between the Internet and DMZ, and another between the DMZ and internal network.

<img width="440" height="158" alt="image" src="https://github.com/user-attachments/assets/ed03b6f5-3d97-4209-a078-2c39bb42150a" />

### Multi-homed Firewall
**Multi-homed Firewall** is a security device with multiple network interfaces (NICs) that connects to two or more networks. Each interface is linked to a different network segment, both physically and logically. This setup improves the network’s efficiency and reliability. With more than three interfaces, it can separate systems based on different security needs. While it offers strong protection, a **back-to-back firewall** provides even deeper security.

<img width="408" height="167" alt="image" src="https://github.com/user-attachments/assets/565109ce-1ef0-4a5f-b03f-6aa3cda2e2f4" />

---
## Demilitarized Zone (DMZ) 
**Demilitarized Zone (DMZ)** in networking is a security zone that sits between a company’s internal network and the public internet. It acts as a **buffer** to keep private data safe from external threats. Services like **email, web, or FTP servers** that need internet access are placed in the DMZ, while the internal network remains protected behind a firewall.

A DMZ is set up using a **firewall** with multiple interfaces—one for the internal network, one for the DMZ, and one for the internet. This setup ensures that even if DMZ servers are compromised, attackers can’t directly reach the internal systems.

<img width="791" height="238" alt="image" src="https://github.com/user-attachments/assets/e4337ffb-d879-46e7-bc11-69554cd1d209" />

---
## Types of Firewalls 
There are two types of firewalls, each developed with specific features and capabilities that consider different network environments and security needs. Understanding these categories is essential for implementing effective firewall technologies to secure networks. 

### Types of Firewalls Based on Configuration

#### Network-based firewalls
**Network-based firewalls** are security devices placed at the edge of a network to control incoming and outgoing traffic. They use **packet filtering** to check the source and destination of data packets against a set of rules, deciding whether to allow or block them. These firewalls can be built into routers or used as standalone systems, like **Cisco ASA** or **FortiGate**, and are mainly used to protect internal networks. While effective, they can be costly and complex to set up and maintain.

#### Advantages:
- **Security:** A network-based firewall with its operating system (OS) is considered to reduce security risks and increase the level of security controls.
- **Speed:** network-based firewalls initiate faster responses and enable more traffic.
- **Minimal Interference:** Since a network-based firewall is a separate network component, it enables better management and allows the firewall to shut down, move, or be reconfigured without much interference in the network.

#### Disadvantages:
- More expensive than a host-based firewall.
- Difficult to implement and configure.
- Consumes more space and involves cabling.

#### Host-based Firewalls
**Host-based firewalls** are security tools installed directly on a device like a PC, laptop, or server to block unauthorized access and protect against threats like Trojans and email worms. They work like filters, sitting between applications and the operating system's network functions, checking all incoming and outgoing data based on user-defined rules.

These firewalls are easy to install, great for home or mobile users, and offer features like **privacy controls**, **web filtering**, and **content blocking**. While they provide strong individual protection, they use more system resources and may slow down performance. Popular examples include **Norton**, **McAfee**, and **Kaspersky** firewalls.

#### Advantages:
- Less expensive than network-based firewalls.
- Ideal for personal or home use.
- Easier to configure and reconfigure.

#### Disadvantages:
- Consumes system resources.
- Difficult to uninstall.
- Not appropriate for environments requiring faster response times.

### Types of Firewalls Based on Working Mechanism 
**Types of Firewalls Based on Working Mechanism** refer to the different ways firewalls monitor and control network traffic. Depending on where the firewall is placed and how it analyzes traffic (like by checking communication points, traffic flow, or connection states), different types are used to meet specific security needs. Each type has its own strengths, and sometimes technologies like **NAT** (normally used for routing) are combined with firewalls to enhance protection. Choosing the right firewall depends on the network setup and the level of security required.

The various firewall technologies are listed below:
- Packet Filtering
- Circuit-Level Gateways
- Application-Level Firewall
- Stateful Multilayer Inspection
- Application Proxies
- Network Address Translation
- Virtual Private Network

The table below summarizes technologies operating at each OSI layer: 
| **OSI Layer**   | **Firewall Technology**                                                                 |
|----------------|------------------------------------------------------------------------------------------|
| Application     | - Virtual Private Network (VPN)  <br> - Application Proxies                            |
| Presentation    | - Virtual Private Network (VPN)                                                        |
| Session         | - Virtual Private Network (VPN)  <br> - Circuit-Level Gateways                         |
| Transport       | - Virtual Private Network (VPN)  <br> - Packet Filtering                                |
| Network         | - Virtual Private Network (VPN)  <br> - Network Address Translation (NAT)  <br> - Packet Filtering  <br> - Stateful Multilayer Inspection |
| Data Link       | - Virtual Private Network (VPN)  <br> - Packet Filtering                                |
| Physical        | - Not Applicable                                                                        |

The **security level of different technologies** depends on how well they work across the **OSI layers**. As data moves from the top layer to the bottom, each layer adds extra information to the packet. Then, it travels through the network, and the receiving system processes it from the bottom layer back up. By comparing how technologies handle security at each layer, we can better understand their overall protection level.

---
## Packet Filtering Firewall 
A **Packet Filtering Firewall** checks each network packet against a set of rules before allowing it through. It looks at details like the source and destination IP address, port number, and protocol. Based on this, it either blocks the packet, forwards it, or sends a message back. This firewall works at the **network layer (OSI)** or **internet layer (TCP/IP)** and focuses only on packet headers to decide the direction of traffic.

Traditional packet filters check each packet based on specific criteria:
* **Source IP Address**: Verifies where the packet came from.
* **Destination IP Address**: Confirms the packet is going to the right destination.
* **Source Port**: Checks which port on the sender's side is used.
* **Destination Port**: Decides if the requested service (like HTTP, FTP) is allowed or blocked.
* **TCP Flags**: Looks at connection bits like SYN or ACK to understand the connection status.
* **Protocol Used**: Filters based on the protocol (e.g., TCP, UDP, ICMP).
* **Direction**: Identifies if the packet is going into or out of the network.
* **Interface**: Checks if the packet is coming from a trusted or untrusted network zone.

<img width="792" height="255" alt="image" src="https://github.com/user-attachments/assets/42bc8b88-a37d-4fc8-915f-d2e22fd49a9b" />

---
## Circuit-Level Gateway Firewall 
