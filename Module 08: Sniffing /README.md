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



# 🧰 Sniffing Tools
