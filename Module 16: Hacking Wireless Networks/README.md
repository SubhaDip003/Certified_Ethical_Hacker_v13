# 🛜 Wireless Concepts
Wireless networking is a communication method that uses radio-frequency signals instead of physical cables to connect devices. It makes data access mobile, portable, and more flexible by transmitting information through electromagnetic waves. This removes the need for complex wired setups and allows devices to communicate and share data seamlessly without physical connections.

---
## Wireless Terminology 
1. **Global System for Mobile Communications (GSM)** → A worldwide standard for mobile communication that allows users to make calls, send texts, and transfer mobile data securely over wireless networks. It ensures compatibility between mobile devices and networks across the globe.

2. **Bandwidth** → Refers to the maximum amount of data that can travel through a network connection in a given time, measured in bits per second (bps). Higher bandwidth means faster data transfer and better performance for tasks like streaming, downloading, or online gaming.

3. **Access Point (AP)** → A device that acts as a bridge between wireless devices and a wired network. It allows devices like laptops, phones, and IoT gadgets to connect wirelessly using Wi-Fi or Bluetooth standards, essentially functioning as the entry point to a wireless LAN.

4. **Basic Service Set Identifier (BSSID)** → The unique MAC address of a specific Access Point (AP) in a wireless network. Even if users don’t see it directly, their device connects to a BSSID when joining Wi-Fi. If they move around, their device might switch BSSIDs seamlessly without losing internet connection.

5. **Industrial, Scientific, and Medical (ISM) Band** → A group of radio frequencies reserved internationally for non-commercial uses like research, healthcare devices, and industrial applications. Wi-Fi and Bluetooth also operate in these ISM bands, which are free to use without a license.

6. **Hotspot** → A location, such as a café, airport, or library, where public Wi-Fi is available. By enabling Wi-Fi on a device, users can connect to the Internet through these hotspots, which are often free or sometimes password-protected for security.

7. **Association** → The process where a wireless device (like a laptop or phone) formally connects to an AP. It involves authentication, exchanging credentials, and getting permission to send and receive data over that wireless network.

8. **Service Set Identifier (SSID)** → The name of a Wi-Fi network that users see when searching for available connections. It is a unique identifier (up to 32 characters) that allows users to pick the right network from several available options. All devices connecting to the same WLAN must use the same SSID.

9. **Orthogonal Frequency-Division Multiplexing (OFDM)** → A digital modulation technique that splits data into many smaller signals, each carried on different frequencies. Because the frequencies don’t interfere with each other, OFDM increases efficiency, reduces signal loss, and supports high-speed data transmission, making it ideal for Wi-Fi, 4G, and 5G.

10. **Multiple Input, Multiple Output - Orthogonal Frequency-Division Multiplexing (MIMO-OFDM)** → A powerful combination of using multiple antennas (MIMO) and OFDM technology. It boosts data speed, reduces interference, and enhances network reliability, making it the backbone of modern wireless technologies like 4G LTE and 5G.

11. **Direct-Sequence Spread Spectrum (DSSS)** → A method that spreads data signals over a wide frequency band using a pseudo-random code. This makes the signal more resistant to interference, noise, and jamming. DSSS is commonly used in Wi-Fi and GPS systems for secure and reliable communication.

12. **Frequency-Hopping Spread Spectrum (FHSS)** → A technique where the signal quickly switches between multiple frequency channels in a pseudorandom order. Since both sender and receiver know the hopping pattern, it’s hard for attackers to intercept or jam the signal. This method improves security and is used in technologies like Bluetooth.

---
## Wireless Networks
Wireless networks transmit data using radio waves, mainly at the physical layer of the network. Wi-Fi, based on the IEEE 802.11 standard, is the most common wireless technology. It allows devices like laptops, smartphones, and game consoles to connect to the internet through a wireless access point (AP) within range. Wi-Fi uses methods such as DSSS, FHSS, infrared, and OFDM to establish communication between the transmitter and receiver, enabling flexible and wide-area connectivity without physical cables.

The following are some of the advantages and disadvantages of wireless networks: 

**Advantages**
- Installation is fast and easy without the need for wiring through walls and ceilings
- Easily provides connectivity in areas where it is difficult to lay cables
- The network can be accessed from anywhere within the range of an AP
- Public spaces such as airports, libraries, schools, and even coffee shops offer constant Internet connections through WLANs

**Disadvantages**
- Security may not meet expectations
- The bandwidth suffers as the number of devices in the network increases
- Wi-Fi upgrades may require new wireless cards and/or APs
- Some electronic equipment can interfere with Wi-Fi networks

### Types of Wireless Networks 
The different types of wireless networks are described as follows. 

#### 1. Extension to a Wired Network
A user can extend a wired network by placing APs between a wired network and wireless devices. A wireless network can also be created using an AP. The types of APs include the following:
- **Software APs (SAPs):** SAPs can be connected to a wired network, and they run on a computer equipped with a wireless network interface card (NIC).
- **Hardware APs (HAPs):** HAPs support most wireless features.

In this type of network, the AP acts as a switch, providing connectivity for computers that use a wireless NIC. The AP can connect wireless clients to a wired LAN, which allows wireless access to LAN resources such as file servers and Internet connections.

<p align="center">
  <img width="585" height="340" alt="image" src="https://github.com/user-attachments/assets/c833fd6c-8724-4d9e-a015-249e9a6199f7" />
</p>

#### 2. Multiple Access Points
Multiple access points are used in wireless networks to extend coverage when one AP cannot cover the entire area. Each AP’s range overlaps with the next, allowing users to move seamlessly through the network using roaming. Extension points can also act as wireless relays, further increasing the range and providing connectivity to distant locations.

<p align="center">
  <img width="613" height="338" alt="image" src="https://github.com/user-attachments/assets/f6f37dc0-914e-4c88-8ffb-0302f404c44d" />
</p>

#### 3. LAN-to-LAN Wireless Network
A LAN-to-LAN wireless network connects two or more local area networks through access points (APs) using wireless links. While APs can interconnect with each other to extend connectivity between different networks, setting up and managing such wireless LAN interconnections is complex because it requires proper configuration, security, and reliable signal management.

<p align="center">
  <img width="570" height="298" alt="image" src="https://github.com/user-attachments/assets/f98c944f-60ee-4586-8472-f967539cc212" />
</p>

#### 4. 3G/4G/5G Hotspot
A 3G/4G/5G hotspot is a type of wireless network that provides Wi-Fi access to Wi-Fi-enabled devices, including MP3 players, notebooks, tablets, cameras, PDAs, netbooks, and more.

<p align="center">
  <img width="507" height="308" alt="image" src="https://github.com/user-attachments/assets/b8ee21e3-8da8-4b0f-af39-e5061ffbb37f" />
</p>

---
## Wireless Standards 
IEEE 802.11 is the standard for wireless LANs, first introduced in 1997 with speeds of 1–2 Mbps using infrared and the 2.4 GHz band. Originally designed for basic wireless connections to Ethernet, it has since evolved to support high-speed data transfer, multiple frequency bands, enterprise authentication, strong encryption, and quality of service. Over time, new amendments like 802.11a, 802.11b, 802.11g, 802.11n, and 802.11ac have improved speed, reliability, roaming, and security, making Wi-Fi a core technology for modern networks.

| Amendments       | Frequency (GHz)   | Modulation                   | Speed (Mbps)            | Range (Meters)            |
|------------------|-------------------|------------------------------|-------------------------|---------------------------|
| 802.11 (Wi-Fi)   | 2.4               | DSSS, FHSS                   | 1, 2                    | 20 – 100                  |
| 802.11a          | 5                 | OFDM                         | 6, 9, 12, 18, 24, 36, 48, 54 | 35 – 100              |
|                  | 3.7               |                              |                         | 5000                      |
| 802.11ax         | 2.4 to 5          | 1024-QAM                     | 2400                    | 240                       |
| 802.11b          | 2.4               | DSSS                         | 1, 2, 5.5, 11           | 35 – 140                  |
| 802.11be         | 2.4, 5, 6         | QAM                          | 3000                    | 120                       |
| 802.11d          | It is an enhancement to 802.11a and 802.11b that enables global portability by allowing variations in frequencies, power levels, and bandwidth |
| 802.11e          | It provides guidance for prioritization of data, voice, and video transmissions enabling QoS |
| 802.11g          | 2.4               | OFDM                         | 6, 9, 12, 18, 24, 36, 48, 54 | 38 – 140              |
| 802.11i          | A standard for wireless local area networks (WLANs) that provides improved encryption for networks that use 802.11a, 802.11b, and 802.11g standards; defines WPA2-Enterprise/WPA2-Personal for Wi-Fi |
| 802.11n          | 2.4, 5            | MIMO-OFDM                    | 54 – 600                | 70 – 250                  |
| 802.15.1 (Bluetooth) | 2.4           | GFSK, π/4-DPSK, 8DPSK        | 25 – 50                 | 10 – 240                  |
| 802.15.4 (ZigBee) | 0.868, 0.915, 2.4| O-QPSK, GFSK, BPSK           | 0.02, 0.04, 0.25        | 1 – 100                   |
| 802.16 (WiMAX)   | 2 – 11            | SOFDMA                       | 34 – 1000               | 1609.34 – 9656.06 (1–6 miles) |

- **802.11:** The 802.11 (Wi-Fi) standard applies to WLANs and uses FHSS or DSSS as the frequency-hopping spectrum. It allows an electronic device to establish a wireless connection in any network.
  
- **802.11a:** It is the first amendment to the original 802.11 standard. The 802.11 standard operates in the 5 GHz frequency band and supports bandwidths up to 54 Mbps using orthogonal frequency-division multiplexing (OFDM). It has a high maximum speed but is relatively more sensitive to walls and other obstacles.
  
- **802.11ax (Wi-Fi 6):** Wi-Fi 6, also known as 802.11ax, is the latest generation of Wi-Fi and enhances the foundation of 802.11ac (Wi-Fi 5). It supports speeds of up to 9.6 Gbps, uses orthogonal frequency-division multiple access (OFDMA) to efficiently manage multiple connections, and improves performance in crowded areas through features such as BSS Coloring and target wake time (TWT). Wi-Fi 6 is ideal for dense environments, such as stadiums, airports, and smart homes with many connected devices.

- **802.11b:** IEEE extended the 802.11 standard by creating the 802.11b specifications in 1999. This standard operates in the 2.4 GHz ISM band and supports bandwidths up to 11 Mbps using direct-sequence spread spectrum (DSSS) modulation.
  
- **802.11be (Wi-Fi 7):** Wi-Fi 7, also known as 802.11be, is an emerging standard that aims to significantly improve Wi-Fi 6/6E. It supports speeds of up to 30 Gbps, uses a multilink operation (MLO) to aggregate multiple channels across different bands, and reduces the latency for real-time applications. Wi-Fi 7 was designed for future-proof, ultrahigh-speed Internet, virtual reality, augmented reality, and advanced IoT applications.
  
- **802.11d:** The 802.11d standard is an enhanced version of 802.11a and 802.11b that supports regulatory domains. The specifications of this standard can be set in the media access control (MAC) layer.
  
- **IEEE 802.11e:** It is used for real-time applications such as voice, VoIP, and video. To ensure that these time-sensitive applications have the network resources they need, 802.11e defines mechanisms to ensure quality of service (QoS) to Layer 2 of the reference model, which is the MAC layer.
  
- **802.11g:** It is an extension of 802.11 and supports a maximum bandwidth of 54 Mbps using OFDM technology. It uses the same 2.4 GHz band as 802.11b. The IEEE 802.11g standard defines high-speed extensions to 802.11b and is compatible with the 802.11b standard, which means 802.11b devices can work directly with an 802.11g AP.
  
- **802.11i:** The IEEE 802.11i standard improves WLAN security by implementing new encryption protocols such as the Temporal Key Integrity Protocol (TKIP) and Advanced Encryption Standard (AES).
  
- **802.11n:** The IEEE 802.11n is a revision that enhances the 802.11g standard with multiple-input multiple-output (MIMO) antennas. It works in both the 2.4 GHz and 5 GHz bands. Furthermore, it is an IEEE industry standard for Wi-Fi wireless local network transportation. Digital Audio Broadcasting (DAB) and WLAN use OFDM.
  
- **802.11ah:** Also called Wi-Fi HaLow, uses 900 MHz bands for extended-range Wi-Fi networks and supports Internet of Things (IoT) communication with higher data rates and wider coverage range than the previous standards.
  
- **802.11ad:** The 802.11ad standard includes a new physical layer for 802.11 networks and works on the 60 GHz spectrum. The data propagation speed in this standard is much higher from those of standards operating on the 2.4 GHz and 5 GHz bands, such as 802.11n.
  
- **802.12:** Media utilization is dominated by this standard because it works on the demand priority protocol. The Ethernet speed with this standard is 100 Mbps. Furthermore, it is compatible with the 802.3 and 802.5 standards. Users currently on those standards can directly upgrade to the 802.12 standard.
  
- **802.15:** It defines the standards for a wireless personal area network (WPAN) and describes the specifications for wireless connectivity with fixed or portable devices.

- **802.15.1 (Bluetooth):** Bluetooth is mainly used for exchanging data over short distances on fixed or mobile devices. This standard works on the 2.4 GHz band.

- **802.15.4 (ZigBee):** The 802.15.4 standard has a low data rate and complexity. The specification used in this standard is ZigBee, transmits long-distance data through a mesh network. The specification handles applications with a low data rate of 250 Kbps, but its use increases battery life.

- **802.15.5:** This standard deploys itself on a full-mesh or half-mesh topology. It includes network initialization, addressing, and unicasting.

- **802.16:** The IEEE 802.16 standard is a wireless communications standard designed to provide multiple physical layer (PHY) and MAC options. It is also known as WiMax. This standard is a specification for fixed broadband wireless metropolitan access networks (MANs) that use a point-to-multipoint architecture.


---
## Service Set Identifier (SSID) 
A Service Set Identifier (SSID) is the unique name that identifies a wireless network (WLAN). It is a case-sensitive string of up to 32 alphanumeric characters and acts as the shared identifier between access points (APs) and client devices. When a user wants to connect to Wi-Fi, their device looks for available SSIDs broadcasted by APs. The SSID is included in the frame header of packets, which allows users to discover and attempt authentication with a specific network.

All devices and APs within the same WLAN must use the same SSID for communication. If an administrator changes the SSID, every client device must be reconfigured to connect again. By default, many devices ship with SSIDs that display the vendor’s name, which can pose a security risk if not changed, as attackers can target known configurations.

Although an SSID is required for devices to connect, it does not provide actual security. SSIDs are transmitted in plaintext within probe requests and responses, meaning attackers can easily capture them using network sniffing tools. Even if an SSID is hidden, it can still be revealed once legitimate clients connect to the network. Non-secure configurations, such as allowing connections with a blank SSID or the value set to “any,” make networks even more vulnerable.

Because of these weaknesses, the SSID should not be relied upon as a security mechanism. Stronger protections such as WPA2 or WPA3 encryption must be implemented to secure WLANs against unauthorized access and attacks.

---
## Wi-Fi Authentication Process 

### Pre-Shared Key (PSK) Mode 
Pre-Shared Key (PSK) mode, also called WPA-PSK or WPA2-PSK, secures Wi-Fi networks using a single shared password. This password is entered on both the router and the device to allow access. It is commonly used in homes and small offices because it is simple to set up and manage. However, its security depends entirely on choosing a strong, secret password—weak keys can make the network vulnerable to attacks.

<p align="center">
  <img width="709" height="195" alt="image" src="https://github.com/user-attachments/assets/82bf8cb3-e435-419b-b180-3a3f3818797b" />
</p>

### Centralized Authentication Mode
Centralized authentication mode, used in WPA/WPA2-Enterprise (802.1X), relies on a Remote Authentication Dial-In User Service (RADIUS) server to authenticate users individually instead of using a shared password. Each user is given unique credentials, such as a username, password, or digital certificate, which are verified by the server before granting access. This approach provides stronger security and is ideal for large networks like corporate offices, schools, and government agencies.

<p align="center">
  <img width="741" height="371" alt="image" src="https://github.com/user-attachments/assets/6d063605-f8da-4a93-b734-beaac83f7418" />
</p>

---
## Types of Wireless Antennas 
Antennas are an integral part of Wi-Fi networks. In addition to sending and receiving radio signals, they convert electrical impulses into radio signals and vice versa. The types of wireless antennas include the following: 

### Directional Antenna 
A directional antenna can broadcast and receive radio waves from a single direction. In order to improve transmission and reception, the directional antenna’s design allows it to work effectively in only a few directions. This also helps in reducing interference.

<p align="center">
  <img width="525" height="276" alt="image" src="https://github.com/user-attachments/assets/ea6451bd-4d0a-4448-98e1-ce5c72c92faa" />
</p>

### Omnidirectional Antenna 
Omnidirectional antennas radiate electromagnetic (EM) energy in all directions. It provides a 360° horizontal radiation pattern. They radiate strong waves uniformly in two dimensions, but the waves are usually not as strong in the third dimension. These antennas are efficient in areas where wireless stations use time-division multiple access technology. A good example for an omnidirectional antenna is the antenna used by radio stations. These antennas are effective for radio signal transmission because the receiver may not be stationary. Therefore, a radio can receive a signal regardless of its location.

<p align="center">
  <img width="512" height="260" alt="image" src="https://github.com/user-attachments/assets/c99020b8-84e9-4d60-a8ea-c83b194a5af8" />
</p>

### Parabolic Grid Antenna
A parabolic grid antenna works like a satellite dish but uses a wire grid instead of a solid surface. Its design allows highly focused radio beams that can transmit Wi-Fi signals over long distances, up to around 10 miles. This makes it useful for capturing weak signals with better quality, giving attackers more data, higher bandwidth, and stronger power for Layer-1 DoS or man-in-the-middle attacks. It is lightweight, space-saving, and can handle both horizontal and vertical signal polarization.

<p align="center">
  <img width="670" height="215" alt="image" src="https://github.com/user-attachments/assets/ef49680a-2c7d-4e4e-b9d0-a2d220d80ce7" />
</p>

### Yagi Antenna
A Yagi antenna, also known as a Yagi–Uda antenna, is a unidirectional antenna designed to focus signals in one direction for better communication. It operates in the 10 MHz to UHF/VHF range, offering high gain and improved signal reception with reduced noise. The antenna is built with a reflector, a dipole, and multiple directors, which together create an end-fire radiation pattern that strengthens signal transmission and reception in the chosen direction.

### Dipole Antenna
A dipole antenna is a straight electrical conductor measuring half a wavelength from end to end, and it is connected at the center of the radio frequency (RF) feed line. Also called a doublet, the antenna is bilaterally symmetrical; therefore, it is inherently a balanced antenna. This kind of antenna feeds on a balanced parallel-wire RF transmission line.

### Reflector Antennas
Reflector antennas use a parabolic surface to focus electromagnetic signals at a single point, improving signal strength and reducing interference, especially in satellite communications. Larger reflectors relative to the wavelength provide higher gain, but they are expensive to manufacture.
