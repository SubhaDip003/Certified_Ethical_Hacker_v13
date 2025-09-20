# 🏭 OT Concepts and Attacks
Operational technology (OT) plays a major role in today’s modern society, as it drives a collection of devices designed to work together as an integrated or homogeneous system. For example, OT in telecommunications is used to transfer information from the electrical grid through wheeling power. The same telecommunications are also used for financial transactions between electrical producers and consumers. OT is a combination of hardware and software that is used to monitor, run, and control industrial process assets. Before learning how to hack OT, it is important to understand its basic concepts. This section discusses various important concepts related to OT. <br>
With evolving security threats and security posture of organizations using OT, organizations need to attach the utmost importance to OT security and adopt appropriate strategies to address security issues due to OT/IT convergence. This section also discusses various OT threats and attacks such as hacking industrial networks, HMI attacks, side-channel attacks, hacking PLCs, hacking industrial machines via RF remote controllers, etc. 

---
## What is OT?
Operational Technology (OT) is the combination of hardware and software used to monitor and control industrial devices like pumps, sensors, valves, robots, and cameras. It is widely used in industries such as manufacturing, energy, healthcare, and transportation to ensure safe and efficient operations. OT includes systems like SCADA, PLCs, RTUs, and DCSs that manage and automate industrial processes. Since many OT systems rely on older hardware and software, they are more vulnerable to cyber-attacks due to limited updates and patching options.

<p align="center">
  <img width="597" height="273" alt="image" src="https://github.com/user-attachments/assets/4f447c25-c749-4ff3-be2e-b7e58d80a123" />
  <img width="277" height="274" alt="image" src="https://github.com/user-attachments/assets/6a57ef63-1723-4c73-a4cc-3102fd90954b" />
</p>

---
## Essential Terminology 
Discussed below are some of the most important and extensively used terms related to OT systems: 
- **Assets** <br>
  Different components of OT are generally referred to as assets. Most OT systems, such as ICSs, comprise physical assets such as sensors and actuators, servers, workstations, network devices, PLCs, etc. ICS systems also include logical assets that represent the workings and containment of physical assets, such as graphics representing process flow, program logic, database, firmware, or firewall rules.

- **Zones and Conduits** <br>
    Zones and conduits is a network segregation technique used to isolate networks and assets to impose and maintain strong access control mechanisms. 

- **Industrial Network and Business Network** <br>
  OT generally comprises a collection of automated control systems. These systems are networked to achieve a business objective. A network comprising these systems is known as an industrial network. An enterprise or business network comprises a network of systems that offer an information infrastructure to the business. Businesses often need to establish communications between business networks and industrial networks.

- **Industrial Protocols** <br>
  Most OT systems employ proprietary protocols (S7, CDA, SRTP, etc.) or non-proprietary protocols (Modbus, OPC, DNP3, CIP, etc.). These protocols are generally used for serial communication and can also be used for communication over standard Ethernet using Internet Protocol (IP) along with transport layer protocols TCP or UDP. As these protocols operate at the application layer, they are referred to as applications.

- **Network Perimeter/Electronic Security Perimeter** <br>
  The network perimeter is the outermost boundary of a network zone, i.e., a closed group of assets. It acts as a point of separation between the interior and exterior of a zone. Generally, cybersecurity controls are implemented at the network perimeter. An Electronic Security Perimeter refers to a boundary between secure and insecure zones.

- **Critical Infrastructure** <br>
  Critical infrastructure refers to a collection of physical or logical systems and assets, the failure or destruction of which will severely impact security, safety, the economy, or public health.

---
## Introduction to ICS
Industrial Control Systems (ICS) are a vital part of modern industries and critical infrastructure. They are used to control, monitor, and automate processes in sectors like power generation, water treatment, oil and gas, pharmaceuticals, manufacturing, and food production. An ICS is not a single system but a combination of different control systems, devices, networks, and software working together to achieve industrial objectives.

ICS includes several types of systems such as Supervisory Control and Data Acquisition (SCADA), Distributed Control Systems (DCS), Basic Process Control Systems (BPCS), Safety Instrumented Systems (SIS), Human-Machine Interfaces (HMI), Programmable Logic Controllers (PLC), Remote Terminal Units (RTU), and Intelligent Electronic Devices (IED). These components work with sensors, actuators, and controllers to manage processes like production, distribution, and safety monitoring.

The operation of ICS can be configured in three modes:

* **Open Loop:** The system output depends only on predefined settings without feedback adjustment.
* **Closed Loop:** The system adjusts its input based on the output to maintain the desired result.
* **Manual Loop:** The process is controlled directly by humans without automation.

Controllers in ICS ensure processes meet required specifications by maintaining stability and efficiency. These systems often involve multiple control loops and HMIs, enabling operators to supervise operations. In addition, remote management and diagnostic tools are integrated through industrial communication protocols, allowing real-time monitoring, maintenance, and troubleshooting, even across distributed sites.

ICS plays a critical role in industries where processes are interdependent across multiple locations. Communication protocols ensure that these systems remain synchronized and efficient. Due to their widespread use in critical infrastructure, ICS requires strong security measures, as any compromise can lead to operational disruption, safety risks, or economic loss.

<p align="center">
  <img width="487" height="417" alt="image" src="https://github.com/user-attachments/assets/5836372c-7772-433b-89b8-d59f3f27b71a" />
</p>

---
## Components of an ICS 
An ICS is a broad class of command and control networks and systems that are required to control and monitor every industrial process. Each type of ICS works and functions differently based on the functionality and complexity of the control action. <br>
ICSs can be classified into the following types of most commonly and widely used control systems:

<p align="center">
  <img width="359" height="333" alt="image" src="https://github.com/user-attachments/assets/033ac860-e756-41a8-8b1b-12feab7a332b" />
</p>

### Distributed Control System (DCS) 
A Distributed Control System (DCS) is an advanced control system used in industries like power plants, oil refineries, chemical plants, and water treatment facilities. It manages large and complex processes by connecting a central supervisory unit with multiple local controllers, I/O points, and field devices. DCS uses feedback and feedforward loops to maintain set conditions and ensure smooth operations. It provides redundancy at every level to avoid downtime in case of failures, offers scalability for both small and large setups, and continuously evolves with new technologies like wireless systems, remote monitoring, and embedded web servers.

<p align="center">
  <img width="600" height="282" alt="image" src="https://github.com/user-attachments/assets/3df0a9eb-1f8e-4dff-ae08-eb11f2c3ca7b" />
</p>

### Supervisory Control and Data Acquisition (SCADA)
SCADA (Supervisory Control and Data Acquisition) is a centralized system used to monitor and control industrial processes across large areas, such as oil and gas pipelines, power grids, water treatment, and transportation systems. It combines hardware and software to collect real-time data from field devices like PLCs, RTUs, and IEDs, which are then processed and displayed to operators for decision-making. SCADA enables automation, detects issues, and can respond automatically or alert operators. While designed with redundancy and fault tolerance, SCADA systems remain vulnerable to cyberattacks, making their protection critical for industrial security.

<p align="center">
  <img width="653" height="295" alt="image" src="https://github.com/user-attachments/assets/9a943fad-002a-43d9-b58b-21b4ff24ba81" />
</p>

### Programmable Logic Controller (PLC)
A Programmable Logic Controller (PLC) is a small, durable digital computer used in industrial automation. It is designed to handle harsh environments and provides easy programming, sequential control, timers, counters, and reliable operation. PLCs are widely used in industries like steel, energy, automobile, chemical, and cement. They continuously monitor input signals from sensors and control outputs for actuators, replacing older systems like relays and drum sequencers. This makes PLCs essential for efficient and automated industrial processes.

A PLC system consists of three modules:
1. **CPU Module:** <br>
  The CPU module in a PLC includes the processor and memory. The processor handles data processing and computations, while memory consists of RAM for user programs and ROM for the operating system, drivers, and applications. PLCs also use retentive memory to preserve programs and data during power loss, allowing operations to resume without reprogramming once power is restored.

2. **Power Supply Module:** <br>
  The power supply module in a PLC converts AC power into DC power to keep the system running. It typically provides 5V DC for the CPU and I/O circuits, while some PLCs also supply 24V DC to operate sensors and actuators. Without this module, the PLC and connected devices cannot function.

3. **I/O Modules:** <br>
  The input and output modules of the PLC system are used in connecting the sensors and actuators with the system for sensing and controlling real-time values such as pressure, temperature, and flow. <br>
  There are different types of I/O modules. Some of the most important are discussed below:
   - **Digital I/O Module:** Used for the connection of sensors and actuators that are digital in nature (only for switching ON and OFF). These modules work with multiple digital inputs and outputs and support both AC and DC voltages.
   - **Analog I/O Module:** Used for the connection of sensors and actuators that provide analog electric signals. This module includes an analog-to-digital converter for converting analog data into digital data. The CPU module processes this digital data.
   - **Communication I/O Module:** Used for exchanging information between a communication network and a CPU located at a remote distance.

The main purpose of a PLC is to make machinery and systems work automatically without human intervention. Therefore, a PLC is very important, as it is responsible for all the growth, manufacturing, production, etc.

<p align="center">
  <img width="475" height="244" alt="image" src="https://github.com/user-attachments/assets/a06ff59d-0df7-4c84-94ba-38acee005eb5" />
</p>

### Basic Process Control System (BPCS)
A Basic Process Control System (BPCS) is used in industries to control and monitor processes like temperature, pressure, flow, and batch operations. It takes input signals from equipment, processes them, and generates output signals to keep operations running as per design. BPCS acts as the first layer of protection against unsafe conditions and helps improve performance. While it is flexible and supports many industrial needs, it differs from safety systems because it lacks advanced diagnostics to detect system flaws.

Listed below are some of the important functions offered by BPCS:
- Offers trending and alarm/event logging facilities
- Provides an interface from which an operator can monitor and control a system using an operator console (HMI)
- Controls the processes that in turn optimize the plant operation to enhance the quality of the product
- Generates production data reports
- Manages the sequencing, timing, and coordination of various process steps running in batches, ensuring consistent quality and efficiency.
- Includes critical safety interlocks or features that prevent the operation of certain equipment under unsafe conditions, thereby protecting both the processes and personnel.
- Handles the storage and retrieval of recipes, which include formulas, process steps, and production parameters, facilitating easy replication of batch processes.
- Integrates with other business and engineering systems, providing a bridge between plant floor operations and business management functions

<p align="center">
  <img width="530" height="296" alt="image" src="https://github.com/user-attachments/assets/b98947ed-60fc-4404-94eb-29eed4f52867" />
</p>

### Safety Instrumented Systems (SIS) 
A Safety Instrumented System (SIS) is an automated control system used in industries to protect people, equipment, and processes during hazardous situations. It monitors critical operations and, if a process goes beyond safe limits, it shuts down the system or switches it to a safe state. SIS works as a key layer of protection when the Basic Process Control System (BPCS) fails. Common examples include fire and gas systems, safety shutdown systems, and interlock systems. By detecting risks early and taking automatic action, SIS helps prevent accidents and ensures safe operations. The events generated and actions performed by the SIS system are illustrated in the diagram:

<p align="center">
  <img width="471" height="395" alt="image" src="https://github.com/user-attachments/assets/5b925533-b640-4299-a340-6dbf10b22e66" />
</p>

A Safety Instrumented System (SIS) is an independent control system designed to maintain safe operations in industrial processes. Its role is to detect abnormal conditions and take corrective actions to prevent accidents or equipment damage. The system is built around three core components: sensors, logic solvers, and final control elements.

* **Sensors** continuously measure critical process parameters such as temperature, pressure, and flow to determine whether operations are within safe limits. These can include pneumatic devices, electrical switches, or advanced smart transmitters.

* **Logic solvers** analyze the data from sensors and decide the necessary actions. They execute pre-programmed instructions to handle both normal and emergency situations, ensuring the system shifts into a safe state when required.

* **Final control elements**, such as pneumatically operated valves controlled by solenoids, carry out the actions determined by the logic solver. They work as the last line of defense to stop dangerous processes or bring equipment back into safe operation.

Since no component is entirely free from failure, industries must regularly test SIS systems to confirm reliability. Alongside functional testing, cybersecurity assessments are essential to protect against digital threats that may disrupt or compromise SIS operations. Continuous monitoring and assessment help maintain the system at its original design standards, ensuring both safety and resilience against modern risks.

<p align="center">
  <img width="429" height="306" alt="image" src="https://github.com/user-attachments/assets/4d482470-6106-4b92-a82a-0c47f868f945" />
</p>

---
## IT/OT Convergence (IIOT) 
IT/OT convergence is the integration of IT systems that handle data and cybersecurity with OT systems that manage industrial operations and equipment. Instead of working separately, both teams collaborate to improve efficiency, security, and productivity. The goal is not to replace roles but to bridge communication and processes, ensuring smoother operations and stronger protection against cyber threats.

### Benefits of merging OT with IT 
IT/OT convergence can enable smart manufacturing known as industry 4.0, in which IoT applications are used in industrial operations. Using the IoT for industrial operations such as monitoring supply-chain, manufacturing, and management systems is referred to as the Industrial Internet of Things (IIoT). <br>
The following are some of the benefits of converging IT/OT: 
- **Enhancing Decision Making:** Decision making can be enhanced by integrating OT data into business intelligence solutions.
- **Enhancing Automation:** Business flow and industrial control operations can be optimized by OT/IT merging; together they can improve the automation.
- **Expedite Business Output:** IT/OT convergence can organize or streamline development projects to accelerate business output.
- **Minimizing Expenses:** Reduces the technological and organizational overheads
- **Mitigating Risks:** Merging these two fields can improve overall productivity, security, and reliability, as well as ensuring scalability.
- **Increased agility:** With integrated systems, organizations can be more responsive to changes in market conditions or operational demands. Agility can lead to a competitive advantage in rapidly changing industries.
- **Predictive maintenance:** IT systems can analyze data from OT devices to predict when equipment fails. This predictive maintenance reduces downtime and maintenance costs and helps the equipment last longer.
- **Better quality control:** Integrating IT systems with OT processes allows more rigorous monitoring and control of quality standards across production lines, leading to higher product quality and consistency.
- **Compliance and reporting:** IT/OT convergence simplifies compliance with regulatory requirements by providing tools for improved data collection, analysis, and reporting. This integration ensures that the data are accurate, traceable, and accessible for auditing.
- **Scalability:** Unified IT and OT systems are easier to scale up or down based on business needs, thus supporting growth and adaptation without the need for extensive infrastructure changes.

<p align="center">
  <img width="612" height="211" alt="image" src="https://github.com/user-attachments/assets/3055e5c2-b8af-4b23-92f6-d226da2fc6c4" />
</p>

---
## The Purdue Model
The Purdue model (PERA) is a layered reference architecture for industrial control systems that separates the network into zones to improve security and reliability. It divides systems into the manufacturing/OT zone and the enterprise/IT zone, with a demilitarized zone (DMZ) between them to restrict direct communication. This separation helps contain compromises, protect production systems from IT-side risks, and maintain uninterrupted industrial operations.

The three zones are further divided into several operational levels. Each zone, with associated levels, is described below:

<p align="center">
  <img width="630" height="195" alt="image" src="https://github.com/user-attachments/assets/979846b9-42c9-45f9-b574-b38938e619d0" />
</p>

### Enterprise Zone (IT Systems)
The enterprise security zone is an IT area where core business operations like supply-chain management and scheduling run on systems such as SAP and ERP. It also includes data centers, users, and cloud access points. This zone is structured into two levels to organize and secure critical business processes and resources.
- **Level 5 (Enterprise Network)** <br>
  This is a corporate level network where business operations such as B2B (business-to-business) and B2C (business-to-customer) services are performed. Internet connectivity and management can be handled at this level. The enterprise network systems also accumulate data from all the subsystems located at the individual plants to report the inventory and overall production status.

- **Level 4 (Business Logistics Systems)** <br>
  All the IT systems supporting the production process in the plant lie at this level. Managing schedules, planning, and other logistics of the manufacturing operations are performed here. Level 4 systems include application servers, file servers, database servers, supervising systems, email clients, etc.

### Manufacturing Zone (OT Systems)
All the devices, networks, control, and monitoring systems reside in this zone. The manufacturing zone consists of four levels. 
- **Level 3 (Operational Systems/Site Operations)** <br>
  Level 3 (Operational Systems/Site Operations) focuses on managing and controlling plant operations to ensure smooth production workflows and desired output. It includes functions like production scheduling, batch management, quality assurance, data historians, MES/MOMS, laboratories, and process optimization. At this level, data from lower levels is collected for analysis and reporting, while instructions from higher levels are implemented to improve overall plant performance.

- **Level 2 (Control Systems/Area Supervisory Controls)** <br>
  Supervising, monitoring, and controlling the physical process is carried out at this level. The control systems can be DCSs, SCADA software, Human–Machine Interfaces (HMIs), real-time software, and other supervisory control systems such as engineering works and PLC line control.

- **Level 1 (Basic Controls/Intelligent Devices)** <br>
  Level 1, also called the Basic Controls or Intelligent Devices level, is where direct control of physical processes takes place. At this level, actions such as starting motors, opening valves, or moving actuators are executed. It involves devices like sensors, analyzers, IEDs, PLCs, RTUs, PID controllers, EUCs, and VFDs. Unlike Level 2, where PLCs perform supervisory tasks, in Level 1 they function mainly as control devices.

- **Level 0 (Physical Process)** <br>
  In this level, the actual physical process is defined, and the product is manufactured. Higher levels control and monitor operations at this level; therefore, this layer is also referred to as Equipment Under Control (EUC). Level 0 systems include devices, sensors (e.g., speed, temperature, pressure), actuators, or other industrial equipment used to carry out the manufacturing or industrial operations. A minor error in any of the devices at this level can affect overall operations.

### Industrial Demilitarized Zone (IDMZ)
An Industrial Demilitarized Zone (IDMZ) is a secure buffer network that separates operational technology (OT) systems in manufacturing from enterprise IT systems. It ensures safe communication between the two while containing errors or intrusions so production can continue without disruption. Typical IDMZ components include domain controllers, database replication servers, and proxy servers, all designed to protect both environments and maintain reliable operations.

---
## OT Technologies and Protocols 
OT technologies and protocols are the communication standards that enable real-time connectivity and data exchange between industrial systems within an ICS network. They are essential for operations in industries, as they manage how devices and control systems interact. For effective security, engineers must understand these protocols because they form the foundation of industrial network operations and can be exploited if not properly secured.

The key communication technologies and protocols of the OT network over the Purdue model defined by ISA-95 are as follows:

<p align="center">
  <img width="627" height="255" alt="image" src="https://github.com/user-attachments/assets/6e319029-cb83-4c11-bac5-75e62390332e" />
</p>

### Protocols used in Level 4 and 5 
1. **DCOM** → A Microsoft protocol that allows software components to communicate directly over a network in a secure and reliable way.
2. **FTP/SFTP** → FTP is used to transfer files between computers, while SFTP adds encryption and authentication to make file transfers secure.
3. **GE-SRTP** → A protocol from GE used in specific PLCs to transfer data and convert digital instructions into physical machine actions.
4. **IPv4/IPv6** → Protocols that handle how data packets move across networks. IPv4 is older, while IPv6 is the updated version that supports more devices and better efficiency.
5. **OPC UA** → A secure and platform-independent protocol that lets industrial devices and enterprise systems exchange data reliably.
6. **TCP/IP** → The main protocol suite of the internet, used for connecting and communicating between devices worldwide.
7. **SMTP, HTTP/HTTPS** → Common internet protocols. SMTP is used for sending emails, while HTTP/HTTPS handles safe web browsing and data exchange.
8. **Wi-Fi** → A wireless networking technology (like 802.11n) that connects devices to a local network and the internet at high speeds within a certain range.

### Protocols used in Level 3 
1. **CC-Link** → An open industrial network that lets devices from different manufacturers communicate, mainly used in machines, process control, and building automation.
2. **HSCP (Hybrid SCP)** → A high-speed protocol designed for transferring large files efficiently over long-distance and wideband networks.
3. **ICCP (IEC 60870-6)** → A protocol standard for SCADA and ICS systems, mainly used in power automation to enable communication between control centers.
4. **IEC 61850** → A protocol used in electrical substations that allows different Intelligent Electronic Devices (IEDs) to work and communicate together.
5. **IEC 60870-5-104** → A telecontrol protocol commonly used in utilities for electrical engineering and power system automation.
6. **ISA/IEC 62443** → A cybersecurity framework that provides guidelines to secure industrial automation and control systems from current and future threats.
7. **Modbus** → A simple serial communication protocol widely used with PLCs to connect and communicate with multiple devices on the same network.
8. **NTP (Network Time Protocol)** → Ensures all devices in a network are time-synchronized, which is important for logging, monitoring, and security.
9. **Profinet** → A protocol that allows real-time communication between controllers (like PLCs) and devices (like RFID readers) in industrial setups.
10. **SuiteLink** → A Windows-based industrial communication protocol using TCP/IP, valued for high-speed, quality, and reliable data transfer.
11. **Tase-2 (IEC 60870-6)** → An open protocol that supports fast and secure data exchange between control systems over WAN and LAN networks.
12. **ControlNet** → A real-time industrial protocol that reliably collects data from field devices and sends instructions, even in noisy environments.
13. **Profibus PA/DP** → A protocol used at the plant level: **DP** for controlling sensors/actuators via a central system, and **PA** for monitoring process equipment in automation systems.

### Protocols used in Level 2 
1. **6LoWPAN** → A lightweight version of IPv6 made for small, low-power devices. Commonly used in smart homes and building automation systems.
2. **DNP3** → A protocol that connects and controls devices in process automation systems, often used in utilities like electricity and water.
3. **DNS/DNSSEC** → DNS translates domain names into IP addresses, while DNSSEC adds security by verifying that DNS responses are authentic and not tampered with.
4. **FTE (Fault Tolerant Ethernet)** → Provides network redundancy by connecting each device twice to the same LAN, ensuring continuous communication even if one path fails.
5. **HART-IP** → Allows efficient communication between WirelessHART gateways and multiplexers to send and receive digital data in industrial networks.
6. **IEC 60870-5-101/104** → A standard communication protocol that enables control stations and substations to communicate reliably using TCP/IP networks.
7. **SOAP** → A strict messaging protocol using XML to securely transfer data between clients and servers over a network.
8. **DeviceNet** → Connects industrial devices like sensors and actuators to controllers (PLCs) using CAN (Controller Area Network) technology.
9. **AS-Interface (AS-i)** → A low-cost and simple network used to link basic automation devices like sensors and actuators for industrial processes.

### Protocols used in Level 0 and 1 
1. **BACnet** → A communication protocol for building automation systems, allowing devices like HVAC, lighting, and security systems to work together.
2. **EtherCAT** → A fast Ethernet-based protocol used in industrial automation for real-time control of machines and systems.
3. **CANopen** → A protocol built on the CAN bus, mainly used in vehicles and embedded systems to connect sensors, actuators, and controllers.
4. **Crimson** → A programming platform used in Red Lion products (like HMIs and controllers) to configure and manage automation devices.
5. **DeviceNet** → An industrial protocol based on CIP, used to connect and exchange data between controllers and industrial devices.
6. **Zigbee** → A low-power, short-range wireless protocol used for IoT and automation devices that send small amounts of data.
7. **ISA SP100 (ISA100)** → A wireless protocol standard for industrial automation, used in manufacturing and process industries.
8. **MELSEC-Q** → Mitsubishi’s protocol that connects multiple automation networks like CC-Link IE and Ethernet for high-speed communication.
9. **Niagara Fox** → A building automation protocol developed by Tridium, used for communication between Niagara software systems.
10. **Omron Fins** → A protocol used by Omron PLCs to share data with other PLCs and devices over Ethernet networks.
11. **PCWorx** → A software and protocol used in ICS controllers that support multiple industrial and TCP/IP communication standards.
12. **Profibus** → A complex industrial protocol designed for factory and process automation, ensuring devices from different vendors work together.
13. **Sercos II** → A real-time protocol used in industrial machines for precise motion control and high-performance automation.
14. **S7 Communication** → Siemens’ proprietary protocol for communication between Siemens PLCs (S7-300/400) and SCADA systems.
15. **WiMax** → A wireless protocol based on IEEE 802.16, used for long-range, high-speed metropolitan area networks.
16. **FOUNDATION Fieldbus** → A digital communication protocol commonly used in process industries to connect field devices (sensors, actuators) with control systems.

---
## Challenges of OT 
OT systems run critical infrastructure (power, water, healthcare) but often use old software and hardware, making them easy targets for attacks like phishing, spying, and ransomware that can disrupt services or cause real-world harm.
To reduce risks, regularly assess vulnerabilities, segment networks, apply patches/updates where possible, enforce strong access controls and monitoring, and keep reliable backups and incident plans.

Discussed below are some of the challenges and risks to OT that makes it vulnerable to many threats: 
1. **Lack of Visibility** → Many OT networks don’t have proper monitoring, making it hard to spot unusual activity or cyber threats quickly.
2. **Plain-Text Passwords** → Weak or unencrypted passwords are common, which makes it easy for attackers to steal credentials and break in.
3. **Network Complexity** → OT networks have many different devices with unique needs, making them harder to secure consistently.
4. **Legacy Technology** → Older OT systems often lack encryption, strong passwords, or modern security features, leaving them open to attacks.
5. **Lack of Antivirus Protection** → Many OT environments use outdated systems without antivirus, making them easy targets for malware.
6. **Lack of Skilled Professionals** → The shortage of cybersecurity experts makes it difficult to detect threats and secure OT systems properly.
7. **Rapid Pace of Change** → OT systems often struggle to keep up with fast technological changes, which creates security gaps.
8. **Outdated Systems** → Devices like PLCs use old firmware that cannot defend against modern cyberattacks.
9. **Haphazard Modernization** → Upgrading OT systems is slow and difficult due to legacy parts, leaving operations exposed for years.
10. **Insecure Connections** → OT systems sometimes use public or unencrypted Wi-Fi, which allows attackers to intercept and alter data.
11. **Rogue Devices** → Unknown or unauthorized devices in industrial networks create weak points for attacks.
12. **Convergence with IT** → As OT connects with IT networks, it becomes exposed to malware, insider threats, and IT security gaps.
13. **Organizational Challenges** → Different teams manage IT and OT security separately, causing gaps that attackers can exploit.
14. **Unique Networks/Proprietary Software** → Custom hardware and vendor-controlled software make updates and patches difficult, increasing risks.
15. **Vulnerable Communication Protocols** → Protocols like Modbus and Profinet lack built-in security, leaving devices open to exploitation.
16. **Remote Management Protocols** → Tools like RDP, VNC, and SSH can be hijacked by attackers to take control of OT systems.
17. **Insufficient Segmentation** → Weak network segmentation allows attackers to move freely once they gain access.
18. **Physical Security** → Remote or poorly protected sites can be physically tampered with, adding another layer of risk.
19. **Vendor Dependencies** → Reliance on third-party vendors may expose OT systems if vendors don’t follow strong cybersecurity practices.
20. **Resource Constraints** → Many OT devices lack the processing power for advanced security protections.
21. **Lack of Encryption** → Data between OT devices often travels unencrypted, making it easy to intercept or modify.
22. **Data Integrity Issues** → If attackers alter sensor readings or control data, it can lead to false decisions and dangerous outcomes.

---
## OT Vulnerabilities
OT systems (industrial controllers, sensors, machines) are increasingly linked with IT networks, and that connection lets attackers exploit IT weaknesses to reach OT. Because OT controls physical processes, a breach can cause safety incidents, outages, or damage—not just data loss. Reduce risk by segmenting OT from IT, enforcing strong access controls, patching promptly, and monitoring traffic closely.

Discussed below are some common OT vulnerabilities: 
| Vulnerability                                   | Description |
|-------------------------------------------------|-------------|
| **1. Publicly Accessible OT Systems**           | - OT systems are directly connected to the Internet so that third-party vendors can remotely perform maintenance and diagnostics <br> - OT systems are not protected using modern security controls <br> - Ability to perform password brute-forcing or probe OT systems to disable or disrupt their functions |
| **2. Insecure Remote Connections**              | - Corporate networks use jump boxes to establish remote connectivity with the OT network <br> - Ability to exploit vulnerabilities in jump boxes to gain remote access to the OT systems |
| **3. Missing Security Updates**                 | - Outdated software versions lead to increased risks and pave the way for attackers to compromise the OT systems |
| **4. Weak Passwords**                           | - Operators and administrators use default usernames and passwords for OT systems, which are easily guessable <br> - Ability to gain access to the OT systems, if the default vendor credentials of embedded devices and management interfaces are not changed |
| **5. Insecure Firewall Configuration**          | - Misconfigured access rules allow unnecessary access between corporate IT and OT networks <br> - Support teams allow excessive access permissions to the management interfaces on the firewalls <br> - Insecure firewalls propagate security threats to the OT network, which makes them vulnerable to attacks |
| **6. OT Systems Placed within the Corporate IT Network** | - Corporate systems are interconnected with the OT network for accessing operational data or exporting data to third-party management systems <br> - OT systems such as control stations and reporting servers are placed within the IT network <br> - Ability to use compromised IT system to gain access to the OT network |
| **7. Insufficient Security for Corporate IT Network from OT Systems** | - Attacks also originate from OT systems, as they use outdated legacy software and are accessed from remote locations <br> - Ability to gain unauthorized access to corporate IT systems through insecure OT devices |
| **8. Lack of Segmentation within OT Networks**  | - Several OT networks have a flat and unsegmented configuration, which assumes all systems have equal importance and functions <br> - Compromise of a single device may expose the entire OT network |
| **9. Lack of Encryption and Authentication for Wireless OT Networks** | - Wireless equipment in OT networks uses insecure and outdated security protocols <br> - Ability to perform sniffing and authentication bypass attacks |
| **10. Unrestricted Outbound Internet Access from OT Networks** | - OT networks allow direct outbound network connections to support patching and maintenance activities from a remote location <br> - Direct outbound Internet connectivity to insecure and unpatched OT devices increases the risk of malware attacks <br> - Susceptibility to malware and command-and-control attacks |

---
## MITRE ATT&CK for ICS 
🔗Source: [https://attack.mitre.org] <br>
MITRE ATT&CK for ICS can be used as a knowledge base by ICS security teams or vendors to understand an attacker’s actions against OT systems and to develop a defense system to prevent them. It also helps security teams illustrate and characterize the behavior of an attacker after any compromise. <br>
MITRE ATT&CK for ICS features different tactics, which are discussed below. 

### Initial Access 
It refers to the methods or techniques that an attacker can employ to establish initial access within the targeted ICS environment. An attacker can compromise different OT assets, websites, IT resources, and other external services to gain access to the ICS environment. Listed below are some of the techniques used by an attacker to gain initial access: 
- **Drive-by compromise:** An attacker can gain access to the OT system by exploiting the target user’s web browser by tricking them into visiting a compromised website during a normal browsing session.
- **Exploiting a public-facing software application:** An attacker exploits the known vulnerabilities of an Internet-facing application to gain access to an OT network. Such applications can be used for remote monitoring and management.
- **Exploiting remote services:** An attacker can manipulate known vulnerabilities of an application by leveraging error messages generated by the OS, program, or the kernel to perform further attacks on the remote services.

Listed below are some of the additional techniques used by attackers to gain initial access to an ICS environment:
- External remote services
- Internet-accessible devices
- Remote services
- Replication through removable media
- Rogue master
- Spear-phishing attachment
- Supply-chain compromise
- Transient cyber assets
- Wireless compromise

### Execution 
Execution refers to an attacker’s attempt to execute malicious code, manipulate data, or perform other system functions through illegitimate approaches. Attackers use different techniques to run malicious code within a device or asset in an ICT environment. Some of the techniques associated with this stage are as follows:
- **Changing the operating mode:** An attacker gains additional access to various OT functionalities by manipulating the operating modes of a controller within the infrastructure, e.g., program download.
- **Command-line interface (CLI):** An attacker uses the CLI to run various malicious commands and communicate with an OT system. It allows them to install and run different malicious programs and perform malicious operations without being detected.
- **Execution through APIs:** Attackers inject code into APIs to perform specific functions in a system after being called by the associated software.

Listed below are some of the additional techniques used by attackers at the execution stage:
- Graphical user interface (GUI)
- Hooking
- Modify controller tasking
- Native API
- Scripting
- User execution

###  Persistence
Attackers employ persistence procedures to retain access within the ICS environment, even if the compromised device is restarted or the communication is interrupted. The following are some of the techniques that can be used by an attacker at this stage.
- **Modifying a program:** An attacker abuses a controller in an OT system by changing or attaching a program to it. It allows changing the behavior of how the controller communicates with other devices or processes within that environment.
- **Module firmware:** A malicious firmware can be inserted into the hardware devices by an attacker to maintain accessibility on the other devices or systems and hold footprints for long-term attacks.
- **Project file infection:** Attackers use malicious code to infect file dependencies such as objects or variables required for the functioning of programmable logic controllers (PLCs). Attackers often attempt to abuse the default functions of PLC.
  
Listed below are some additional techniques used by attackers to maintain persistence:
- System firmware
- Valid accounts

### Privilege Escalation
Privilege escalation allows an attacker to achieve higher-level access and authorizations to perform further malicious activities on an ICS system or network. Some of the techniques that can be used by an attacker to escalate privileges are as follows.
- **Exploiting software:** Attackers can take advantage of known software vulnerabilities by abusing any programming errors to elevate privileges.
- **Hooking:** It allows attackers to hook into the APIs of different processes for redirecting and calling them to elevate privileges.

### Evasion 
Attackers use this tactic to evade conventional defense mechanisms throughout their operations. Some of the techniques used to evade detection are as follows.
- **Removing the indicators:** Potential attack indicators are removed from a host to avoid detection and cover the attack footprints.
- **Rootkits:** An attacker can install rootkits to avoid detection by hiding different services, connections, and other system drivers.
- **Changing the operator mode:** The attackers can modify a controller’s operating mode to access and control different system functionalities.

Some of the additional techniques for evasion are listed below:
- Exploitation of software vulnerabilities
- Masquerading
- Spoofed reporting messages

###  Discovery 
Discovery is the process of gaining information about an ICS environment to assess and identify target assets. The following are some of the techniques that can be used to gain information about the ICS environment.
- **Enumerating the network connection:** Attackers can gain information about the communication patterns of different network devices.
- **Network sniffing:** An attacker can capture or monitor network information such as the protocol used, destination and source addresses, and other important information.
- **Identifying remote systems:** An attacker finds the details of other systems on the network through their hostnames, IP addresses, or other details to perform malicious activities.

Some of the additional techniques that can be used by an attacker for discovery are listed below:
- Remote system information discovery
- Wireless sniffing

### Lateral Movement
Attackers attempt to make additional movements across the target ICS environment by leveraging the existing access. Some of the techniques used by attackers for lateral movement are as follows.
- **Default credentials:** An attacker can leverage the in-built credentials of the control systems to perform administrative tasks.
- **Program download:** An attacker can transmit a user program within a controller by executing a program download.
- **Remote services:** An attacker can abuse the remote services to make lateral movements within the network assets and components.

Some of the additional techniques for lateral movement are listed below:
- Exploiting the remote services
- Lateral tool transfer
- Valid accounts

### Collection 
Collection refers to various methods that an attacker uses to gather information and gain knowledge regarding the data and domains of the ICS infrastructure. An attacker can use the following techniques to gather information.
- **Automated collection:** An attacker can use various tools or scripts to collect the information of an ICS environment automatically.
- **Information repositories:** Attackers can gain sensitive information such as layouts of a control system and specifications by targeting the information repositories.
- **I/O image:** The attackers can access the memory by obtaining the I/O image of a PLC for performing further malicious activities.

Some of the additional techniques for collecting data are listed below:
- Detecting the operating mode
- Man-in-the-middle attack
- Monitoring the process state
- Point and tag identification
- Program upload
- Screen capture
- Wireless sniffing

### Command and Control
An attacker attempts to deactivate, control, or exploit the physical control processes within the target ICS environment using command and control. Some of the techniques used for command and control are as follows.
- **Frequently used ports:** An attacker can use popular ports such as 80 and 443 to communicate and evade the conventional detection mechanisms.
- **Connection proxy:** Attackers can control the traffic of the target network across the ICS environment using a connection proxy.
- **Standard application-layer protocol:** Attackers can use different application-layer protocols such as HTTPS, Telnet, and Remote Desktop Protocol (RDP) to hide their actions and establish control over the systems.

### Inhibit Response Function
The inhibition of response function refers to the different ways an attacker attempts to thwart reactions against any security event such as hazard or failure. Some of the techniques associated with this tactic are as follows.
- **Activate firmware update mode:** An attacker can activate the firmware update mode and thwart normal response functionalities during a security event.
- **Block command messages:** An attacker can block various commands or instruction messages before they reach the control systems.
- **Block reporting messages:** An attacker can stop or disrupt the reporting messages from the industrial systems and prevent them from reaching their destination, allowing the attacker to hide their activities.

Some of the additional techniques for inhibiting response functions are listed below:
- Alarm suppression
- Blocking serial COM
- Data destruction
- Denial of service (DoS)
- Device restart/shutdown
- Control I/O image
- Changing alarm settings
- Rootkit
- Service stop
- System firmware

### Impair Process Control
Attackers use this tactic to disable, exploit, or control the physical control processes in the target environment. Some of the techniques used for this tactic are as follows.
- **I/O brute-forcing:** Attackers can brute-force the I/O addresses to control a process functionality without targeting a particular interface.
- **Alter the parameters:** An attacker can manipulate the control systems by altering their instruction parameters through appropriate programming.
- **Module firmware:** An attacker can re-program a device by injecting malicious firmware into it and thereby prepare it to perform other malicious tasks.
  
Some additional techniques associated with impairing process control are listed below:
- Spoofed reporting messages
- Unauthorized command messages

### Impact
Impact refers to the techniques used by an attacker to damage, disrupt, or gain control of the data and systems of the targeted ICS environment and its surroundings. Some of the techniques used for this tactic are as follows.
- **Damage to property:** An attacker can cause heavy damage to the property and its surrounding environments by performing various attacks on the ICS.
- **Loss of availability:** Attackers can disrupt or hamper the industrial processes to make them unresponsive to the associated connections.
- **Denial of control:** An attacker can manipulate the controls to disrupt the communications between the operators and the process controls.

Some of the additional techniques that can be used by the attackers are listed below: 
- Denial of view
- Loss of control
- Loss of productivity and revenue
- Loss of protection
- Loss of safety
- Loss of view
- Manipulation of control
- Manipulation of view
- Theft of operational information

---
## OT Threats
OT threats arise when operational technology systems, originally designed without security in mind, are connected to IT networks and the Internet. Many rely on outdated software, creating entry points for attackers to infiltrate corporate and industrial environments. Since OT networks link machines and production systems, successful attacks can cause large-scale disruption, data breaches, and even physical damage to critical infrastructure.

Discussed below are some of the important threats faced by OT networks: 
1. **Maintenance & Administrative Threat** → Attackers use zero-day flaws to compromise maintenance tools or admin systems, then push malware into OT/IT systems and industrial controllers (SCADA/PLC).
2. **Data Leakage** → Hackers access IT systems linked to OT (like IT/OT gateways) to steal sensitive operational files and configuration data.
3. **Protocol Abuse** → Old OT protocols (Modbus, CAN bus) lack security. Attackers misuse them (e.g., spoof emergency-stop) to send damaging single-packet commands.
4. **Destruction of ICS Resources** → Exploited vulnerabilities can disrupt or damage controllers and devices, causing safety hazards and production loss.
5. **Reconnaissance Attacks** → Poor encryption/authentication lets attackers scan and map OT networks to collect info for later attacks.
6. **Denial-of-Service (DoS) Attacks** → Attackers send malformed or malicious protocol requests (e.g., CIP) to break device communication or overload systems.
7. **HMI-Based Attacks** → Vulnerable Human–Machine Interfaces allow memory corruption, code injection, or privilege escalation, giving attackers control over operations.
8. **Exploiting Enterprise Tools** → Attackers target enterprise-specific systems (like SIS) and their protocols to inject malware and disrupt safety or control functions.
9. **Spear Phishing** → Targeted emails with malicious links/attachments infect a user’s machine, then the malware spreads to OT systems and damages industrial components.
10. **Malware Attacks** → Attackers reuse old malware or create OT-focused malware to exploit discovered weaknesses in industrial systems.
11. **Exploiting Unpatched Vulnerabilities** → Many ICS devices run without timely patches; attackers exploit these known flaws to gain access or cause harm.
12. **Side-Channel Attacks** → By observing physical signals (timing, power), attackers extract sensitive information from devices without breaking software protections.
13. **Buffer Overflow Attacks** → Flaws in HMI/web clients or communication interfaces let attackers inject malicious input and change system behavior.
14. **Exploiting RF Remote Controllers** → Insecure RF protocols for remote control can be spoofed or hijacked, allowing attackers to manipulate machinery or sabotage production.

---
## HMI-based Attacks
HMI-based attacks target the Human–Machine Interface that operators use to monitor and control industrial systems. If attackers compromise an HMI, they can manipulate control commands, hide or disable alerts, steal sensitive system information, and cause real-world damage to SCADA devices and infrastructure. Because HMIs sit at the operational core, protecting them with strong access controls, network segmentation, and monitoring is critical to prevent unsafe or covert changes.

Discussed below are various SCADA vulnerabilities exploited by attackers to perform HMI-based attacks on industrial control systems: 
1. **Memory Corruption** → Bugs like out-of-bounds reads/writes or stack/heap overflows let attackers overwrite memory in an HMI. This can crash the interface or make it run attacker-chosen instructions, disrupting displays or control logic.
2. **Credential Management** → Hard-coded or plainly stored passwords and poor protection of credentials let attackers steal admin logins. With those creds they can change settings, access databases, or take control of devices.
3. **Lack of Authorization/Authentication & Insecure Defaults** → Systems that ship with weak defaults, no encryption, or poor access checks allow anyone who reaches the interface to view or change sensitive data. Attackers exploit this to eavesdrop on commands, impersonate users, or escalate privileges.
4. **Code Injection** → Flaws that let attackers inject scripts or commands (e.g., SQL, OS, or HMI-specific script injections like Gamma’s EvalExpression) enable remote execution of arbitrary code. That means attackers can run commands, alter logic, or manipulate operator screens.
5. **Buffer Overflow Vulnerabilities** → When an HMI accepts more input than a buffer can hold, the excess data can overwrite important program data or return addresses. Attackers use this to crash software or run malicious code with the HMI’s privileges.
6. **Path Traversal** → Web servers or file handlers that don’t validate file paths let attackers read or modify files outside the web root (e.g., `../etc/passwd`). This reveals configuration, credentials, or logs, and can be used to further compromise the control system.

---
## Side-Channel Attacks 
Side-channel attacks steal secrets by observing how a device behaves physically rather than breaking its algorithms. Two common methods are timing analysis, which measures how long operations take to reveal information, and power analysis, which monitors changes in power use during cryptographic tasks. Industrial control systems (ICS) are often vulnerable because their hardware behavior can leak sensitive data through these channels. Continuous monitoring and hardware-level protections help reduce this risk.

### Timing Analysis 
Timing analysis attacks recover passwords by measuring how long a device takes to authenticate inputs. An attacker submits guesses one character at a time and watches the response time: if a guess makes the device take slightly longer, that often means a correct character or prefix. Repeating this lets the attacker reconstruct the whole password. These attacks are detectable and can be blocked by using constant-time comparisons, adding random timing noise, throttling attempts, and employing rate limits and monitoring for anomalous request patterns.

### Power Analysis 
Power-analysis attacks recover secrets by measuring a device’s power consumption while it operates. An attacker with physical access connects probes (like an oscilloscope and analysis hardware) to record power traces during cryptographic or authentication operations. Differences in the power profile—such as how the device behaves when a correct character is processed versus a wrong one—can reveal password characters or cryptographic keys. These attacks are stealthy because the device continues to function, and specialized software is used to extract keys from the measured traces.

If attackers obtain device keys, they can alter device configurations used in critical systems like power grids. Such changes can disrupt operations or feed false data to operators, causing incorrect control decisions. Because these devices are often managed centrally and distributed across the OT network, tampering with even one device can ripple out and affect large parts of the system. Continuous key protection, configuration integrity checks, and network monitoring are essential to prevent such damage.

<p align="center">
  <img width="494" height="326" alt="image" src="https://github.com/user-attachments/assets/7851ef99-cb63-4e9c-b3f3-72ab140ab374" />
</p>

---
## Hacking Programmable Logic Controller (PLC) 
Programmable Logic Controllers (PLCs) are used to control physical processes in critical infrastructure and are attractive targets for attackers. By locating internet-exposed PLCs with tools like Shodan, attackers can gain access and manipulate pin controls or firmware to disrupt operations. Compromised PLCs can suffer integrity and availability attacks—such as payload sabotage or installation of PLC rootkits—that alter process behavior or hide malicious activity, creating serious safety and operational risks for organizations.

### PLC Rootkit Attack

<p align="center">
  <img width="621" height="267" alt="image" src="https://github.com/user-attachments/assets/4376568f-09f9-4e42-ba09-e165317d66e2" />
</p>

Steps used to perform a PLC rootkit attack:
- **Step 1:** Attacker gains authorized access to the PLC device by injecting a rootkit. Then, he performs a control-flow attack against the PLC runtime to guess the default password and gain root-level access to the PLC.
- **Step 2:** Now, the attacker maps the input and output modules along with their locations in the memory to overwrite the input and output PLC parameters.
- **Step 3:** After learning about the I/O pins and the PLC logic mapping, the attacker manipulates the I/O initialization sequence, thus taking complete control over the PLC operations.

A PLC rootkit (or PLC ghost attack) exploits flaws in programmable logic controllers to replace the legitimate control code with malicious code. PLC CPUs have a programming mode (for downloading code) and a run mode (for executing it); after an attacker gains access they upload malware that the PLC stores and runs instead of the original program. That malicious code can alter I/O initialization and manipulate sensors and actuators, allowing the attacker to take full control of mechanical processes and cause disruption or physical damage. This attack needs deep knowledge of PLC architecture and can evade many standard detection methods.

---
## Evil PLC Attack 
An Evil PLC attack happens when an attacker finds programmable logic controllers (PLCs) that are exposed or poorly secured, then changes their configuration and control logic to disrupt industrial processes. By modifying a PLC’s settings and downloaded programs, the attacker can alter device behavior, tamper data, or stop production—often without immediate detection—because many Internet-exposed PLCs lack strong access controls or monitoring. Continuous network segmentation, access restrictions, and regular integrity checks help reduce this risk.

The following are the various steps involved in an Evil PLC attack:
- **Step 1:** Attacker identifies vulnerable PLC using Shodan or Censys.
- **Step 2:** The attacker exploits the vulnerable PLC firmware and weaponizes it by changing its programming logic through download procedures.
- **Step 3:** Using the infected PLC, the attacker initiates upload procedures on the connected workstations to execute arbitrary code.

<p align="center">
  <img width="478" height="377" alt="image" src="https://github.com/user-attachments/assets/ed1da595-95ff-498a-8ec9-67246957899a" />
</p>

---
## Hacking Industrial Systems through RF Remote Controllers 
Industrial machines controlled by RF remote controllers use a transmitter (TX) and receiver (RX) to send and act on radio commands. If these systems lack proper authentication or use predictable signals, an attacker standing within radio range can use a programmable transceiver to capture, craft, or replay packets and then send forged commands to the receiver. This lets the attacker control machinery, disrupt operations, or cause safety hazards without touching the network or devices directly.

Listed below are threats industrial systems often face via RF remote controllers:
- **Replay Attack** <br>
  Attackers record the commands (RF packets) transmitted by an operator and replay them to the target system to gain basic control over the system.

  <p align="center">
    <img width="491" height="295" alt="image" src="https://github.com/user-attachments/assets/afa7beb4-490a-41bc-807b-df25e3ecd338" />
  </p>

- **Command Injection** <br>
  Command injection occurs when an attacker manipulates or injects commands into a device’s communication, often by analyzing and reverse-engineering RF packets. By capturing legitimate commands and creating new ones, the attacker can control the device, disrupt its normal operations, or access sensitive functions without authorization.
    <p align="center">
      <img width="474" height="252" alt="image" src="https://github.com/user-attachments/assets/86e35631-bb40-4e48-9fbd-17d9476d4f41" />
    </p>

- **Abusing E-stop** <br>
  Using the above information, the attacker can send multiple e-stop (emergency stop) commands to the target device to cause DoS.

  <p align="center">
    <img width="583" height="321" alt="image" src="https://github.com/user-attachments/assets/f23f612a-6419-44f4-b634-a14819cb4dd0" />
  </p>

- **Re-pairing with Malicious RF Controller** <br>
  A re-pairing attack with a malicious RF controller occurs when an attacker hijacks a legitimate remote controller by pairing a fake controller with the target device. The attacker captures the command sequence from the original controller and uses the malicious controller to send commands, allowing unauthorized control and potential attacks on the device.

  <p align="center">
    <img width="467" height="375" alt="image" src="https://github.com/user-attachments/assets/71169358-4d13-4b4c-9872-bacb24138787" />
  </p>

- **Malicious Reprogramming Attack** <br>
  Attackers can inject malware into the firmware running on the remote controllers to maintain persistent and complete remote access over the target industrial system.

  <p align="center">
    <img width="497" height="350" alt="image" src="https://github.com/user-attachments/assets/43667b59-470c-4b9a-a217-97384832876c" />
  </p>

---
## OT Supply Chain Attacks
OT supply chain attacks target the hardware, software, or services of an organization’s suppliers to infiltrate its operational technology environment. By exploiting trusted relationships, attackers can bypass security measures, remain undetected for long periods, and cause significant damage to critical systems.

The following are some of the key techniques that attackers use to conduct supply chain attacks in OT environments:
| OT Supply Chain Attack             | Description |
|------------------------------------|-------------|
| **Third-Party Software Compromise** | Attackers inject malicious code into trusted software updates, creating backdoors or malicious functionalities when installed. |
| **Hardware Manipulation**           | Attackers alter hardware components during manufacturing or distribution, embedding malicious firmware or chips that can be activated once deployed in the target environment. |
| **Service Provider Breach**         | Attackers compromise service providers such as maintenance or support contractors to infiltrate the target organization's OT network, using stolen credentials, remote-access tools, or insider access. |
| **Injection of Malicious Components** | Attackers introduce malicious components or firmware into the supply chain by tampering during shipping or substituting legitimate parts with compromised ones. |
| **Exploitation of Trusted Relationships** | Attackers exploit the trust and access levels granted to suppliers, subcontractors, or partners to move laterally within the target organization’s network. |

---
## OT Malware
OT malware targets industrial systems and critical infrastructure, causing disruptions to both hardware and software. Examples like Stuxnet and INDUSTROYER.V2 can spread across networks, making devices inoperable. Industrial control systems are especially vulnerable due to legacy technology, proprietary software, and infrequent updates. OT ransomware can lock or encrypt system files, rendering industrial systems unusable and halting operations.

Discussed below are some popular examples of OT malware: 
- **Fuxnet** [https://claroty.com] <br>
  FuxNet is industrial control system (ICS) malware designed to disrupt operational technology (OT) environments. It can modify critical data, block access to sensor gateways, and damage sensors by rewriting memory chips. The malware exploits weak credentials to gain root access and uses techniques like sending malformed packets to corrupt sensors, causing inaccurate readings and potential physical damage to equipment.

  <p align="center">
    <img width="502" height="231" alt="image" src="https://github.com/user-attachments/assets/bda68a32-9a56-407e-a635-3c6ad29c528b" />
    <img width="502" height="321" alt="image" src="https://github.com/user-attachments/assets/37809e8c-8da5-48a8-ada0-0f3649c01622" />
  </p>

Listed below are some additional examples of OT malware:
- Kapeka
- Abyss Locker
- AvosLocker
- COSMICENERGY
- INDUSTROYER.V2
- Pipedream

---
## OT Malware Analysis: COSMICENERGY 
🔗Source: [https://cloud.google.com] <br>
COSMICENERGY is a specialized malware targeting operational technology (OT) and industrial control systems (ICS). It disrupts power systems by interacting with IEC 60870-5-104 (IEC-104) devices like remote terminal units (RTUs), similar to malware such as INDUSTROYER and INDUSTROYER.V2, which are known for causing outages in power grids.

<p align="center">
  <img width="438" height="367" alt="image" src="https://github.com/user-attachments/assets/93eadd6b-4cb6-4b2a-a78f-a1176f113a00" />
</p>

COSMICENERGY Attack Scenario:
- **Stage 1: Reconnaissance** <br>
  Attackers are likely to conduct reconnaissance to identify potential targets and gather information regarding the target environment. This includes identifying MSSQL servers that have access to the OT network, MSSQL credentials, and target IEC-104 device IP addresses. Attackers may also gather information about targeted assets, such as power-line switches, circuit breakers in an RTU, or relay configurations.

- **Stage 2: Initial Access** <br>
  Attackers gain initial access to the target environment, potentially through insecure methods such as exploiting vulnerabilities or using stolen credentials. In the case of COSMICENERGY, this may have involved connecting to a user-supplied remote MSSQL server. COSMICENERGY can upload and execute the following files on the target to achieve its objectives:

To generate the markdown table you've requested, I've compiled the information from the images you provided. This table is formatted to display correctly on GitHub.

-----

### File Hashes

| Filename | Description | Hash |
| :--- | :--- | :--- |
| `r3_iec104_control.exe` | PIEHOP PyInstaller executable | **MD5:** `cd8f394652db3d0376ba24a990403d20`<br>**SHA1:** `bc07686b422aa0dd01c87ccf557863ee62f6a435`<br>**SHA256:** `358f0f8c23acea82c5f75d6a2de37b6bea7785ed0e32c41109c217c48bf16010` |
| `r3_iec104_control` | PIEHOP Python compiled bytecode entry point | **MD5:** `f716b30fc3d71d5e8678cc6b81811db4`<br>**SHA1:** `e91e4df49afa628fba1691b7c668af64ed6b0e1d`<br>**SHA256:** `7dc25602983f7c5c3c4e81eeb1f2426587b6c1dc6627f20d51007beac840ea2b` |
| `r3_iec104_control.py` | Decompiled PIEHOP entry point Python script | **MD5:** `c018c54eff8d0b9be50b5d419d80f21`<br>**SHA1:** `4d7c4bc20e8c392ede2cb0cef787fe007265973b`<br>**SHA256:** `8933477e82202de97fb41f4cbbe6af32596cec70b5b47da022046981c01506a7` |
| `OT_T855_IEC104_GR.exe` | LIGHTWORK executable | **MD5:** `7b6678a1c0000344f4faf975c0cfc43d`<br>**SHA1:** `6eceb78acd1066294d72fe86ed57bf43bc6de6eb`<br>**SHA256:** `740e0d2fba550308344b2fb0e5ecfebdd09329bdcfaa909d3357ad4fe5552532` |
| `iec104_mssql_lib.pyc` | PIEHOP Python compiled bytecode | **MD5:** `adfa40d44a58e1bc909abca444f7f616`<br>**SHA1:** `a9b5b16769f604947b9d8262841aa3082f7d71a2`<br>**SHA256:** `182d6f5821a04028fe4b603984b4d33574b7824105142b722e318717a688969e` |
| `iec104_mssql_lib.py` | Decompiled PIEHOP Python script | **MD5:** `2b86adb6afdfa9216ef8ec2ff4fd2558`<br>**SHA1:** `20c9c04a6f8b95d2f0ce596dac226d56be519571`<br>**SHA256:** `90d96bb2aa2414a0262d38cc805122776a9405efece70beeebf3f0bcfc364c2d` |

- **Stage 3: Launching an Actual Attack** <br>
  Once attackers gain access to the target environment, they execute the COSMICENERGY malware. COSMICENERGY comprises two main components: PIEHOP and LIGHTWORK. PIEHOP, written in Python, connects to the MSSQL server to upload files, and issues remote commands to the RTU.

  <p align="center">
    <img width="563" height="37" alt="image" src="https://github.com/user-attachments/assets/5be7d6aa-e84e-494a-a683-cb6f3e6c46c2" />
  </p>

  The entry point of the PIEHOP (r3_iec104_control.py) invokes the PIEHOP’s main function, supplying the argument control=True. Then, the file r3_iec104_control.py imports the "iec104_mssql_lib" module.

  <p align="center">
    <img width="561" height="70" alt="image" src="https://github.com/user-attachments/assets/4a443c14-c5c2-4322-b832-b16fc4276c6a" />
    <img width="328" height="528" alt="image" src="https://github.com/user-attachments/assets/9ca36a26-73b9-412d-aaaf-a4faf69085d5" />
  </p>

  LIGHTWORK (OT_T855_IEC104_GR.exe), written in C++, crafts IEC-104 ASDU messages to change the state of the RTU information object addresses (IOAs) to ON or OFF, thereby affecting the actuation of power-line switches and circuit breakers. LIGHTWORK accepts the following command-line argument:
  ```
  <ip_address> <port> <command> [either ON (1) or OFF (0)]
  ```

  <p align="center">
    <img width="545" height="31" alt="image" src="https://github.com/user-attachments/assets/5731cc1a-9a02-456b-9ce0-41bb8a2caa07" />
  </p>

  Upon executing the OT_T855_IEC104_GR.exe, LIGHTWORK initiates its action by sending a “C_IC_NA_1 – station interrogation command” to the target station, retrieving the status of the target station. It then initiates a “C_SC_NA_1 – single command” for each hardcoded information object address (IOA) to change the state of the target station’s IOA (OFF or ON). Finally, it issues a single “C_CS_NA_1 – clock synchronization command” to the target station, which synchronizes the remote station time clock with the time clock of the device issuing the commands.

  <p align="center">
    <img width="573" height="155" alt="image" src="https://github.com/user-attachments/assets/97b0b32c-ddc0-48ff-8401-96682e83be35" />
  </p>

  If all the above commands are executed perfectly without any errors, LIGHTWORK provides the following command-line output:

  <p align="center">
    <img width="495" height="272" alt="image" src="https://github.com/user-attachments/assets/e5b2108e-a0ad-4e46-a7a2-439cc944867e" />
  </p>

  As described above, using these two components, the COSMICENERGY causes frequent power disruptions by interacting with the IEC-104 devices. By issuing ON or OFF commands to these devices, attackers can disrupt the flow of electricity, potentially causing widespread outages and damaging the electric grid.

- **Stage 4: Lateral Movement & Clearing Tracks** <br>
  COSMICENERGY does not exhibit traditional lateral movement capabilities, because it lacks the ability to spread laterally within a network. However, internal reconnaissance is required to gather the information necessary for execution, indicating that attackers may have moved laterally within the network to gather this information. <br>
  After achieving their objectives, the attackers attempt to cover their tracks by deleting traces of malware and other malicious activities from the target environment. This could include deleting the executable files of PIEHOP and LIGHTWORK from compromised systems.
