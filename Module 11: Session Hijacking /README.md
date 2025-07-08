# 🔐 Session Hijacking
**Session Hijacking** is a cyberattack where an attacker takes control of an active communication session between a user and a server. After a user logs in, the server gives them a **session ID** to keep the connection active. If an attacker **steals or guesses** this session ID, they can trick the server into thinking they are the real user.

Since authentication happens only at the start of the session, the attacker can **access the system without logging in**, steal sensitive data, perform fraud, or impersonate the user. This can lead to attacks like **Man-in-the-Middle (MITM)**—where the attacker secretly relays or alters communication—and **Denial-of-Service (DoS)** by disrupting the session.

![image](https://github.com/user-attachments/assets/8e80a0c1-9c40-43ac-829d-f6617070cdbc)

---
## Why is Session Hijacking Successful? 
Session hijacking succeeds because of the following factors. 

1. **No Account Lockout for Invalid Sessions** - 
   If a website doesn’t block repeated invalid session ID attempts, attackers can **brute-force** the valid session ID without alerting the system.

2. **Weak or Predictable Session ID Generation** - 
   If session IDs are created using **simple or linear algorithms**, attackers can predict them by analyzing patterns. Short session IDs make it easier.

3. **Insecure Session ID Storage or Transmission** - 
   If session IDs are not handled securely, attackers can steal them using **DNS spoofing, XSS**, or browser bugs before the session expires.

4. **No Session Timeout** - 
   Without a timeout, sessions stay active too long. Attackers can steal session cookies from features like **"Remember Me"** and use them indefinitely.

5. **Vulnerable TCP/IP Protocol** - 
   Since **TCP/IP lacks built-in session security**, attackers can hijack sessions on most devices using these protocols.

6. **Lack of Encryption** - 
   If data is sent without proper **SSL/TLS encryption**, attackers can **sniff** session IDs from network traffic — even if some protections are in place.

---
## Session Hijacking Process
**Session Hijacking** is a technique where an attacker takes over a user’s active session after the user has logged in. Instead of breaking in directly, the attacker waits for a valid session to be created, then hijacks it to act as the real user. Once in control, the attacker can stay connected without raising suspicion, redirect traffic meant for the user, install backdoors, and gain deeper access to the system—all while appearing legitimate.

![image](https://github.com/user-attachments/assets/219b1a1a-52b4-4ffe-9606-14dba8ca5df7)

Session hijacking can be divided into three broad phases. 

### 🔹 1. Tracking the Connection
The attacker uses tools like **network sniffers** or **Nmap** to watch traffic and find a target.
They capture important TCP values like **sequence numbers** and **acknowledgment numbers**.
These values help the attacker build fake packets that look real to the server or client.

### 🔹 2. Desynchronizing the Connection
The attacker **breaks the sync** between the target and the server.
They do this by sending:
* **Null data** to update the server's sequence number.
* Or **RST (Reset)** or **SYN packets** to close the old connection and open a new one.

This tricks the server into thinking it's still talking to the target, even though it's now communicating with the attacker.
If done wrong, it can create **ACK storms** (endless network replies), which can expose the attack.

### 🔹 3. Injecting the Attacker’s Packet
Now that the connection is hijacked, the attacker can:
* **Inject fake data** into the conversation.
* Or act as a **man-in-the-middle**, watching and changing the communication between the target and the server.

---
## Packet Analysis of a Local Session Hijack 
**Local Session Hijacking** is a type of attack where the hacker takes control of a network session by exploiting the **TCP three-way handshake** process. It starts with the attacker **tracking the session** by sniffing network traffic. Then, they **desynchronize** the connection by predicting or capturing the **next sequence number (NSN)**. Once they have the correct sequence number, the attacker **injects commands** into the session before the real user does.

If the attacker is on the same network and can sniff TCP packets, it becomes easy to hijack the session accurately. This method is especially dangerous in local networks, where monitoring traffic is simpler.

---
## Types of Session Hijacking 
**Session Hijacking** comes in two types: **active** and **passive**. In **active hijacking**, the attacker takes full control of an ongoing session between a user and a system. In **passive hijacking**, the attacker only monitors the session without interfering, mainly to steal information. The key difference is that active attacks take over the session, while passive ones just watch silently.

### Passive Session Hijacking
**Passive Session Hijacking** is a silent attack where the hacker doesn’t interfere but quietly watches a user’s session. By using network sniffers, the attacker captures sensitive data like **usernames and passwords**. Later, they use this information to log in as the real user and gain access.

This type of attack is simple and dangerous, especially if the data isn't encrypted. Defense methods like **one-time passwords (S/KEY)** and **Kerberos** help protect against sniffing, but they don’t stop active attacks if the data isn’t secured properly.

### Active Session Hijacking
**Active Session Hijacking** is when an attacker takes control of an ongoing session between two users, usually by breaking one side of the connection or secretly joining the conversation. A common example is a **Man-in-the-Middle (MITM)** attack, where the attacker tries to predict session sequence numbers to intercept the connection. However, modern systems make this harder by using **random sequence numbers**, which helps protect against such attacks.

---
## Session Hijacking in OSI Model 
There are two levels of session hijacking in the OSI model: the network-level and application-level. 

### Network-Level Hijacking
This happens at the **network layer**, where an attacker **intercepts data packets** being transmitted between a client and a server (like in a TCP or UDP session).
The attacker doesn't need to know how each web app works — they just focus on capturing and using the **protocol data** to spy or hijack the connection.

### Application-Level Hijacking
This occurs at the **application layer**, especially in **web sessions using HTTP**.
The attacker **steals session IDs** (like cookies or tokens) to take control of a user’s session or create fake sessions to gain access to restricted features or data.

> In many real-world attacks, **both types can happen together** to maximize control and damage.

---
## **Spoofing vs. Hijacking**

**Spoofing** is when an attacker pretends to be another user or system to start a fake session—usually by faking an IP address. It’s used to trick systems into thinking the attacker is trusted. In **IP spoofing**, attackers don’t take over an active session but create a new one using fake credentials or addresses.

**Session hijacking**, on the other hand, is when the attacker takes over an **already active session** between a user and a service. This often involves guessing TCP **sequence numbers** to sync with the session and act like the legitimate user. In **blind hijacking**, the attacker can’t see the responses but sends commands anyway by predicting sequence numbers.

Hijacking is harder because it needs more control—like knowing the session’s status, sequence numbers, or displacing the real user. Both spoofing and hijacking fail if **encryption**, **packet integrity checks**, or secure protocols like **SSL** are used, since they protect session data and identity from being tampered with.
