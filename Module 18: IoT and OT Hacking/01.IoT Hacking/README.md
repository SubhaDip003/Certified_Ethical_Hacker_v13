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

