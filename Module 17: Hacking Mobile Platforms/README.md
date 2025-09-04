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








