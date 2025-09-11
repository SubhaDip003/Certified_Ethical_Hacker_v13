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






