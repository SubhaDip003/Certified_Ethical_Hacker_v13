# 🎯 Mobile Platform Attack Vectors
Mobile security is becoming increasingly challenging with the emergence of complex attacks that use multiple attack vectors to compromise mobile devices. These security threats exploit critical data as well as financial information and other details of mobile users and may also damage the reputation of mobile networks and organizations.

This section discusses vulnerable areas in the mobile business environment, the OWASP top 10 mobile risks, the anatomy of mobile attacks, mobile attack vectors, associated vulnerabilities and risks, security issues arising from app stores, app sandboxing issues, mobile spam, pairing mobile devices on open Bluetooth and Wi-Fi connections, and other mobile attacks.

---
## Vulnerable Areas in Mobile Business Environment 
🔗Source: [https://www.ibm.com] <br>
Smartphones used in business are highly vulnerable because they store sensitive corporate and personal data while connecting through multiple channels like 3G/4G/5G, Wi-Fi, Bluetooth, and wired links. This wide connectivity increases the chances of attacks during data transmission. In addition to mobile-specific threats, smartphones also face the same risks as computers, networks, and web applications, making them a prime target for attackers.

<p align="center">
  <img width="669" height="409" alt="image" src="https://github.com/user-attachments/assets/38b6d12e-1c71-4cf3-9cd0-a94114354b37" />
</p>

---
## OWASP Top 10 Mobile Risks - 2024 
🔗Source: [https://owasp.org] <br>
According to OWASP, the following are the top 10 mobile risks: 

- **M1 - Improper Credential Usage** <br>
  Improper Credential Usage in mobile apps happens when passwords, tokens, or keys are stored or transmitted insecurely. Examples include hardcoded credentials, saving them in unprotected storage, or sending them without encryption. Such weaknesses let attackers steal credentials, gain unauthorized access, and compromise sensitive data or user accounts, leading to serious breaches.

- **M2 - Inadequate Supply Chain Security** <br>
  OWASP M2 – Inadequate Supply Chain Security highlights the risks of using outdated or insecure third-party components in mobile apps. Poor coding practices, weak code reviews, and insecure distribution can introduce vulnerabilities, allowing attackers to exploit flaws, insert malicious code, or even compromise app signing keys. This can lead to data theft, spying, backdoors, denial-of-service, or unauthorized access to backend servers, ultimately harming both users and the developer’s reputation.

- **M3 - Insecure Authentication/Authorization** <br>
  Insecure authentication and authorization in mobile apps occur when login and access controls are poorly implemented, such as weak password rules, unsafe token handling, or missing permission checks. Attackers can exploit this by using low-privileged tokens or reverse-engineering the app to perform actions meant for higher-privileged users. This allows them to impersonate legitimate users, bypass security, and access sensitive data through malware or automated botnets.

- **M4 - Insufficient Input/Output Validation** <br>
  This category involves the inadequate validation or sanitization of inputs from users or external sources within a mobile application, leading to SQL injection, command injection, and cross-site scripting (XSS) attacks. Vulnerability can also arise owing to errors in application logic, lack of security awareness, or insufficient testing and code review practices. Exploiting these vulnerabilities can lead to unauthorized data access and manipulation, malicious code execution, and application crashes, potentially compromising an entire mobile device.

- **M5 - Insecure Communication** <br>
  Insecure communication in mobile apps happens when they use weak or outdated protocols, misconfigured settings, or invalid SSL certificates. This allows attackers to intercept or modify data sent over the network. Such flaws can expose sensitive information, enable account takeover, and lead to identity theft or other fraudulent activities.

- **M6 - Inadequate Privacy Controls** <br>
  M6 – Inadequate Privacy Controls refers to weak protection of sensitive user data like names, addresses, or financial details in mobile apps. When developers fail to enforce proper access controls or ignore privacy regulations, attackers can steal or misuse this data for fraud, impersonation, or identity theft. This not only harms users but also exposes organizations to loss of trust and regulatory penalties.

- **M7 - Insufficient Binary Protections** <br>
  M7 - Insufficient Binary Protections refers to mobile apps that lack safeguards against reverse engineering or code tampering. Without these protections, attackers can analyze or modify the app’s code, insert malicious functionality, create fake versions of the app, or unlock paid features for free, putting both users and businesses at risk.

- **M8 - Security Misconfiguration** <br>
  Security Misconfiguration refers to flaws caused by weak or incomplete security settings in mobile apps. Issues like weak encryption, insecure storage, unnecessary permissions, default credentials, or misconfigured access controls can let attackers exploit the app. These misconfigurations may lead to data breaches, account hijacking, or unauthorized access to sensitive information and backend systems.

- **M9 - Insecure Data Storage** <br>
  Insecure data storage in mobile apps happens when sensitive information like credentials, personal data, or financial details is stored without proper protection. Weak encryption, plain text storage, or poor credential management make this data easy for attackers to steal through device access, malware, or intercepted transmissions. Such flaws can cause data breaches, account compromise, financial loss, and even identity theft.

- **M10 - Insufficient Cryptography** <br>
  Insufficient cryptography in mobile apps happens when weak algorithms, poor key management, or flawed implementations are used for protecting data. This allows attackers to break encryption, reverse-engineer hashes, or misuse cryptographic flaws to access sensitive information, bypass security, and compromise user accounts or data.

---
## Anatomy of a Mobile Attack 
🔗Source: [https://www.nowsecure.com] <br>
Because of the extensive usage and implementation of bring your own device (BYOD) policies in organizations, mobile devices have emerged as a prime target for attacks. Attackers scan these devices for vulnerabilities. Such attacks can involve the device and the network layer, the data center, or a combination of them. <br>
Attackers exploit vulnerabilities associated with the following to launch malicious attacks: 

<p align="center">
  <img width="1078" height="483" alt="image" src="https://github.com/user-attachments/assets/f9022483-fae3-4eee-aff3-6db6ef7c642f" />
</p>

### The Device
Vulnerabilities in mobile devices pose significant risks to sensitive personal and corporate data. Attackers targeting the device itself can use various entry points. Device-based attacks are of the following types: 

#### Browser-based Attacks 
Browser-based methods of attack are as follows:
1. **Phishing** → Attackers trick users with fake emails, pop-ups, or websites that look real, asking for sensitive data like login details, credit card numbers, or addresses. Mobile users are more at risk because small screens hide full URLs and warning signs.
2. **Framing** → Hackers use hidden iFrames (a web page inside another) to load malicious content on trusted sites. This is often used with clickjacking to secretly steal user information.
3. **Clickjacking** → Users are fooled into clicking hidden buttons or links, thinking they’re doing something harmless. In reality, the attacker steals sensitive info or controls the device.
4. **Man-in-the-Mobile** → Malware is placed on a mobile device to intercept one-time passwords (OTPs) sent via SMS or calls. The stolen OTPs are then sent to attackers for account takeover.
5. **Buffer Overflow** → When a program stores more data than expected, it overwrites memory and causes crashes or abnormal behavior. Hackers exploit this to execute malicious code on the device.
6. **Data Caching** → Mobile devices store cached data for speed and efficiency. Attackers target these caches to steal sensitive information stored locally on the device.

#### Phone/SMS-based Attacks 
Phone/SMS-based methods of attack are as follows:
- **Baseband Attacks:** → Attackers exploit vulnerabilities in a phone’s GSM/3GPP baseband processor, which sends and receives radio signals to cell towers.
- **SMiShing** → SMS phishing (also known as SMiShing) is a type of phishing fraud in which an attacker uses SMS to send text messages containing deceptive links of malicious websites or telephone numbers to a victim. The attacker tricks the victim into clicking the link or calling the phone number and revealing his or her personal information such as social security number (SSN), credit card number, and online banking username and password.

#### Application-based Attacks 
Application-based methods of attack are as follows: 
1. **Sensitive Data Storage** → Some apps installed and used by mobile users employ weak security in their database architecture, which makes them targets for attackers who seek to hack and steal the sensitive user information stored in them.
2. **No Encryption/Weak Encryption** → Apps that transmit unencrypted or weakly encrypted data are susceptible to attacks such as session hijacking.
3. **Improper SSL Validation** → Security loopholes in an application’s SSL validation process may allow attackers to circumvent the data security.
4. **Configuration Manipulation** → Apps may use external configuration files and libraries that can be exploited in a configuration manipulation attack. This includes gaining unauthorized access to administration interfaces and configuration stores as well as retrieval of clear text configuration data.
5. **Dynamic Runtime Injection** → Attackers manipulate and abuse the run time of an application to circumvent security locks and logic checks, access privileged parts of an app, and even steal data stored in memory.
6. **Unintended Permissions** → Misconfigured apps can sometimes open doors to attackers by providing unintended permissions.
7. **Escalated Privileges** → Attackers engage in privilege escalation attacks, which take advantage of design flaws, programming errors, bugs, or configuration oversights to gain access to resources that are usually protected from an application or user.

Other application-based methods of attack include UI overlay/pin stealing, third-party code, intent hijacking, zip directory traversal, clipboard data, URL schemes, GPS spoofing, weak/no local authentication, integrity/tampering/repackaging, side-channel attack, app signing key unprotected, app transport security, XML specialization, and so on.

#### The System 
OS-based methods of attack are as follows:
1. **No Passcode/Weak Passcode** → If a user sets no lock or uses a weak passcode (like 1234 or 0000), attackers can easily guess it and access sensitive files, apps, and personal data on the device.
2. **iOS Jailbreaking** → Jailbreaking removes Apple’s built-in security controls, giving full root access. This makes the device more open to malware, poor performance, and data theft since security restrictions no longer protect it.
3. **Android Rooting** → Rooting provides admin-level access to the Android system. While it allows customization, it also exposes sensitive data and makes the device vulnerable to malicious apps and attacks.
4. **OS Data Caching** → The operating system temporarily stores data in cache memory. Attackers can reboot the phone with a malicious OS, dump this memory, and steal sensitive information from it.
5. **Passwords and Data Accessible** → iOS stores encrypted passwords and data in the Keychain, but flaws in cryptography can be exploited. Attackers use these weaknesses to decrypt and extract saved passwords, keys, and private info.
6. **Carrier-loaded Software** → Phones often come with pre-installed apps from carriers. Some of these apps may contain vulnerabilities that attackers can abuse to spy, modify, or steal data from the device.
7. **User-initiated Code** → Attackers trick users into installing malicious apps or clicking harmful links. Once installed, the code can hijack browser sessions, steal cookies, or abuse permissions to compromise the device.

Other OS-based methods of attack include no/weak encryption, confused deputy attack, TEE/secure enclave processor, side-channel leakage, multimedia/file format parsers, kernel driver vulnerabilities, resource DoS, GPS spoofing, device lockout, and so on.

#### The Network 
Network-based methods of attack are as follows:
1. **Wi-Fi (Weak/No Encryption)** → If a wireless network uses no encryption or weak algorithms, attackers can eavesdrop and capture sensitive data like passwords and messages. Even SSL/TLS, though stronger, can be attacked if not properly implemented.
2. **Rogue Access Points** → Hackers set up fake or unauthorized access points. When users connect to these, attackers can spy on traffic and steal information from the protected network.
3. **Packet Sniffing** → Using tools like Wireshark, attackers capture data packets moving through the network. If information like login credentials is sent in plain text, it can easily be stolen.
4. **Man-in-the-Middle (MITM)** → Attackers secretly sit between two communicating systems, reading, altering, or injecting false data into the communication without the users noticing.
5. **Session Hijacking** → Hackers steal active session IDs (like cookies) and use them to impersonate the victim, gaining full access to accounts or services without needing a password.
6. **DNS Poisoning** → Attackers corrupt DNS records to redirect users to malicious websites instead of the real ones, tricking victims into sharing sensitive information.
7. **SSLStrip** → Attackers downgrade a secure HTTPS connection to insecure HTTP. Victims think they are on a secure site, but their data is actually being sent without encryption.
8. **Fake SSL Certificates** → Hackers create or use forged certificates to make a malicious site look secure (HTTPS). This lets them intercept or manipulate supposedly “secure” traffic.

Other network-based methods of attack include BGP hijacking, HTTP proxies, etc.

#### The Data Center/CLOUD 
Data centers have two primary points of entry: a web server and a database. 
1. **Web-server-based attacks** <br>
   Web-server-based vulnerabilities and attacks are of the following types:
   - **Platform Vulnerabilities** → Weaknesses in the operating system, server software (like IIS), or web server modules can be exploited by attackers. They may also analyze communication between a device and the server to find protocol or access flaws.
   - **Server Misconfiguration** → Mistakes in web server setup (like weak permissions, open directories, or default settings) can let attackers gain unauthorized access to sensitive files or services.
   - **Cross-Site Scripting (XSS)** → Attackers inject malicious scripts (JavaScript, HTML, Flash, etc.) into web pages. When other users visit these pages, the script runs in their browser, allowing attackers to steal data, hijack sessions, or deliver malware.
   - **Cross-Site Request Forgery (CSRF)** → Attackers trick users into performing unintended actions on a trusted site where they are already logged in, like transferring money or changing account details, by sending hidden malicious requests.
   - **Weak Input Validation** → If the server trusts input from users or apps without proper checks, attackers can bypass security and perform attacks like injection, buffer overflow, or XSS. This can lead to stolen data or system compromise.
   - **Brute-Force Attacks** → Attackers repeatedly try different usernames, passwords, or inputs until they find the correct one. Applications without limits on login attempts are especially vulnerable.

     Other web-server-based vulnerabilities and attacks include cross-origin resource sharing, side-channel attack, hypervisor attack, VPN, and so on.

2. Database Attacks
   Database-based vulnerabilities and attacks are of the following types:
   - **SQL Injection** → Hackers insert malicious SQL commands into input fields of a web app. This tricks the database into running those commands, letting attackers view, steal, or even change sensitive data without proper authorization.
   - **Privilege Escalation** → Attackers exploit weaknesses in the database or application to move from low-level access to higher-level (admin/root) access, giving them control over sensitive data and system functions.
   - **Data Dumping** → The attacker forces the database to export or reveal large amounts of information, which may include usernames, passwords, financial details, or other private records.
   - **OS Command Execution** → Some databases allow commands that interact with the operating system. If exploited, attackers can run system-level commands, potentially gaining full control of the server.

---
## How a Hacker can Profit from Mobile Devices that are Successfully Compromised 
🔗Source: [https://www.sophos.com], [https://securelist.com] <br>
When hackers compromise a smartphone, they gain access to valuable data such as contacts, photos, emails, banking details, and business information. They can spy on user activities, steal financial credentials, impersonate the victim on social media, or even use the device as part of a botnet. This allows attackers to profit through identity theft, fraud, data resale, or large-scale malicious campaigns.

After successfully compromising the mobile device, hackers can exploit the following: 

<p align="center">
  <img width="712" height="455" alt="image" src="https://github.com/user-attachments/assets/b17eed61-a3ac-472f-b379-6687a018a73a" />
</p>

---
## Mobile Attack Vectors and Mobile Platform Vulnerabilities 
### Mobile Attack Vectors
Mobile devices have attracted the attention of attackers owing to their widespread use. Such devices access many of the resources that traditional computers use. Moreover, these devices have some unique features that have led to the emergence of new attack vectors and protocols. Such vectors make mobile phone platforms susceptible to malicious attacks both from the network and upon physical compromise. Given below are some of the attack vectors that allow an attacker to exploit vulnerabilities in mobile OS, device firmware, or mobile apps.

<p align="center">
  <img width="673" height="194" alt="image" src="https://github.com/user-attachments/assets/37ed7568-3c82-49a8-a0ae-20c0e50a37a3" />
</p>

### Mobile Platform Vulnerabilities and Risks
Mobile platform vulnerabilities arise as smartphones become the primary tool for internet use, communication, and data management. With advanced hardware and operating systems, they attract cybercriminals who exploit new features to launch attacks. These risks can compromise user privacy, steal sensitive data, or even give attackers full control of a device, making mobile security a critical concern.

Some mobile platform vulnerabilities and risks are listed below:
```text
- Malicious apps in stores					- Privacy issues (Geolocation
- Mobile malware							- Weak data security
- App sandboxing vulnerabilities			- Weak data security
- Weak device and app encryption			- Excessive permissions
- OS and app update issues					- Weak communication security
- Jailbreaking and rooting					- Physical attacks
- Mobile application vulnerabilities		- Insufficient code obfuscation
- Insufficient transport layer security		- Insufficient session expiration
```
---
## Security Issues Arising from App Stores 
App stores are a major target for attackers to spread malicious apps. Hackers often repackage genuine apps with malware and upload them to third-party stores, tricking users into downloading them. Once installed, these apps can steal sensitive data like photos, call logs, and documents, or damage other apps and files. Weak or no app vetting in some stores increases the risk, while social engineering can also push users to install unsafe apps outside official stores, leading to data theft and further attacks.

<p align="center">
	<img width="676" height="185" alt="image" src="https://github.com/user-attachments/assets/161e6ca0-3431-44b4-b92f-2cbb5d8860bd" />
</p>

---
## App Sandboxing Issues 
App sandboxing is a security method that limits what a mobile app can access, keeping it isolated from other apps and system resources. This protects users from malware and untrusted code by restricting apps to only their intended functions. However, if the sandbox is weak, attackers can exploit its vulnerabilities, bypass isolation, and gain access to sensitive data or system resources, putting the device at risk.

<p align="center">
	<img width="688" height="227" alt="image" src="https://github.com/user-attachments/assets/4d4471ce-75bc-43b0-ab78-a77791c4847b" />
</p>

---
## Mobile Spam 
Mobile spam, also called SMS or text spam, refers to bulk unsolicited messages sent to mobile phones through SMS, MMS, email, or instant messaging. These messages may contain ads, fake prize notifications, phishing attempts, or malicious links designed to steal personal and financial information. Mobile spam not only misleads users but can also cause financial loss, spread malware, and even lead to corporate data breaches, while consuming valuable network bandwidth.

<p align="center">
	<img width="304" height="434" alt="image" src="https://github.com/user-attachments/assets/b499f183-4ff7-4f1b-9b61-4048bdea35be" />
</p>

---
## SMS Phishing Attack (SMiShing) (Targeted Attack Scan) 
SMS phishing, or SMiShing, is a type of attack where criminals send fake text messages to trick users into revealing sensitive information or downloading malware. These messages often look urgent or tempting, such as claiming a lottery win, account suspension, or gift voucher, and include a malicious link or phone number. When the victim clicks the link, they are redirected to a phishing site that steals details like credit card numbers, PINs, or personal information, which attackers then use for identity theft, online fraud, or other malicious activities.

<p align="center">
	<img width="630" height="356" alt="image" src="https://github.com/user-attachments/assets/3aff95af-edeb-46a2-887f-c89a29dfb82a" />
</p>

### Why is SMS Phishing Effective? 
SMS phishing is an effective attack method for several reasons: 
1. **High Open Rates** → People usually open SMS messages instantly, giving attackers a better chance to deliver their scam.
2. **Trust in SMS** → Many see SMS as more personal and reliable than email, so they question it less.
3. **Limited Space** → Short messages look simple and convincing, making it harder to notice phishing clues.
4. **Lack of Awareness** → Most people know about email scams but are less aware of SMS-based (smishing) threats.
5. **Mobile Device Usage** → Phones often lack strong security tools, leaving users more exposed to attacks.
6. **Ease of Impersonation** → Hackers can fake phone numbers to appear like trusted sources such as banks or companies.
7. **Urgency and Action** → Messages often create panic, pushing users to act fast without checking authenticity.
8. **Direct Links & Downloads** → SMS can contain links to fake sites or malware downloads, and users may click without thinking.
9. **Shortened URLs** → Attackers use URL shorteners to hide malicious links, making them look normal and safe.
10. **No Anti-Phishing Protection** → Unlike email, SMS has no strong filters or security features, so scams easily reach the target.

### SMS Phishing Attack Examples 

<p align="center">
	<img width="703" height="243" alt="image" src="https://github.com/user-attachments/assets/6f74d2dd-8df1-489d-acec-1e0ae267c0be" />
</p>

---
## Pairing Mobile Devices on Open Bluetooth and Wi-Fi Connections 
Pairing mobile devices on open Bluetooth or Wi-Fi networks creates serious security risks. Attackers can use these unsecured connections to spread malware, intercept unencrypted data, or trick users into accepting malicious pairing requests. Through techniques like bluesnarfing and bluebugging, they can eavesdrop, steal sensitive information, or perform man-in-the-middle attacks. This exposure may lead to identity theft and other harmful activities, especially when devices connect automatically in public or untrusted networks.

### Bluesnarfing (Stealing information via Bluetooth)
Bluesnarfing is an attack where an attacker uses a Bluetooth connection to secretly steal data from a device. If Bluetooth is enabled and set to “discoverable,” vulnerable devices such as phones or laptops can be exploited. Attackers can then access sensitive information like contacts, messages, emails, photos, or business files without the user’s knowledge.

### Bluebugging (Taking over a device via Bluetooth) 
Bluebugging is a Bluetooth attack where an attacker secretly takes control of a victim’s device. Once connected, the attacker can access sensitive data, read or forward calls and messages, use the internet, and even view contacts, photos, or videos—all without the user’s knowledge. This turns the device into a backdoor for malicious activities.

<p align="center">
	<img width="724" height="247" alt="image" src="https://github.com/user-attachments/assets/1cacc212-6e05-4873-88b3-29f7d54e0e27" />
</p>

---
## Agent Smith Attack 
The Agent Smith attack spreads through malicious apps disguised as games or tools on third-party stores like 9Apps. Once installed, the hidden code replaces popular apps such as WhatsApp or SHAREit with infected versions. These fake apps flood the device with fraudulent ads for profit and can also steal sensitive data like personal details, credentials, and banking information through attacker-controlled commands.

<p align="center">
	<img width="703" height="175" alt="image" src="https://github.com/user-attachments/assets/43ed8a52-315c-4f58-990b-8cc261b4d1e4" />
</p>

---
## Exploiting SS7 Vulnerability
Signaling System 7 (SS7) is a communication protocol that allows mobile users to exchange communication through another cellular network (especially when roaming). Mobile devices are meant to be carried across different locations to serve their users. Changing the telecom operator or using the network of another cell tower is allowed via the SS7 protocol. This signaling mechanism is operated depending on mutual trust between the operators, without any authentication verification. Since the SS7 signaling network is not isolated, the attacker can exploit this vulnerability to perform an MITM attack by impeding text messages and calls between the communicating devices. The attacker can eavesdrop on bank credentials, OTPs and other sensitive information routed through the network. This vulnerability in SS7 can also allow the attacker to bypass two-factor authentication and end-to-end encryption via SMS. 

### Threats Associated with SS7 vulnerability
When the attacker gains access to the SS7 protocol, the victim’s device faces the following risks:
- Exposing the subscriber’s identity
- Revealing the network identity
- Spying on and intercepting the network to steal personal data
- Allowing phone tapping
- Performing DoS attacks to damage the reputation of the target telecom operator
- Tracking geographic locations

<p align="center">
	<img width="703" height="194" alt="image" src="https://github.com/user-attachments/assets/49f51e69-bc5a-4f6d-8bdc-a149111b743d" />
</p>

---
## Simjacker: SIM Card Attack
Simjacker is a SIM card attack that exploits a vulnerability in the S\@T browser, a toolkit built into many SIM cards. Attackers send a special SMS carrying hidden commands, which the SIM executes without the user’s knowledge. This allows them to track location, monitor calls, collect device details like IMEI, send premium-rate messages, redirect the browser to malicious sites, or even disable the SIM. Since the attack runs silently on the SIM card, it can take full control of the device without any user interaction.

**Steps involved in Simjacker attack**
- The attacker sends fraudulent SMS containing hidden code or instructions from a SIM Application Toolkit (STK)
- The victim receives the malicious SMS and the S@T browser on the SIM card automatically recognizes and processes the hidden instructions or code
- The injected code performs various activities on the device without the user’s consent
- The accomplice device receives the user information via SMS, which an attacker can use to track live locations, exfiltrate the device information, and perform many other malicious activities.

<p align="center">
	<img width="707" height="291" alt="image" src="https://github.com/user-attachments/assets/7fa238ca-00f7-4985-a990-1e0616e3058e" />
</p>

---
## Call Spoofing 
Call spoofing is a method where attackers fake the caller ID to make it look like the call is coming from a trusted source, such as a bank or government agency. This tricks people into sharing sensitive details or making payments. It can also be used to hide identities while making harassing or threatening calls.

The various tools that an attacker can use to perform call spoofing against a targeted phone number are discussed below: 
- **SpoofCard** [https://www.spoofcard.com] <br>
	SpoofCard is a tool that lets attackers hide their real phone number by using a virtual one to make calls or send texts. It also allows voice changing, adding background noise, sending calls straight to voicemail, and recording conversations for storage or sharing on cloud services. This makes it useful for concealing identity and carrying out malicious activities.

<p align="center">
	<img width="227" height="488" alt="image" src="https://github.com/user-attachments/assets/6f6f9e55-4993-48a9-9b07-bfe46c0a6dac" />
</p>

Some additional call spoofing tools are listed below:
- **Fake Call** [https://play.google.com]
- **SpoofTel** [https://www.spooftel.com]
- **Fake Call and SMS** [https://play.google.com]
- **Fake Caller ID** [https://fakecallerid.io]
- **Phone Id- Fake Caller Buster** [https://play.google.com]

---
## OTP Hijacking/Two-Factor Authentication Hijacking 
OTP hijacking, or two-factor authentication hijacking, happens when attackers intercept one-time passwords sent via SMS, email, or authenticator apps. They often do this by stealing personal data, tricking telecom providers into transferring SIM ownership, or using SIM jacking malware to read OTPs. Once they gain control of the OTP, attackers can log into accounts, reset passwords, and steal sensitive information, all while the victim may believe the OTP was simply not delivered.

<p align="center">
	<img width="639" height="278" alt="image" src="https://github.com/user-attachments/assets/db730951-90b1-4f59-9121-6a7ebac227c1" />
</p>

### OTP Hijacking via Lock Screen Notifications
Attackers physically steal SMS-based OTPs from the target user’s mobile phone by monitoring the user’s actions closely. They can view the notifications on the target user’s lock screen when they request for an OTP. Attackers can hijack lock screen notifications using different methods such as eavesdropping or tricking the user into lending their phone for making an emergency call.

---
## OTP Hijacking Tools 
- **AdvPhishing** [https://github.com/Ignitetch/AdvPhishing] <br>
	AdvPhishing is a social media phishing tool that assists attackers in bypassing two-factor or OTP authentication. AdvPhishing can gain access to the targeted IP address and is compatible with Linux and Termux OS. Attackers deploy AdvPhishing on public networks using NGrok tunnelling and localhost tunnelling.

	<p align="center">
		<img width="371" height="332" alt="image" src="https://github.com/user-attachments/assets/8f25233e-566d-4746-b90b-991756a01b02" />
	</p>

- **mrphish** [https://github.com/noob-hackers/mrphish] <br>
	mrphish is a bash-based script used for phishing social media accounts with port forwarding and OTP bypassing control. This tool works on both rooted and non-rooted Android devices.

 	<p align="center">
		<img width="349" height="336" alt="image" src="https://github.com/user-attachments/assets/c7d539f0-fb41-450f-8801-9d9fd91520e5" />
	</p>

---
## Camera/Microphone Capture Attacks 
Camera and microphone capture attacks occur when attackers gain unauthorized access to a device’s camera or microphone to spy on users. This allows them to secretly record conversations, capture images or videos, and steal sensitive information, leading to serious privacy and security risks. The following are two different attacking methods attackers often employ to compromise camera and micro phones of the devices. 

### Camfecting Attack 
A camfecting attack happens when an attacker takes control of a device’s webcam using a remote access Trojan (RAT). This allows the attacker to secretly watch or record the victim, often disabling the camera light to avoid detection. Through this, they can steal personal photos, videos, and even location details, while controlling the camera remotely.

**Steps Involved in Camfecting Attack**
- The attacker either sends a phishing mail with a malicious link or lures the victim into visiting a malicious website.
- When the victim clicks on the malicious link or visits the malicious website, malware is downloaded and installed on the device, providing remote access to the attacker.
- Now, the attacker can capture personal data such as photos and videos. 

<p align="center">
	<img width="641" height="134" alt="image" src="https://github.com/user-attachments/assets/d0a42242-2c24-496f-9494-dbe64e0c3899" />
</p>

### Android Camera Hijack Attack
Attackers attempt to leverage Google’s camera application, which is widely used in Android devices as the default camera app. An attacker can exploit Android’s multiple security bypass vulnerabilities to circumvent the required permissions and gain access to the victim’s camera and microphone. Further, the attacker can exploit this vulnerability even if the mobile device is locked. Android camera applications generally require storage permissions to store photos and videos. 
These applications need the victim to provide permissions such as
- `android.permission.CAMERA`
- `android.permission.RECORD_AUDIO`
- `android.permission.ACCESS_COARSE_LOCATION`
- `android.permission.ACCESS_FINE_LOCATION`

Such storage permissions provide unrestricted access to the entire internal storage and allow attackers to perform various activities such as capturing photos; recording videos and voice calls; and accessing stored photos, videos, GPS locations, and other sensitive information.

**Steps Involved in Android Camera Hijack Attack**
Attackers exploit various bypass vulnerabilities on the target Android device by tricking the victim into downloading a malicious app. The malicious app installs a Trojan on the victim’s device without their knowledge. When the victim starts using the infected application, a persistent connection is established between the victim and attacker. Even if the victim closes the application, the connection persists, allowing attackers to capture photos and record videos stealthily.

<p align="center">
	<img width="577" height="207" alt="image" src="https://github.com/user-attachments/assets/f1a0d90e-dbad-460f-a892-9d8f875cedd6" />
</p>

---
## Camera/Microphone Hijacking Tools 
- **StormBreaker** [https://github.com/xaviha/stormbreaker] <br>
	Attackers use the StormBreaker tool for social engineering by capturing the camera/microphone. The tool can access the device’s location, webcam, and microphone without explicitly requesting any permissions.

	<p align="center">
		<img width="670" height="347" alt="image" src="https://github.com/user-attachments/assets/8ae66617-aefd-4643-9d66-3194b3e34f53" />
	</p>

The following are some additional camera/microphone hacking tools: 
- **CamPhish** [https://github.com/techchipnet/CamPhish]
- **HACK-CAMERA** [https://github.com/hackerxphantom/HACK-CAMERA]
- **E-TOOL** [https://github.com/Expert-Hacker/E-TOOL]
- **CamOver** [https://github.com/EntySec/CamOver]
- **CAM-DUMPER** [https://github.com/AnandKatariya/Cam-Dumper]
