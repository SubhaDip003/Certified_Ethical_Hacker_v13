# 📡 IoT Concepts and Attacks 
The Internet of Things (IoT) connects everyday physical devices through machine-to-machine communication and big data, bridging the gap between the digital and physical world. While it brings innovation, it also creates new security risks. Attackers target IoT devices and networks using techniques like DDoS attacks, HVAC system exploits, rolling code attacks, BlueBorne Bluetooth attacks, and signal jamming. Understanding these threats is key to securing IoT environments.

---
## What is the IoT? 
The Internet of Things (IoT) refers to everyday devices connected to the internet that can sense, collect, and share data using built-in sensors, processors, and communication hardware. These “things” can include home appliances, industrial machines, vehicles, and wearables. IoT enables automation, smarter decision-making, and deeper integration across systems, improving efficiency and user experience. Its key features include connectivity, sensors, artificial intelligence, and real-time interaction.

---
## How the IoT Works 
IoT technology includes four primary systems: IoT devices, gateway systems, data storage systems using cloud technology, and remote control using mobile apps. These systems together make communication between two endpoints possible. <br>
Discussed below are some of the important components of IoT technology that play an essential role in the function of an IoT device: 
1. **Sensing Technology** → Sensors inside IoT devices collect data from the environment, like temperature, gas levels, machine performance, or even a patient’s health.
2. **IoT Gateways** → Gateways act as a bridge, connecting IoT devices with users or the cloud, so the collected data can be securely transmitted and accessed.
3. **Cloud Server/Data Storage** → Data from sensors is stored in the cloud, where it is analyzed and processed. The results are then shared with the user for decision-making or action.
4. **Remote Control using Mobile App** → Users can monitor, control, and manage IoT devices from anywhere using apps on their smartphones, tablets, or laptops.

Example: 
1. A smart security system installed in a home will be integrated with a gateway, which in turn helps to connect the device to the Internet and the cloud infrastructure.
2. Data stored in a cloud includes information about every device connected to the network. This information includes the device’s ID and the present status of the device, as well as information regarding who has accessed the device and how many times. It also includes information such as how long the device was accessed for previously.
3. The connection with the cloud server is established through web services.
4. The user on the other side, who has the required app to access the device remotely on his/her mobile phone, interacts with it, which in turn allows him/her to interact with the device at home. Before accessing the device, he/she is asked to authenticate him/herself. If the credentials submitted by him/her match those saved in the cloud, he/she is granted access. Otherwise, his/her access is denied, ensuring security. The cloud server identifies the device’s ID and sends a request associated with that device using gateways.
5. The security system that is currently recording the footage at home, if it senses any unusual activity, then sends an alert to the cloud through the gateway, which matches the device’s ID and the user associated with it, and finally, the end-user receives an alert.

<p align="center">
  <img width="666" height="232" alt="image" src="https://github.com/user-attachments/assets/73389d0f-00a3-4c9b-b92f-26f5d7c55236" />
</p>

---
## IoT Architecture
The IoT architecture includes several layers, from the Application layer at the top to the Edge Technology layer at the bottom. These layers are designed in such a way that they can meet the requirements of various sectors, including societies, industry, enterprises, governments, etc. <br>
The functions performed by each layer in the architecture are given below: 
1. **Edge Technology Layer** → This is the foundation of IoT. It includes sensors, RFID tags, readers, and devices that collect real-world data (like temperature, motion, or location) and send it into the network.
2. **Access Gateway Layer** → Works as a bridge between devices and clients. It handles the first step of processing like routing messages, identifying data, and managing subscriptions.
3. **Internet Layer** → The communication backbone of IoT. It allows devices to connect with each other, with the cloud, gateways, or back-end systems to share and transfer data.
4. **Middleware Layer** → Acts as the middle manager between hardware and applications. It handles tasks like data storage, filtering, analysis, device management, and access control, ensuring smooth communication and security.
5. **Application Layer** → The top layer where users interact with IoT services. It delivers solutions for different fields like healthcare, smart homes, automobiles, industries, and security systems.

---
## IoT Application Areas and Devices 
IoT devices are widely used across many sectors to make daily life and work more efficient. They power smart homes and buildings, enable healthcare monitoring, improve industrial automation, support modern transportation, enhance security systems, and are integrated into retail services. By connecting devices and sharing data, IoT helps simplify tasks and improve overall quality of life. <br>
Some of the applications of IoT devices are as follows: 
1. **Smart Home Devices** → IoT powers devices like thermostats, smart lights, and security systems that connect to the internet, making homes more automated, energy-efficient, and secure.
2. **Healthcare & Life Sciences** → Wearables, pacemakers, ECG/EKG machines, and telemedicine tools use IoT to monitor health in real time, assist doctors, and improve patient care.
3. **Industrial IoT (IIoT)** → Factories use IoT to increase production, apply smart manufacturing methods, and create new business models, boosting efficiency and revenue.
4. **Transportation** → IoT enables communication between vehicles, roadside systems, and pedestrians. This improves traffic flow, navigation, road safety, and parking management.
5. **Retail** → IoT helps with smart payments, digital ads, and product tracking. It prevents theft and losses while improving customer experience and sales.
6. **IT & Networks** → Office devices like printers, fax machines, and PBX systems use IoT for better connectivity, smoother communication, and easy data sharing across distances.

🔗Source: [https://www.beechamresearch.com] <br>

<p align="center">
  <img width="642" height="411" alt="image" src="https://github.com/user-attachments/assets/e84213fa-45ee-4a80-ab36-c671d4f11773" />
  <img width="641" height="484" alt="image" src="https://github.com/user-attachments/assets/d4d7c9ec-43b8-4e21-8105-a133356e0246" />
  <img width="643" height="295" alt="image" src="https://github.com/user-attachments/assets/d842895a-c94e-48cf-b278-6a51ed92bbde" />
</p>

---
## IoT Technologies and Protocols 
IoT relies on a variety of emerging technologies and protocols to enable devices to communicate with each other. Since many IoT solutions are still immature and vendor support is inconsistent, security and reliability become major challenges. To ensure proper communication between endpoints, IoT mainly depends on standard networking protocols, which form the backbone for data exchange and device connectivity.

The major communication technologies and protocols with respect to the range between a source and the destination are as follows:

### Short-Range Wireless Communication 
- **Bluetooth Low Energy (BLE):** BLE or Bluetooth Smart is a wireless personal area network. This technology is designed to be applied in various sectors such as healthcare, security, entertainment, and fitness.
- **Light-Fidelity (Li-Fi):** Li-Fi is like Wi-Fi with only two differences: the mode of communication and the speed. Li-Fi is a Visible Light Communications (VLC) system that uses common household light bulbs for data transfer at a very high speed of 224 Gbps.
- **Near-Field Communication (NFC):** NFC is a type of short-range communication that uses magnetic field induction to enable communication between two electronic devices. It is primarily used in contactless mobile payment, social networking, and the identification of documents or other products.
- **QR Codes and Barcodes:** These codes are machine-readable tags that contain information about the product or item to which they are attached. A quick response code, or QR code, is a two-dimensional code that stores product information and can be scanned using smartphones, whereas a barcode comes in both one-dimensional (1D) and two-dimensional (2D) forms of code.
- **Radio-Frequency Identification (RFID):** RFID stores data in tags that are read using electromagnetic fields. RFID is used in many sectors including industrial, offices, companies, automobiles, pharmaceuticals, livestock, and pets.
- **Thread:** A thread is an IPv6-based networking protocol for IoT devices. Its main purpose is home automation so that the devices can communicate with each other on local wireless networks.
- **Wi-Fi:** Wi-Fi is a technology that is widely used in wireless local area networking (LAN). At present, the most common Wi-Fi standard that is used in homes or companies is 802.11n, which offers a maximum speed of 600 Mbps and a range of approximately 50 m.
- **Wi-Fi Direct:** This is used for peer-to-peer communication without the need for a wireless access point. Wi-Fi direct devices start communication only after deciding which device will act as an access point.
- **Z-Wave:** Z-Wave is a low-power, short-range communication designed primarily for home automation. It provides a simple and reliable way to wirelessly monitor and control household devices like HVAC, thermostats, garages, home cinemas, etc.
- **Zig-Bee:** This is another short-range communication protocol based on the IEEE 203.15.4 standard. Zig-Bee is used in devices that transfer data infrequently at a low rate in a restricted area and within a range of 10–100 m.
- **ANT:** Adaptive Network Topology (ANT) is a multicast wireless sensor network technology mainly used for short-range communication between devices related to sports and fitness sensors.

### Medium-Range Wireless Communication
- **HaLow:** This is another variant of the Wi-Fi standard; it provides an extended range, making it useful for communications in rural areas. It offers low data rates, thus reducing the power and cost of transmission.
- **LTE-Advanced:** LTE-Advanced is a standard for mobile communication that provides enhancement to LTE, focusing on providing higher capacity in terms of data rate, extended range, efficiency, and performance.
- **6LoWPAN:** IPv6 over Low-Power Wireless Personal Area Networks (6LoWPAN) is an Internet protocol used for communication between smaller and low-power devices with limited processing capacity, such as various IoT devices.
- **QUIC:** Quick UDP Internet Connections (QUICs) are multiplexed connections between IoT devices over the User Datagram Protocol (UDP); they provide security equivalent to SSL/TLS.

### Long-Range Wireless Communication
- **LPWAN:** Low Power Wide Area Networking (LPWAN) is a wireless telecommunication network, designed to provide long-range communications between two endpoints. Available LPWAN protocols and technologies include the following:
  - **LoRaWAN:** A Long Range Wide Area Network (LoRaWAN) is used to support applications such as mobile, industrial machine-to-machine, and secure two-way communications for IoT devices, smart cities, and healthcare applications.
  - **Sigfox:** This is used in devices that have short battery life and need to transfer a limited amount of data.
  - **Neul:** This is used in a tiny part of the TV white space spectrum to deliver high-quality, high-power, high-coverage, and low-cost networks.
- **Very Small Aperture Terminal (VSAT):** VSAT is a communication protocol that is used for data transfer using small dish antennas for both broadband and narrowband data.
- **Cellular:** Cellular is a type of communication protocol that is used for communication over a longer distance. It is used to send high-quality data but with the drawbacks of being expensive and having high power consumption.
- **MQTT:** Message Queuing Telemetry Transport (MQTT) is an ISO standard lightweight protocol used to transmit messages for long-range wireless communication. It helps in establishing connections to remote locations, for example via satellite links.
- **NB-IoT:** Narrowband IoT (NB-IoT) is a variant of LoRaWAN and Sigfox that uses more enhanced physical layer technology and the spectrum used for machine-to-machine communication.

### Wired Communication
- **Ethernet:** Ethernet is the most commonly used type of network protocol today. It is a type of LAN (Local Area Network) that consists of a wired connection between computers in a small building, office, or campus.
- **Multimedia over Coax Alliance (MoCA):** MoCA is a type of network protocol that provides high-definition videos and related content to homes over existing coaxial cables.
- **Power-Line Communication (PLC):** This is a type of protocol that uses electrical wires to transmit power and data from one endpoint to another. PLC is required for applications in different areas such as home automation, industrial devices, and broadband over power lines (BPL)

### IoT Operating Systems 
IoT operating systems are lightweight platforms designed to run on IoT devices like gateways and sensor nodes. Unlike older devices that worked without an OS, modern IoT devices use these specialized systems to enable connectivity, usability, and smooth communication between devices. They provide the foundation for interoperability and secure operation in increasingly complex IoT environments.

Given below are some of the operating systems used by IoT devices:
- **Windows 10 IoT:** This is a family of operating systems developed by Microsoft for embedded systems.
- **Amazon FreeRTOS:** This is a free open-source OS used in IoT microcontrollers that makes low-power, battery-operated edge devices easy to deploy, secure, connect, and manage.
- **Fuchsia:** This is an open-source OS developed by Google for various platforms, such as embedded systems, smartphones, tablets, etc.
- **RIOT:** This has fewer resource requirements and uses energy efficiently. It has the ability to run on embedded systems, actuator boards, sensors, etc.
- **Ubuntu Core:** Also known as Snappy, this is used in robots, drones, edge gateways, etc.
- **ARM Mbed OS:** This is mostly used for low-powered devices such as wearable devices.
- **Zephyr:** This is used in low-power and resource-constrained devices.
- **Embedded Linux:** This is used with all small, medium, and large embedded systems.
- **NuttX RTOS:** This is an open-source OS primarily developed to support 8-bit and 32-bit microcontrollers of embedded systems.
- **Integrity RTOS:** Primarily used in the aerospace or defense, industrial, automotive, and medical sectors.
- **Apache Mynewt:** This supports devices that work on the BLE protocol.
- **Tizen:** Tizen is an open-source, Linux-based operating system designed for a wide range of devices, including smartphones, tablets, smart TVs, wearables, and IoT devices.

### IoT Application Protocols 
1. **CoAP (Constrained Application Protocol)** → A lightweight web protocol that allows IoT devices with limited resources to exchange data. Commonly used in smart energy systems and building automation.
2. **Edge Computing** → Moves data processing closer to IoT devices (at the network edge) instead of relying only on the cloud. This makes data transfer faster and improves caching, storage, and real-time services.
3. **LWM2M (Lightweight Machine-to-Machine)** → A protocol that helps manage IoT devices at the application level, enabling communication, configuration, and monitoring of devices.
4. **Physical Web** → A technology that lets nearby IoT devices broadcast URLs using Bluetooth beacons, allowing quick and seamless interaction with those devices.
5. **XMPP (eXtensible Messaging and Presence Protocol)** → An open protocol used for real-time messaging and communication between IoT devices. It helps build interoperable IoT applications and services.
6. **Mihini/M3DA** → A software framework that enables data and command exchange between IoT gateways and M2M servers, allowing smooth communication in IoT applications.

---
## IoT Communication Models
IoT technology uses various technical communication models, each with its own characteristics. These models highlight the flexibility with which IoT devices can communicate with each other or with the client. Discussed below are four communication models and the key characteristics associated with each model: 

### Device-to-Device Communication Model
The device-to-device communication model allows connected devices to exchange data directly using protocols like ZigBee, Z-Wave, or Bluetooth. It is widely used in smart home systems such as lights, locks, cameras, and appliances, where devices share small amounts of data at low speeds. This model is also common in wearables—for example, an ECG device can pair with a smartphone to send health alerts during emergencies.

<p align="center">
  <img width="650" height="189" alt="image" src="https://github.com/user-attachments/assets/00635094-242f-4514-9f36-8d38e745f840" />
</p>

### Device-to-Cloud Communication Model
In the device-to-cloud communication model, devices send data directly to a cloud service rather than connecting straight to a client. It typically uses Wi-Fi, Ethernet, or cellular links to push telemetry, video, or commands to the cloud, and clients access the device by authenticating to that cloud. For example, a home CCTV streams to a cloud server; when you log in with the correct credentials, the cloud grants you access to view the camera. This model centralizes access and control but also makes secure cloud authentication and data protection critical.

<p align="center">
  <img width="560" height="185" alt="image" src="https://github.com/user-attachments/assets/74e25288-5e5f-4b8c-8db7-918dd8630af0" />
</p>

### Device-to-Gateway Communication Model
In the device-to-gateway model, an IoT device talks to an intermediate gateway (like a hub or a smartphone), and that gateway forwards data to the cloud. The gateway handles protocol and data translation, can provide security functions (encryption, access control), and reduces direct exposure of resource-constrained devices. Common local protocols include ZigBee and Z-Wave, while the gateway often uses standard IP-based links to reach the cloud. This setup lets simple devices (for example, a smart TV) connect securely to cloud services via a phone or hub.

<p align="center">
  <img width="549" height="221" alt="image" src="https://github.com/user-attachments/assets/78d45324-f872-4867-84fb-32373b799f39" />
</p>

### Back-End Data-Sharing Communication Model
The back-end data-sharing communication model allows IoT devices to send their data to the cloud, where it can be accessed and analyzed by authorized third parties. For example, a company’s energy usage data can be collected and shared with an external analyzer to study monthly or yearly consumption. The insights from this analysis help the company lower costs by adopting energy-saving or harvesting techniques.

<p align="center">
  <img width="557" height="208" alt="image" src="https://github.com/user-attachments/assets/8f2107c4-3a0a-475f-97aa-b66f7237e9f3" />
</p>

---
## Challenges of IoT 
IoT devices are widely used but often lack strong security measures, making them easy targets for hackers. Frequent updates and new features can introduce more vulnerabilities, increasing the risk of exploitation. To address this, manufacturers must prioritize security from the design stage through deployment and ongoing maintenance, ensuring IoT devices remain protected throughout their lifecycle.

Discussed below are some of the challenges facing IoT devices that make them vulnerable to threats: 
1. **Lack of Security and Privacy** → Many IoT devices store sensitive data but often lack even basic security, making them easy targets for hackers.
2. **Vulnerable Web Interfaces** → Built-in web servers in IoT devices can have flaws that attackers exploit to gain control.
3. **Legal, Regulatory, and Rights Issues** → Laws and policies for IoT security are not well-defined, leaving many risks unaddressed.
4. **Default, Weak, and Hardcoded Credentials** → Devices often come with simple or pre-set passwords that hackers can easily guess or crack.
5. **Clear Text Protocols and Open Ports** → Some devices send data without encryption and keep unnecessary ports open, exposing them to attacks.
6. **Coding Errors (Buffer Overflow)** → Poor coding in IoT software can cause vulnerabilities like buffer overflows or SQL injection.
7. **Storage Issues** → Devices have limited storage capacity, but they collect large amounts of data, creating security and management challenges.
8. **Difficult-to-Update Firmware and OS** → Updating software is critical for security, but many devices lack easy update options, leaving them exposed.
9. **Interoperability Standard Issues** → Different IoT devices often can’t work smoothly together, making it hard to secure and manage them.
10. **Physical Theft and Tampering** → Attackers can steal or tamper with devices to install malicious code or alter their hardware.
11. **Lack of Vendor Support** → Some vendors avoid providing firmware updates or third-party fixes, leaving devices vulnerable.
12. **Emerging Economy and Development Issues** → Policymakers face difficulties creating new regulations for the fast growth of IoT.
13. **Handling of Unstructured Data** → Huge amounts of random, unorganized data from devices make it hard to decide what is useful.
14. **Scalability** → As IoT networks grow, managing and analyzing massive amounts of data becomes harder.
15. **Power Consumption** → Many IoT devices run on batteries, making energy efficiency a constant challenge.
16. **Regulatory Compliance** → IoT systems must meet different regional and industry laws about privacy and security.
17. **Integration with Legacy Systems** → Connecting IoT with old infrastructure is difficult and often creates compatibility and security gaps.

---
## Threat vs Opportunity 
IoT can either be a major threat or a great opportunity depending on how it is managed. If misconfigured, it exposes sensitive data and creates risks to security, privacy, and safety. But if properly secured, IoT can improve communication, service delivery, efficiency, and overall quality of life. Since IoT devices handle highly sensitive information like health or financial records, securing them against threats is critical to ensure safe usage, prevent cyberattacks, and unlock their full potential.

---
## IoT Security Problems 
Potential vulnerabilities in the IoT system can result in major problems for organizations. Most IoT devices come with security issues such as the absence of a proper authentication mechanism or the use of default credentials, absence of a lock-out mechanism, absence of a strong encryption scheme, absence of proper key management systems, and improper physical security. <br>
Some of the security issues at each layer of IoT architecture are given below:

<p align="center">
  <img width="645" height="306" alt="image" src="https://github.com/user-attachments/assets/4891b6b9-7d11-4246-af7a-be4dbeaf78af" />
</p>

---
## OWASP Top 10 IoT Threats 
🔗Source: [https://owasp.org] <br>
The Top 10 IoT threats, according to the Open Web Application Security Project (OWASP), are listed below: 
1. **Weak, Guessable, or Hardcoded Passwords** → Using simple, common, or built-in default passwords makes it easy for attackers to brute-force or exploit backdoors to gain unauthorized access.
2. **Insecure Network Services** → Devices running unsafe services (like open ports or weak protocols) can be exploited with attacks such as buffer overflows, leading to denial-of-service or remote access.
3. **Insecure Ecosystem Interfaces** → Weak security in web apps, APIs, mobile apps, or cloud services (like poor authentication, weak encryption, or no input validation) can expose the entire IoT system to attacks.
4. **Lack of Secure Update Mechanisms** → If firmware updates are not properly validated, delivered securely, or protected against rollback, attackers can inject malicious code or exploit outdated software.
5. **Use of Insecure or Outdated Components** → Using old or vulnerable software, libraries, or third-party components can compromise the device, especially if they come from untrusted sources.
6. **Insufficient Privacy Protection** → Poor handling of personal data stored on devices can lead to exposure or theft of sensitive user information.
7. **Insecure Data Transfer and Storage** → Without strong encryption or access controls, sensitive data in transit (network traffic) or at rest (stored data) can be stolen or altered by attackers.
8. **Lack of Device Management** → Missing security features like monitoring, updates, or secure removal of devices leaves them vulnerable to exploitation once deployed.
9. **Insecure Default Settings** → Devices often ship with weak factory settings (like open ports or default credentials), and if operators can’t change them, attackers can easily exploit them.
10. **Lack of Physical Hardening** → Without proper physical protection, attackers can directly tamper with the device, extract sensitive data, or gain control to launch further attacks.

---
## OWASP IoT Attack Surface Areas 
🔗Source: [https://owasp.org] <br>
The OWASP IoT attack surface areas are given below: 

<p align="center">
  <img width="624" height="333" alt="image" src="https://github.com/user-attachments/assets/76acc77b-ca84-481f-9bf2-64c5f36090a0" />
  <img width="624" height="459" alt="image" src="https://github.com/user-attachments/assets/4f5767fe-fe8b-4940-a143-288a01b540da" />
  <img width="622" height="315" alt="image" src="https://github.com/user-attachments/assets/93f4338e-7700-46e8-a4fd-c65db868447c" />
  <img width="621" height="490" alt="image" src="https://github.com/user-attachments/assets/e976d194-ab21-44c7-b10b-de9089d58f81" />
  <img width="629" height="409" alt="image" src="https://github.com/user-attachments/assets/f5574647-c4b5-4db5-970c-7085538f7185" />
  <img width="622" height="496" alt="image" src="https://github.com/user-attachments/assets/34806e0f-e531-472a-9588-ed0431649d57" />
  <img width="628" height="420" alt="image" src="https://github.com/user-attachments/assets/db7aa37f-b043-42b3-a6a8-0247849b5847" />
  <img width="625" height="462" alt="image" src="https://github.com/user-attachments/assets/effaffc4-f93c-40c1-b673-0475fdf5d4d7" />
</p>

---
## IoT Vulnerabilities 
🔗Source: [https://owasp.org] <br>
The OWASP IoT vulnerabilities are given below: 

<p align="center">
  <img width="621" height="539" alt="image" src="https://github.com/user-attachments/assets/7446d84d-af07-4ee1-8586-ce47f6f96600" />
  <img width="618" height="209" alt="image" src="https://github.com/user-attachments/assets/b6bd87bd-463b-4705-af77-87f55d52fd5e" />
  <img width="621" height="440" alt="image" src="https://github.com/user-attachments/assets/ea5a648d-f50b-44a4-9b6b-c1d62d135cc1" />
  <img width="620" height="390" alt="image" src="https://github.com/user-attachments/assets/18a619db-95e4-4208-8e68-a76cab1547a9" />
</p>

---
## IoT Threats
IoT devices have very few security protection mechanisms against various emerging threats. These devices can be infected by malware or malicious code at an alarming rate. Attackers often exploit these poorly protected devices on the Internet to cause physical damage to the network, to wiretap the communication, and also to launch disruptive attacks such as DDoS.
Listed below are some types of IoT attack: 

1. **DDoS Attack** → Attackers turn many IoT devices into a botnet and flood a target with traffic, making its service unavailable.
2. **Attack on HVAC Systems** → Exploiting HVAC vulnerabilities to steal credentials or use the system as a foothold to attack the wider network.
3. **Rolling Code Attack** → Jam and sniff a vehicle’s remote signal to capture or predict the one-time code, then replay it to unlock/steal the vehicle.
4. **BlueBorne Attack** → Attackers connect to nearby Bluetooth-enabled devices and exploit Bluetooth protocol flaws to take control or steal data.
5. **Jamming Attack** → The attacker overwhelms or blocks wireless signals so sender and receiver can’t communicate.
6. **Remote Access using Backdoor** → Vulnerable IoT devices are compromised and turned into secret entry points for attackers into the network.
7. **Remote Access using Telnet** → An open Telnet port is abused to read device info or gain shell access and control devices.
8. **Sybil Attack** → One attacker creates many fake identities on the network to confuse routing or voting systems and disrupt communication.
9. **Exploit Kits** → Automated scripts or pages target unpatched IoT flaws to install malware or take control quickly.
10. **Man-in-the-Middle Attack** → The attacker intercepts and possibly alters communications between two devices while pretending to be each party.
11. **Replay Attack** → Recorded legitimate messages are resent repeatedly to confuse, crash, or gain unauthorized actions from a device.
12. **Forged Malicious Device** → An attacker with physical access swaps a real IoT device for a malicious clone to spy or inject attacks.
13. **Side-Channel Attack** → Secrets (like keys) are inferred by observing emissions—power, timing, or radio—rather than breaking the code directly.
14. **Ransomware Attack** → Malware encrypts device data or locks the screen, demanding payment to restore access.
15. **Client Impersonation** → A malicious device pretends to be a legitimate client or server to gain data or perform unauthorized actions.
16. **SQL Injection Attack** → Flaws in web/mobile control apps let attackers run harmful database commands to access or control devices.
17. **SDR-Based Attack** → Using software-defined radio to listen to or inject wireless signals, enabling snooping or spoofing on IoT links.
18. **Fault Injection Attack** → Intentionally causing errors (voltage, clock glitches, etc.) to force faulty behavior and extract secrets or bypass checks.
19. **Network Pivoting** → A compromised IoT device is used as a bridge to reach and attack otherwise protected systems on the network.
20. **DNS Rebinding Attack** → Malicious JavaScript in a webpage tricks the browser into talking to a local router or device, bypassing same-origin protections.
21. **Firmware Update (FOTA) Attack** → The attacker intercepts or tampers with a firmware update and installs malicious code on the device.

---
## Hacking IoT Devices: General Scenario 
The IoT includes different technologies such as embedded sensors, microprocessors, and power management devices. Security consideration changes from device to device and application to application. The greater the amount of confidential data we send across the network, the greater the risk of data theft, data manipulation, data tampering, and attacks on routers and servers. <br>
Improper security infrastructure might lead to the following unwanted scenarios:
- An eavesdropper intercepts communication between two endpoints and discovers the confidential information that is sent across. He/she can misuse that information for his/her own benefit.
- A fake server can be used to send unwanted commands to trigger unplanned events. For example, some physical resources (water, coal, oil, electricity) could be sent to an unknown and unplanned destination, etc.
- A fake device can inject a malicious script into the system to make it work as instructed by the device. This may cause the system to behave inappropriately and dangerously.

<p align="center">
  <img width="663" height="392" alt="image" src="https://github.com/user-attachments/assets/28713dad-19be-406b-af66-94ec5f08d105" />
</p>

---
## DDoS Attack
A distributed denial-of-service (DDoS) attack uses many compromised devices (a botnet) to flood a target server or service with traffic until it slows down or becomes unavailable. Attackers first infect devices with malware to build the botnet, then command those devices to send massive numbers of requests to the victim. Because the incoming traffic exceeds what the server can handle, legitimate users cannot access the service, causing outages, slow performance, or total shutdown. Continuous monitoring and traffic filtering help mitigate these attacks.

Given below are the steps followed by an attacker to perform a DDoS attack on IoT devices:
- Attacker gains remote access to vulnerable devices
- After gaining access, he/she injects malware into the IoT devices to turn them into botnets
- Attacker uses a command and control center to instruct botnets and to send multiple requests to the target server, resulting in a DDoS attack
- Target server goes offline and becomes unavailable to process any further requests 

<p align="center">
  <img width="634" height="434" alt="image" src="https://github.com/user-attachments/assets/f6df4b63-160f-48b3-8914-477a7b2d7b4c" />
</p>

---
## Exploit HVAC 
Many organizations use Internet-connected heating, ventilation, and air conditioning (HVAC) systems without implementing security mechanisms, Internet-connected HVAC systems are often deployed with weak or no security, creating an easy entry point for attackers. Using default or shared credentials, exposed remote-access features for vendors, or unpatched vulnerabilities, attackers can take control of HVAC devices, move laterally into corporate networks, and steal sensitive data or disrupt operations. Securing vendor access, changing default logins, and segmenting HVAC systems from critical networks help reduce this risk.

Steps followed by an attacker to exploit HVAC systems:
- Attacker uses Shodan ([https://www.shodan.io]) and searches for vulnerable industrial control systems (ICSs)
- Based on the vulnerable ICSs found, the attacker then searches for default user credentials using online tools such as [https://www.defpass.com]
- Attacker uses default user credentials to attempt to access the ICS
- After gaining access to the ICS, the attacker attempts to gain access to the HVAC system remotely through the ICS
- After gaining access to the HVAC system, an attacker can control the temperature from the HVAC or carry out other attacks on the local network

<p align="center">
  <img width="658" height="234" alt="image" src="https://github.com/user-attachments/assets/444dfab4-c1f2-4cf5-8881-01d81b2196a4" />
</p>

---
## Rolling Code Attack 
Most smart vehicles use smart locking systems, which include an RF signal transmitted in the form of code from a modern key fob to lock or unlock the vehicle. Here, the code sent to the vehicle is only used once and is different for every other use, which means if a vehicle receives the same code again, it rejects it. 

A rolling code attack targets keyless-entry systems that use one-time “rolling” or “hopping” codes to prevent replay. The attacker jams the key fob’s signal while simultaneously capturing the code the fob transmits; because the car never receives it, that code remains valid. Later the attacker replays the captured code to unlock the vehicle or garage. This defeats the replay protection and typically requires physical proximity plus a jamming/sniffing device.

For example, given below are the steps followed by an attacker to perform a rolling-code attack:
1. Victim presses car remote button and tries to unlock the car
2. Attacker uses a jammer that jams the car’s reception of the rolling code sent by the victim and simultaneously sniffs the first code
3. The car does not unlock; victim tries again by sending a second code
4. Attacker sniffs the second code
5. On the second attempt by the victim, the attacker forwards the first code, which unlocks the car
6. The recorded second code is used later by the attacker to unlock and steal the vehicle 

Attackers can make use of tools such as HackRF One and RFCrack to perform this attack.

<p align="center">
  <img width="639" height="453" alt="image" src="https://github.com/user-attachments/assets/a940f8b5-cbdb-4725-87d5-c81b5446ba34" />
</p>

---
## BlueBorne Attack
A BlueBorne attack exploits flaws in the Bluetooth protocol to take over nearby devices without user interaction or pairing. Because Bluetooth processes run with high privileges, attackers can connect to a device, identify its MAC and OS, and then use known protocol vulnerabilities to execute code, intercept traffic, or move laterally across a network. BlueBorne can affect many IoT and mobile devices (phones, TVs, watches, car systems, printers) and is dangerous because it works across multiple operating systems and requires only that Bluetooth be turned on.

Steps to perform BlueBorne attack:
1. Attacker discovers active Bluetooth-enabled devices around him/her; all Bluetooth-enabled devices can be located even if they are not in discoverable mod
2. After locating any nearby device, the attacker obtains the MAC address of the device
3. Now, the attacker sends continuous probes to the target device to determine the OS
4. After identifying the OS, the attacker exploits the vulnerabilities in the Bluetooth protocol to gain access to the target device
5. Now the attacker can perform remote code execution or a man-in-the-middle attack and take full control of the device

<p align="center">
  <img width="636" height="165" alt="image" src="https://github.com/user-attachments/assets/592e5e57-e125-4485-a038-f7f42b1155af" />
</p>

---
## Jamming Attack 
A jamming attack disrupts wireless communication by flooding the radio channel with noise or bogus signals at the same frequency the target devices use. Attackers use specialized transmitters to create this interference, causing devices to miss or delay transmissions and effectively denying service to legitimate users. Any wireless device or network can be affected, and the result is loss of connectivity and failure of IoT devices or services that rely on the radio link.

<p align="center">
  <img width="659" height="440" alt="image" src="https://github.com/user-attachments/assets/987c5946-5d9b-4a53-baac-ad291e908315" />
</p>

---
## Hacking Smart Grid/Industrial Devices: Remote Access using Backdoor 
Attackers use social engineering to collect employee emails and send phishing messages with a malicious attachment. When an employee opens it, a backdoor is installed, giving the attacker remote access to the company’s internal network. From there the attacker moves laterally to reach critical systems like the Supervisory Control and Data Acquisition (SCADA) network that controls substations. By installing malicious firmware or issuing crafted commands, the attacker can take control of industrial devices and disable power to targeted areas. Continuous user training, strong email filtering, network segmentation, and firmware integrity checks reduce this risk.

<p align="center">
  <img width="654" height="188" alt="image" src="https://github.com/user-attachments/assets/4798dedc-f60a-44c3-80a4-dccd72de70d1" />
</p>

---
## SDR-Based Attacks on IoT 
Software-defined radio (SDR) lets radio signals be created and processed in software instead of fixed hardware. Attackers using SDR can sniff IoT communications, inject spam or malicious commands, or alter signal transmission and reception to disrupt or take over devices. Because SDR works at the radio level, it can target both one-way (half-duplex) and two-way (full-duplex) links, enabling eavesdropping, spoofing, and denial-of-service against IoT systems. Continuous monitoring, strong authentication, and secure radio protocols help reduce these risks.

Types of SDR-based attacks performed by attackers to break into an IoT environment:

### Replay Attack 
This is the major attack described in IoT threats, in which attackers can capture the command sequence from connected devices and use it for later retransmission. An attacker can perform the below steps to launch a replay attack:
- Attacker targets the specified frequency that is required to share information between devices
- After obtaining the frequency, the attacker can capture the original data when the commands are initiated by the connected devices
- Once the original data is collected, the attacker uses free tools such as URH (Universal Radio Hacker) to segregate the command sequence
- Attacker then injects the segregated command sequence on the same frequency into the IoT network, which replays the commands or captured signals of the devices

### Cryptanalysis Attack
A cryptanalysis attack is another type of substantial attack on IoT devices. In this attack, the procedure used by the attacker is the same as in a replay attack except for one additional step, i.e., reverse-engineering the protocol to obtain the original signal. To accomplish this task, the attacker must be skilled in cryptography, communication theory, and modulation scheme (to remove noises from the signal). This attack is practically not as easy as a replay attack to launch, yet the attacker can try to breach security using various tools and procedures.

### Reconnaissance Attack
A reconnaissance attack supplements cryptanalysis by extracting device-specific information from public records and hardware. Many IoT devices must be certified for RF use, and their certification reports can reveal chip models and radio details. If designers try to hide identifiers, an attacker may probe the device with tools like a multimeter to locate pins or markings, identify the chipset, and match it to published reports. This process lets attackers learn hardware IDs, firmware versions, or known weaknesses that help plan later exploits.

---
## Identifying and Accessing Local IoT Devices 
An attacker gains access over local IoT devices when a user from the network visits a malicious page, i.e., created and distributed by an attacker in the form of an advertisement or any attractive means. Once the victim visits the harmful website, a malicious JavaScript code inside the page begins the process. <br>
Attackers generally implement two methods to take control of local IoT devices, as discussed below: 

### Discovering or Identifying the Local IoT Devices
The first attempt the attacker makes is to identify target devices, then obtain information about all the connected devices. <br>
To do this, the attacker follows the steps given below: 
1. Attacker obtains local IP Address (using the malicious code)
2. Attacker requests all the available devices in the network
3. Active devices respond with reset packet and request for inactive devices would return timeout
4. Attacker detects all available devices based on their responses 

<p align="center">
  <img width="437" height="181" alt="image" src="https://github.com/user-attachments/assets/f977e801-8d04-4c49-b9ba-d047ed4b5d22" />
</p>

### Accessing the Local IoT Devices using DNS Rebinding
DNS rebinding is a process of gaining access over the victim’s router using a malicious JavaScript code injected on a web page. After this, an attacker can assault any device activated using the default password. After identifying all the connected devices and their information in the network, the attacker exploits further to gain complete access to the local interconnected devices. <br>
Now that the attacker has the information on IoT devices in the network, he/she follows the steps given below:
1. Checks if the malicious code is performing DNS rebinding in all discovered devices, using DNS rebinding tools such as **Singularity of Origin**
2. Once the DNS rebinding is successfully implemented, the attacker can command and control the local IoT devices
3. The attacker can further extract private information, such as the UIDs and BSSIDs of local access points that are useful in finding the geo-location of the target devices

<p align="center">
  <img width="462" height="184" alt="image" src="https://github.com/user-attachments/assets/ef5e264a-5a68-4493-96eb-a8d67a63046f" />
</p>

After successfully launching this attack, the attacker could bypass the security and gain access to applications running on the local IoT devices. Further, the attacker can launch random audio or video files on different browsers of the devices.

---
## Fault Injection Attacks 












