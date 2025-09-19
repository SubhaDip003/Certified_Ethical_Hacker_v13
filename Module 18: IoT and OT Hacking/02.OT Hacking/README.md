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












