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
