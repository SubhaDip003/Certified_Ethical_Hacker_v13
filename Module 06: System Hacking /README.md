# 🖥️ System Hacking
System hacking is the process of gaining unauthorized access to computer systems to steal data, control the system, or cause damage. Ethical hackers and penetration testers perform system hacking in a legal and controlled way to find weaknesses before real attackers do. This helps organizations fix security issues and protect their systems from being hacked by malicious users.

# 🔑 Gaining Access
Gaining access in system hacking means breaking into a computer or system by using stolen passwords, exploiting software bugs, or tricking users. The goal is to take control of the system so the hacker can view, change, or steal data. It's one of the key steps in hacking after finding system weaknesses.

## Cracking Passwords
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

## 🔐 Types of Password Attacks

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
## 🔐 **Active Online Attacks**

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



# 📶 Escalating Privileges

# ♻️ Maintaining Access

# 🧹 Clearing Logs
