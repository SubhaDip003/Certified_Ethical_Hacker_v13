# 🖥️ System Hacking
System hacking is the process of gaining unauthorized access to computer systems to steal data, control the system, or cause damage. Ethical hackers and penetration testers perform system hacking in a legal and controlled way to find weaknesses before real attackers do. This helps organizations fix security issues and protect their systems from being hacked by malicious users.

# 🔑 Gaining Access
Gaining access in system hacking means breaking into a computer or system by using stolen passwords, exploiting software bugs, or tricking users. The goal is to take control of the system so the hacker can view, change, or steal data. It's one of the key steps in hacking after finding system weaknesses.

## 🔐Cracking Passwords
Explanation of the three Microsoft authentication mechanisms:

1. **Security Accounts Manager (SAM) Database**: This is a database on Windows systems that stores usernames and hashed passwords for local user accounts. It’s used to verify login attempts on the same computer. The SAM file is stored at `%SystemRoot%\system32\config\SAM` in Windows systems, and Windows mounts it in the registry under the `HKEY_LOCAL_MACHINE\SAM` registry hive. It stores LM or NTLM hashed passwords.


2. **NTLM Authentication**: NTLM (NT LAN Manager) is an older Windows authentication method that uses a challenge-response system to prove your identity without sending your password directly. It’s less secure and more vulnerable to attacks.

3. **Kerberos Authentication**: A modern and secure authentication method that uses tickets and a trusted third party (Key Distribution Center) to verify identities. It’s faster and more secure than NTLM, and it's the default in most Windows networks today.

---
![NTLMHash](https://github.com/user-attachments/assets/743328ba-8306-4a27-afa1-bbfe76b902b5)
---

## Tools to Extract the Password Hashes 
The following tools can be used to extract the password hashes from the target system:

### pwdump7 
🔗Source: [https://www.tarasco.org]

pwdump7 is an application that dumps the password hashes (one-way functions or OWFs) from NT’s SAM database. pwdump extracts LM and NTLM password hashes of local user accounts from the Security Account Manager (SAM) database. This application or tool runs by extracting the binary SAM and SYSTEM file from the filesystem, and then extracts the hashes. One of the most powerful features of pwdump7 is that it is also capable of dumping protected files. Pwdump7 can also extract passwords offline by selecting the target files. The use of this program requires administrative privileges on the remote system. 

![pwdump7](https://github.com/user-attachments/assets/644fde34-1834-4459-8d0f-ccdf27b8c018)

### Some of the additional tools to extract password hashes are as follows:
- **Mimikatz** [https://github.com/ParrotSec/mimikatz]
- **DSInternals** [https://github.com/MichaelGrafnetter/DSInternals]
- **hashcat** [https://hashcat.net]
- **PyCrack** [https://github.com/saurabhwadekar/pycrack]
> #### Note: The use of the above tools requires administrative privileges on the remote system.

## Types of Password Attacks

* **Non-Electronic Attack:**
  Involves physical or social tactics like **shoulder surfing** or **dumpster diving** to obtain passwords without using technical tools.

* **Active Online Attack:**
  Attacker tries to log in to an account in real time using methods like **brute-force** or **dictionary attacks** over services like SSH or HTTP.

* **Passive Online Attack:**
  Attacker captures network traffic using tools like **Wireshark** to sniff unencrypted passwords without interacting directly with the system.

* **Offline Attack:**
  Attacker steals password hashes (e.g., from SAM database) and cracks them locally using tools like **Hashcat** or **John the Ripper**.

---
## Non-Electronic Attack
---

* **Social Engineering Attack**: Tricking people into revealing confidential information (e.g., phishing emails or impersonating tech support).
* **Shoulder Surfing**: Watching someone type passwords or PINs over their shoulder (e.g., in cafes, ATMs, or offices).
* **Dumpster Diving**: Searching through trash to find sensitive data (e.g., discarded company reports or employee login details).

---
## **Active Online Attacks**

### **Dictionary Attack**: 
Tries known/common passwords from a pre-built list against a target (e.g., trying `password123`, `letmein` on SSH login).
### **Brute-Force Attack**: 
Attempts every possible password combination until the correct one is found (e.g., `aaaa`, `aaab`, `aaac`, etc.).

- 🧰 **John the Ripper** 🔗Source [https://www.openwall.com/john/] – A powerful open-source tool used for fast password cracking through dictionary, brute-force, and hybrid attacks.
```
john --wordlist=rockyou.txt hash.txt                         # → Basic dictionary attack using rockyou.txt against given hashes.
john --show hash.txt                                         # → Displays cracked passwords alongside their hashes.
john --format=raw-md5 --wordlist=rockyou.txt hash.txt        # → Cracks hashes of a specific format (e.g., raw MD5) using a wordlist.
john --rules --wordlist=rockyou.txt hash.txt                 # → Enables smart mangling rules for wordlist to try complex variations.
john --incremental hash.txt                                  # → Performs a brute-force attack (slow but thorough) without a wordlist.
john --mask=?l?l?l?l?l hash.txt                              # → Mask attack; tries combinations like abcde (5 lowercase letters).
john --fork=4 --wordlist=rockyou.txt hash.txt                # → Utilizes 4 CPU cores in parallel to crack faster.
john --session=mysession --wordlist=rockyou.txt hash.txt     # → Starts a named session for later resume.
john --restore=mysession                                     # → Resumes a previously saved cracking session.
john --format=NT hash.txt --wordlist=rockyou.txt             # → Cracks NTLM hashes (used in older Windows systems).
john --list=formats                                          # → Lists all supported hash types/formats.
john --show --format=raw-md5 hash.txt                        # → Shows cracked passwords for hashes of specified format.
```

### **Rule-based Attack**: 
Enhances dictionary or brute-force attacks by applying specific rules or patterns (e.g., adding `123` to each word: `admin123`, `root123`).

---
  * **Hybrid Attack**: Combines dictionary words with brute-force variations (e.g., trying `admin`, `admin1`, `admin2024`).
  * **Syllable Attack**: Generates passwords from syllable combinations (e.g., `fa`, `fo`, `fur` → `fafur`, `fofa`).
---
### **Password Spraying Attack**: 
Uses one or a few common passwords across many accounts (e.g., trying `Welcome1` on 50 employee emails).

- 🐉 **Hydra** - is a fast and flexible password cracking tool used to perform brute-force attacks on various network protocols and services.
```
hydra -l admin -P passwords.txt ftp://192.168.1.100             # → Brute-force FTP login for user 'admin' using a password list.
hydra -L users.txt -P passwords.txt ssh://192.168.1.100         # → Brute-force SSH using a list of usernames and passwords.
hydra -l admin -P passwords.txt http-get://192.168.1.100/login  # → Brute-force HTTP GET login form for user 'admin'.
hydra -l admin -P passwords.txt -s 2222 ssh://192.168.1.100     # → Brute-force SSH on a non-default port (2222).
hydra -L users.txt -p 123456 rdp://192.168.1.100                # → Brute-force RDP login using user list and fixed password.
hydra -L users.txt -P passwords.txt smb://192.168.1.100         # → Brute-force SMB login using username and password lists.
hydra -C creds.txt ssh://192.168.1.100                          # → Brute-force SSH using a colon-separated combo file (user:pass).
hydra -V -l admin -P passwords.txt ssh://192.168.1.100          # → Verbose mode: shows each attempt while cracking SSH.
hydra -t 4 -L users.txt -P passwords.txt ssh://192.168.1.100    # → Sets 4 parallel threads for faster brute-forcing.
hydra -f -l admin -P passwords.txt ftp://192.168.1.100          # → Stops after the first valid FTP credential is found.
hydra -R                                                        # → Resumes a previous Hydra session if it was interrupted.
hydra -x 6:8:a ssh://192.168.1.100 -l root                      # → Brute-force SSH using generated passwords (length 6–8, lowercase alpha).
```
> #### ✅ Pro Tip: Replace the protocol (e.g. ftp://, ssh://, http-get://) based on the service you're attacking.


**The following are some additional password-spraying attack tools:**
- **thc-hydra** [https://github.com/vanhauser-thc/thc-hydra]
- **Metasploit** [https://www.metasploit.com]
- **Rubeus** [https://github.com/GhostPack/Rubeus]
- **adfsbrute** [https://github.com/ricardojoserf/adfsbrute]
- **CrackMapExec** [https://github.com/byt3bl33d3r/CrackMapExec]

### **Mask Attack**: 
Uses known patterns (like `Abc123!`) to narrow down brute-force attempts (e.g., if format is `?u?l?l?d?d?d` for `Axy123`).

- 🐈‍⬛**Hashcat** 🔗Source [https://hashcat.net] - Attackers use the hashcat tool to perform password attacks such as brute-force attacks, dictionary attacks, and mask attacks. To perform mask attacks, an attacker must know the flags used for the built-in charset, custom charset, and attack mode to create an appropriate pattern for the password.
  
#### Built-in Charsets 
The following built-in charset helps specify the type of character to be used: 
- ?l = abcdefghijklmnopqrstuvwxyz
- ?u = ABCDEFGHIJKLMNOPQRSTUVWXYZ
- ?d = 0123456789
- ?h = 0123456789abcdef
- ?H = 0123456789ABCDEF
- ?s = «space
- !"#$%&'()*+,-./:;<=>?@[]^_`{|}~
- ?a = ?l?u?d?s
- ?b = 0x00 - 0xff
  
#### Custom Charset
A custom charset is used in situations where the attacker is unsure about the type of character in a particular placeholder: 
* -1 abcdefghijklmnopqrstuvwxyz0123456789
* -1 abcdefghijklmnopqrstuvwxyz?d
* -1 ?l0123456789
* -1 ?l?d
---

#### 🔹 What is Hash Mode?

Hash mode tells Hashcat what kind of hash you are trying to crack — like **MD5**, **NTLM**, or **SHA256**. For example:

* `-m 0` is for **MD5** hashes.
* `-m 1000` is for **NTLM** hashes.

---

#### 🔹 Common Hashcat Commands (in simple terms):

1. **Crack passwords like `abc123` (3 letters + 3 digits)**:

```bash
hashcat -a 3 -m 0 hashes.txt ?l?l?l?d?d?d
```

* `-a 3`: Brute-force attack.
* `-m 0`: MD5 hash.
* `?l`: lowercase letter.
* `?d`: digit.

---

2. **Crack 8-character passwords like `aBcxy1903`**:

```bash
hashcat -a 3 -m 0 -1 ?l?u hashes.txt ?1?1?1?1?1?1?1?1
```

* `-1 ?l?u`: Makes a custom charset of both lowercase and uppercase letters.
* `?1`: Uses the custom charset.

---

3. **Crack a password with unknown length (from 6 to 10 characters)**:

```bash
hashcat -a 3 -m 0 -i --increment-min=6 --increment-max=10 53ab0dff8ecc7d5a18b4416d00568f02 ?l?d
```

* `--increment`: Tells Hashcat to try all lengths between min and max.
* `?l?d`: Use lowercase letters and digits.

---

This way, you can customize the cracking pattern depending on what you know about the password.  
#### Some hashcat commands:
```
# Hashcat is a powerful password recovery tool that cracks hashed passwords using CPU or GPU.

hashcat -h                                                     # → Displays the help menu with all options and hash modes.
hashcat -m 0 -a 0 hashes.txt wordlist.txt                      # → Dictionary attack on MD5 hashes using a wordlist (mode 0 = MD5, attack mode 0 = straight).
hashcat -m 1000 -a 0 ntlm.txt rockyou.txt                      # → Performs a dictionary attack on NTLM hashes (mode 1000).
hashcat -m 0 -a 3 hash.txt ?a?a?a?a                            # → Brute-force attack using all possible characters for a 4-character password.
hashcat -m 0 -a 3 hash.txt ?l?l?l?d?d                          # → Mask attack using pattern: 3 lowercase + 2 digits.
hashcat -m 0 -a 0 -r rules/best64.rule hash.txt wordlist.txt   # → Dictionary attack with rules to mutate words (e.g., add numbers, symbols).
hashcat -m 0 -a 6 hash.txt wordlist.txt wordlist.txt           # → Hybrid attack (dictionary + mask) — appends dictionary words together.
hashcat -m 0 -a 1 hash.txt pre.txt post.txt                    # → Hybrid attack (dictionary prepended + dictionary appended).
hashcat -m 0 -a 3 -i -1 ?l?d hash.txt ?1?1?1?1?1               # → Incremental brute-force with custom charset of lowercase and digits.
hashcat -m 0 -a 0 -O -w 3 hash.txt rockyou.txt                 # → Optimized performance dictionary attack with high workload profile.
hashcat -m 1800 -a 0 hash.txt rockyou.txt                      # → Cracks SHA-512(Unix) hashes (common in Linux shadow files).
hashcat -m 22000 -a 3 wifi.hc22000 ?d?d?d?d?d?d?d?d            # → Brute-force 8-digit numeric WiFi WPA/WPA2 hash captured via hcxpcapngtool.
hashcat --example-hashes                                       # → Shows sample hashes for supported algorithms.
```


### **Password Guessing**:

  * **Manual Password Cracking Algorithm**: Human guesses passwords based on personal knowledge (e.g., pet names, birthdays).

  * **Default Password**: Uses manufacturer-set default credentials (e.g., `admin:admin` on routers).
  * The following are some of the online tools to search default passwords: 
    - [https://www.fortypoundhead.com]
    - [https://cirt.net]
    - [https://www.routerpasswords.com]
    - [https://default-password.info]
    - [https://192-168-1-1ip.mobi]

### **Trojans/Spyware/Keyloggers**: 
Malicious programs record keystrokes or send login data to attackers (e.g., `DarkComet` RAT capturing bank credentials).

### **Hash Injection / Pass-the-Hash (PtH) Attack**: 
Uses stolen password hashes to authenticate without needing plaintext passwords (e.g., using `NTLM` hash in SMB authentication).

![PtH](https://github.com/user-attachments/assets/d2e89645-833a-4a43-8fa4-17b50a961067)

### LLMNR/NBT-NS Poisoning
**LLMNR/NBT-NS Poisoning** is a network attack where an attacker responds to name resolution broadcasts on a local network, pretending to be a legitimate system, to capture NTLMv2 password hashes for cracking and later use — commonly performed using tools like **Responder**, **Metasploit**, or **Inveigh**.

![LLMNR](https://github.com/user-attachments/assets/a9839f7a-f2ff-41fe-8ffd-d56ee7616e7b)

Steps involved in LLMNR/NBT-NS poisoning:
1. A user mistypes a network address (for example, types `\\DtaServr` instead of the correct `\\DataServer`) and Windows can’t find it via DNS.
2. Because DNS fails, the user’s PC broadcasts a name‐lookup request over LLMNR/NBT‐NS asking, “Who knows `\\DtaServr`?”
3. The attacker, listening on the network, immediately replies “I’m `\\DtaServr`,” even though they are not the real server.
4. Believing the attacker, the user’s PC tries to authenticate by sending its NTLMv2 hash.
5. The attacker captures that hash and sends back a fake error so the user never realizes they spoke to an impostor.
6. Offline later, the attacker cracks the NTLMv2 hash to recover the user’s password and can then log in to the real `\\DataServer` (or any other system the user has access to).

**LLMNR/NBT-NS Poisoning Tools**
- **Responder** 🔗Source: [https://github.com/SpiderLabs/Responder] - Responder is an LLMNR, NBT-NS, and MDNS poisoner. It responds to specific NBT-NS (NetBIOS Name Service) queries based on their name suffix. By default, the tool only responds to a File Server Service request, which is for SMB.

### Internal Monologue Attack
An Internal Monologue Attack is a technique where an attacker tricks a Windows system into revealing password hashes from memory without sending any data over the network, allowing them to capture and crack the hashes locally.


#### **Internal Monologue Attack – Step-by-Step:**

![Internal Monologue Attack](https://github.com/user-attachments/assets/87d23173-765f-408e-af4e-78f0d0ec3119)

1. **Turn Off Security Settings:**

   * The attacker temporarily **disables protections** (like `LMCompatibilityLevel`, etc.) to make Windows use a weaker login method (NetNTLMv1).

2. **Grab Login Info:**

   * The attacker collects **login tokens** from programs running on the system. These are used to act like real users.

3. **Ask Windows to Generate Hashes:**

   * Using Windows' own system (`NTLM SSP`), the attacker **asks for authentication responses** (NetNTLMv1 hashes) pretending to be each user.

4. **Put Settings Back:**

   * Once the hashes are collected, the attacker **restores the original security settings** to avoid being detected.

5. **Crack the Hash:**

   * The attacker uses **rainbow tables** (precomputed password-hash maps) to **crack the NetNTLMv1 hash** and get the real password.

6. **Login with Cracked Password:**

   * Finally, the attacker uses that cracked password to **log in as the victim** and gain **system-level access**.

#### 💡In Short:
The attacker **tricks Windows into giving NTLM hashes without touching LSASS**, then **cracks them offline** to steal passwords — even in secure environments where tools like Mimikatz don’t work.

### Cracking Kerberos Password
Cracking Kerberos passwords is a way for attackers to exploit weaknesses in the Kerberos authentication system, which is widely used in networks to verify users. Because it's so commonly used, attackers look for ways to break it. Two popular methods are Kerberoasting and AS-REP Roasting.
In Kerberoasting, the attacker gets service tickets (TGS) from Kerberos and tries to crack them offline to recover service account passwords. In AS-REP Roasting, the attacker looks for accounts that don’t require pre-authentication and requests TGTs (tickets), which can then be cracked offline to reveal the user's password. Both techniques help attackers steal credentials and move deeper into the network.

#### AS-REP Roasting Attack (Cracking TGT)

![AS-PER](https://github.com/user-attachments/assets/db01514c-171d-4f62-b8bd-68df0badc13a)

AS-REP Roasting is a Kerberos attack where an attacker targets user accounts that don’t require preauthentication. Normally, Kerberos uses preauthentication to protect against password-guessing, but if this protection is turned off for a user, the attacker can simply ask the domain controller for a Ticket Granting Ticket (TGT) for that user. The domain controller sends back an encrypted ticket (AS-REP), which is encrypted using the user’s password hash. The attacker then captures this encrypted ticket and tries to crack it offline to reveal the user's actual password. Once cracked, the attacker can log in as that user and move around the network or escalate privileges if the user has high access.

#### Kerberoasting Attack (Cracking TGS)
Kerberoasting is an attack where a hacker uses a normal user account to request and steal encrypted service tickets, then cracks them offline to get the service account's password.

![Kerberoasting](https://github.com/user-attachments/assets/caa27a38-4c94-4d46-8f97-7296143a98cd)

#### Kerberoasting Methodology
1. At first, the attacker authenticates within the Kerberos network domain using their legitimate user account to obtain a valid ticket granting ticket (TGT).
2. Next, they can use this TGT to request ticket granting service (TGS) tickets for specific service accounts, which are encrypted with the password hash of the respective service account.
3. Once the tickets are issued, attackers can use tools such as Rubeus to extract these TGS tickets from the system memory.
4. After successfully extracting the password hash from the TGS tickets, the attacker can perform an offline brute-force attack using password-cracking tools such as hashcat or John the Ripper.

### Pass-the-Ticket Attack
A Pass-the-Ticket attack is a method where an attacker uses stolen **Kerberos tickets** (instead of a password) to access systems in a network. Normally, users use Kerberos tickets to access services without typing their password every time. In this attack, the attacker dumps tickets like **TGT (Ticket Granting Ticket)** or **ST (Service Ticket)** from the memory of a legitimate user’s computer using tools. Then, the attacker reuses these tickets to pretend to be that user and gain access to services.

If the attacker gets a **Silver Ticket**, they can access a specific service like a file server. If they get a **Golden Ticket**, created using the **KRBTGT hash** from the domain controller, they can act as **any user** in the domain, even as a domain admin. This gives them full control over the network. The attacker doesn’t need the password — just the ticket is enough to move around the system like a legitimate user.

Attackers use tools such as Mimikatz, Rubeus, Windows Credentials Editor, etc. to launch pass-the-ticket attacks: 
- **Mimikatz** 🔗Source: [https://github.com/ParrotSec/mimikatz] - Mimikatz allows attackers to pass Kerberos TGT to other computers and sign in using the victim’s ticket. The tool also helps in extracting plaintext passwords, hashes, PIN codes, and Kerberos tickets from memory. It is an open-source tool that enables anyone to see and store authentication data such as Kerberos tickets. Attackers can leverage this for privilege escalation and credential stealing.

### NTLM Relay Attack
An NTLM Relay Attack is when an attacker intercepts and forwards authentication messages between a user and a server to trick the server into giving access without knowing the user’s password.

#### Steps To Perform an NTLM Relay Attack
1. The attacker first runs Responder on their machine using `./Responder -I eth0`. This makes it listen to and poison LLMNR, NBT-NS, and mDNS traffic, tricking victims into sending NTLM authentication to the attacker.
2. Next, the attacker sets up ntlmrelayx (from the Impacket toolkit) with a command like `impacket-ntlmrelayx.py -of <path_to/SAM-NTLMv2dump file> -tf <path_to/relaytargets> -smb2support`, which tells it to capture the NTLM hashes from incoming sessions and relay them to a target SMB server.
3. When a victim system tries to access a shared folder (SMB share), their NTLM credentials are intercepted and relayed. If the attack is successful, the attacker can dump password hashes (like LM and NTLM) from the victim’s system.

These captured hashes can then be cracked or reused to gain unauthorized access to systems and data.

## Other Active Online Attacks 

- **Combinator Attack** - A Combinator attack is a password-cracking method that tries different combinations of two or more words from a wordlist to guess the correct password.
- **Fingerprint Attack** - A fingerprint attack is a method where an attacker breaks passwords into small letter chunks or patterns to rebuild and crack them more efficiently than guessing whole passwords.
- **Markov-Chain Attack**
- **GPU-based Attack**

## Passive Online Attacks 
- **Wire Sniffing** - Wire sniffing is a way attackers secretly capture and read data (like passwords) traveling over a network without the user knowing.
- **Man-in-the-Middle/Manipulator-in-the-Middle and Replay Attacks** - A Man-in-the-Middle (MITM) attack is when a hacker secretly intercepts and possibly alters the communication between two people or systems without them knowing.

## Offline Attacks
Offline attacks are when an attacker steals password data and tries to crack it on their own computer without interacting with the system.

Two examples of offline attacks are as follows: 
1. **Rainbow table attack** - A rainbow table attack is a hacking method where attackers use a pre-made list of passwords and their hash values to quickly crack encrypted passwords.
    - **Tool to Create Rainbow Tables:**
      - **rtgen** [http://project-rainbowcrack.com] (**Note:** RainbowCrack supports up to Windows 10 only.)
2. **Distributed Network Attack** - A Distributed Network Attack is a method of cracking passwords by using the combined unused power of many computers across a network to speed up the process.

## Password Recovery Tools
Password recovery tools allow attackers to break complex passwords, recover strong encryption keys, and unlock several documents. 
- **Elcomsoft Distributed Password Recovery** [https://www.elcomsoft.com]
- **Passware Kit Forensic** [https://www.passware.com]
- **hashcat** [https://hashcat.net]
- **PCUnlocker** [https://www.top-password.com]
- **Lazesoft Recover My Password** [https://www.lazesoft.com]
- **Passper WinSenior** [https://passper.imyfone.com]

 ## Password-Cracking Tools
Password-cracking tools allow you to reset unknown or lost Windows local administrator, domain administrator, and other user account passwords. In the case of forgotten passwords, it even allows users instant access to their locked computer without reinstalling Windows. Attackers can use password-cracking tools to crack the passwords of the target system. Some password-cracking tools are listed as follows:
- **L0phtCrack** [https://github.com/Brute-f0rce/l0phtcrack]
- **THC-Hydra** [https://github.com/vanhauser-thc/thc-hydra]
- **RainbowCrack** [http://project-rainbowcrack.com]
- **hashID** [https://pypi.org]
- **Patator** [https://github.com/lanjelot/patator]
- **brutus** [https://github.com/exbotanical/brutus]
- **BruteX** [https://github.com/1N3/BruteX/blob/master/README.md]
- **Secure Shell Bruteforcer** [https://pkg.go.dev/github.com/tolgatd/ssh-brute-forcer#section-readme]

## Password Salting 
Password salting is a way to make passwords more secure by adding a random string of characters (called a "salt") to them before they are turned into hashes. This extra randomness makes it much harder for hackers to guess or crack the password, even if they use pre-made lists of common hashes. The longer and more random the salt, the better the protection it gives.

## Tools to Detect LLMNR/NBT-NS Poisoning 
Network administrators and cybersecurity professionals use tools such as Vindicate, got-responded, and Respounder to detect LLMNR/NBT-NS poisoning attacks.
- **Vindicate** [https://github.com/Rushyo/VindicateTool]
- **got-responded** [https://github.com/joda32/got-responded]
- **Respounder** [https://github.com/codeexpress/respounder]

## 💥Vulnerability Exploitation

# 📶 Escalating Privileges

# ♻️ Maintaining Access

# 🧹 Clearing Logs
