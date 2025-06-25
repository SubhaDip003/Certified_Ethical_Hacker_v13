# 📡Sniffing Concepts
---
## Network Sniffing
**Network Sniffing** is the process of capturing and monitoring data packets that travel across a network. Attackers use sniffing tools to collect sensitive information like passwords, emails, and credit card details. In older hub-based networks, sniffing is easy because data is broadcasted to all devices. Modern networks use **switches**, which send data only to the intended device, making sniffing harder.

However, attackers can still bypass this by putting a device in **promiscuous mode** or installing sniffers on key network points like servers or routers. This lets them monitor large amounts of traffic from one location. Sniffers are especially dangerous because they can capture unencrypted data such as login credentials and private messages, helping attackers plan further attacks.

---
## How a Sniffer Works
In a local network (LAN), computers connect using **Ethernet**, which relies on two addresses: the **MAC address** and the **IP address**. The **MAC address** is unique to each device and built into its network card. Ethernet uses this MAC address to send data.

When a computer wants to communicate, it needs the MAC address of the destination. It checks its **ARP cache** (a table of known IP-to-MAC mappings). If the MAC isn’t found, it sends an **ARP broadcast** asking who owns the IP. The right machine replies with its MAC, and the sender stores it for future use. From then on, data is sent using that MAC address.

There are two basic types of Ethernet environments, and sniffers work differently in each. These two types are: 
- **Shared Ethernet** - In a **shared Ethernet**, all devices are connected to a single network line, so when one device sends data, all others receive it—but only the intended device accepts it. A sniffer bypasses this by capturing **all traffic**, making sniffing easy and **hard to detect**.
- **Switched Ethernet** - In a **switched Ethernet**, a switch sends data only to the intended device using a MAC address table, so sniffers can’t see other traffic by default. Many believe this makes switched networks safe, but **sniffing is still possible** using advanced techniques, even though it's harder than in shared networks.

Although a switch is more secure than a hub, sniffing the network is possible using the following methods: 
#### **ARP Spoofing**
In a typical network, systems use the Address Resolution Protocol (ARP) to map IP addresses to MAC (hardware) addresses. However, ARP is not secure — it accepts any reply, even if no request was sent. In ARP spoofing, an attacker sends a fake ARP reply to the target machine, making it believe that the attacker’s machine is the gateway. This way, the victim sends all its traffic to the attacker instead of the real gateway. Since the attacker is now in the middle, they can quietly sniff, record, or even modify the data passing through. This method is a key part of man-in-the-middle (MITM) attacks.
  
#### MAC Flooding
Switches use a table to keep track of which MAC addresses are connected to which ports. But this table has limited memory. Attackers exploit this by sending a large number of fake MAC addresses to the switch using tools like `macof`. Eventually, the switch’s memory overflows, and it stops functioning like a smart switch. Instead, it starts sending (or broadcasting) all traffic to all ports, just like a hub. Once this happens, an attacker connected to any port on the switch can see the entire network’s traffic — making it easy to sniff sensitive data.

Even after turning a switch into a hub, a normal network card (NIC) won't capture all packets — only those addressed to it. But attackers overcome this by enabling promiscuous mode on their NIC. In this mode, the NIC listens to all traffic, not just its own. Sniffer tools like Wireshark or tcpdump can then be used to capture and analyze all the packets flowing through the network segment. This helps attackers monitor, extract, and sometimes manipulate sensitive information like passwords, emails, or session cookies.

---
## Types of Sniffing
There are two types of sniffing. Each is used for different types of networks. The two types are:
- Passive sniffing
- Active sniffing

### Passive sniffing
**Passive Sniffing** is a technique where attackers silently capture network traffic without sending any data themselves. It works only in **hub-based networks** (common collision domains), where all devices can see each other’s traffic. Since hubs broadcast data to all connected systems, attackers can easily eavesdrop using tools like packet sniffers.

Attackers may use this method by **physically plugging into the network** or by installing a **Trojan** with sniffing capabilities on a victim’s machine.

While modern networks use **switches** that block passive sniffing, the technique remains effective in older setups and offers stealth, making it harder to detect than active sniffing.

### Active sniffing
**Active Sniffing** is a method attackers use to capture data on a switched network by injecting fake traffic, such as ARP packets. Unlike hub-based networks, switches only send data to the intended device, so passive sniffers can't see all traffic. To get around this, attackers actively send special traffic to trick the switch into sending data their way.

Switches use **CAM (Content Addressable Memory)** to track which devices are connected to which ports. By attacking this system, hackers can intercept private data being sent across the network. Active sniffing is hard to perform and easier to detect, but it can reveal sensitive information if successful.

---
## How an Attacker Hacks the Network Using Sniffers
Attackers use sniffing tools to sniff packets and monitor network traffic on a target network. The steps that an attacker follows to make use of sniffers to hack a network are illustrated below. 
- **Step 1:** An attacker who decides to hack a network first discovers the appropriate switch to access the network and connects a system or laptop to one of the ports on the switch.
- **Step 2:** An attacker who succeeds in connecting to the network tries to determine network information such as the topology of the network by using network discovery tools.
- **Step 3:** By analyzing the network topology, the attacker identifies the victim’s machine to target his/her attacks.
- **Step 4:** An attacker who identifies a target machine uses ARP spoofing techniques to send fake (spoofed) Address Resolution Protocol (ARP) messages.
- **Step 5:** The previous step helps the attacker to divert all the traffic from the victim’s computer to the attacker’s computer. This is a typical man-in-the-middle (MITM) type of attack.
- **Step 6:** Now, the attacker can see all the data packets sent and received by the victim. The attacker can now extract sensitive information from the packets, such as passwords, usernames, credit card details, and PINs.

---
## Protocols Vulnerable to Sniffing
The following protocols are vulnerable to sniffing. The main reason for sniffing these protocols is to acquire passwords.

- **Telnet & Rlogin** - These are remote login tools, but they send data (like usernames and passwords) without encryption. Attackers can easily capture keystrokes.
- **HTTP** - Websites using HTTP send data in plain text. This means login info and personal data can be sniffed by attackers during transmission.
- **SMTP (Simple Mail Transfer Protocol)** - Used for sending emails. In most cases, emails and credentials are sent unencrypted, making them easy for attackers to capture.
- **NNTP (Network News Transfer Protocol)** - Transfers news articles, but does not encrypt the content. Attackers can sniff sensitive data shared through it.
- **POP (Post Office Protocol)** - Used to receive emails. Like SMTP, POP does not encrypt data, making passwords and messages vulnerable to sniffing.
- **FTP (File Transfer Protocol)** - Used for transferring files. It lacks encryption, so usernames, passwords, and files can be captured by attackers.
- **IMAP (Internet Message Access Protocol)** - Used to read emails from a server. It has weak security, so attackers can easily access email content and login info.
- **TFTP (Trivial File Transfer Protocol)**: A lightweight file transfer protocol with **no authentication or encryption**. Anyone on the same network can access the files being transferred.

---
## Sniffing in the Data Link Layer of the OSI Model 
**Sniffing in the Data Link Layer** happens at Layer 2 of the OSI model, where data is turned into bits for transmission. **Sniffers** work at this layer to capture network packets as they move across devices. Since OSI layers work independently, higher layers (like the application or transport layer) don’t detect this activity, making sniffing at the data link layer stealthy and hard to notice.

![image](https://github.com/user-attachments/assets/e2e1db8f-d8f0-44c2-ad75-c91c4f9ff1bc)

---
## Hardware Protocol Analyzers
**Hardware Protocol Analyzers** are physical devices used to monitor and analyze network traffic without affecting it. They capture, decode, and inspect data packets to detect unusual or malicious activity. Unlike software tools, they handle large amounts of data without dropping packets, even during heavy traffic.

These analyzers support various networks like LAN, WAN, wireless, and telecom lines, and can detect low-level events such as transmission errors and signal changes. They also provide precise timestamps for every packet. While powerful and accurate, they are costly and usually not accessible to individual users or hobbyists.

**Hardware protocol analyzers from different manufacturers include the following:**

####  Xgig 1000 32/128 G FC & 25/50/100 GE Analyzer 
🔗Source: [https://www.viavisolutions.com]

The **VIAVI Xgig 1000** is a portable hardware tool used to analyze high-speed **Fiber Channel (FC)** and **Ethernet (GE)** networks. It supports speeds up to **128G FC** and **100G Ethernet**, and allows non-intrusive data capture, analysis, and even error injection (jamming) without disrupting the network. It uses a unique analog pass-through adapter to maintain signal quality and provides deep visibility into the physical layer with features like **auto negotiation**, **link training**, and **forward error correction (FEC)**.

![image](https://github.com/user-attachments/assets/9b741474-8a22-4b84-9395-e8aeb0521c98)

#### SierraNet M1288 
🔗Source: [https://www.teledynelecroy.com]

**SierraNet M1288** is a high-performance hardware tool used for testing and analyzing **Ethernet** and **Fiber Channel** networks. It captures and manipulates traffic to test how applications and links behave. It can record up to **256GB of traffic** at full speed and supports features like **128G/256G buffers**, **dynamic memory use**, and **Fiber Channel fabrics (64/128GFC PAM4)**. It also works with **1, 2, and 4 Ethernet lanes**, making it ideal for advanced network testing and troubleshooting.

![image](https://github.com/user-attachments/assets/6458705a-6bad-4f9d-93f3-68f0a622a951)

**Some examples of hardware protocol analyzers are listed below:**
- **PTW60** [https://www.globalspec.com]
- **P5551A PCIe 5.0 Protocol Exerciser** [https://www.keysight.com]
- **Voyager M4x** [https://www.teledynelecroy.com]
- **N2X N5540A Agilent Protocol Analyzer** [https://www.valuetronics.com]
- **Xgig 16-Lane PCI Express 4.0 Chassis** [https://www.viavisolutions.com]

---
## SPAN Port
**SPAN (Switched Port Analyzer)**, also known as **port mirroring**, is a Cisco switch feature used to monitor network traffic. It copies all the data from one or more **source ports** and sends it to a single **destination port**. This destination port is connected to a network analyzer, which helps in checking traffic, finding errors, or investigating suspicious activity. SPAN is useful for analyzing traffic from multiple ports or even entire VLANs, but it only sends the mirrored data to one destination port.

![image](https://github.com/user-attachments/assets/a8cc3b40-c115-45cc-861b-abb1097853a7)

---
## Wiretapping
**Wiretapping** is the secret monitoring of phone or internet conversations by an attacker. The attacker targets a person or device and connects a **listening tool**—either hardware, software, or both—to the communication line. By capturing a small part of the electrical signal, the attacker can **listen in**, **intercept**, and **record** the data being shared, all without the victim knowing.

### Types of Wiretapping
There are two types of wiretapping that an attacker can use to monitor, record, and even alter the data flow in the communication system.

#### Active Wiretapping
In hacking terminology, active wiretapping is an MITM attack. This allows an attacker to monitor and record the traffic or data flow in a communication system. The attacker can also alter or inject data into communication or traffic.

#### Passive Wiretapping
Passive wiretapping is snooping or eavesdropping. This allows an attacker to monitor and record traffic. By observing the recorded traffic flow, the attacker can snoop for a password or other information.

> Note: Wiretapping without a warrant or the consent of the people conducting the conversation is a criminal offense in most countries, and is punishable depending on the country’s law.

---
## Lawful Interception 
**Lawful Interception (LI)** is the legal process of monitoring private communications like calls, emails, and internet activity for security and investigation purposes. Carried out by law enforcement agencies (LEAs), it allows access to data through telecom or internet service providers when users are suspected of illegal activity.

A typical setup includes a **tap/access switch** that collects and sorts network traffic by IP domain. This data is then sent to tools like **E-Detective (ED)** systems, which decode and reconstruct it using protocols like **POP3, SMTP, FTP, and Telnet**. A **Centralized Management Server (CMS)** controls and manages all the ED systems. This helps authorities monitor suspicious communication legally and effectively.

![image](https://github.com/user-attachments/assets/7343fe43-2ea4-465a-aef6-bc939a9d4759)


# 🧰 Sniffing Tools
