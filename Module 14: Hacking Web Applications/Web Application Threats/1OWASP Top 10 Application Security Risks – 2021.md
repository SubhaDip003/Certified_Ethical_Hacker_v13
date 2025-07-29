# 🚨 Web Application Threats
Attackers attempt various application-level attacks to compromise the security of web applications to commit fraud or steal sensitive information. This section discusses the various types of threats and attacks against the vulnerabilities of web applications. 

# 🐝 OWASP Top 10 Application Security Risks – 2021 
🔗Source: [https://owasp.org] <br>
OWASP is an international organization that maintains a list of the top 10 vulnerabilities and flaws of web applications. The latest OWASP top 10 application security risks are as follows. 
1. **A01 – Broken Access Control** →
   This happens when users can access things they shouldn’t, like someone else’s account or admin features. Example: changing a URL to view another user’s data.

2. **A02 – Cryptographic Failures** →
   This is when sensitive data (like passwords or credit card info) isn’t properly encrypted. If it's sent in plain text or uses weak encryption, attackers can steal it.

3. **A03 – Injection** →
   When an application accepts untrusted input and runs it as code. Attackers can use this to run malicious commands. Example: SQL Injection lets them steal or change data.

4. **A04 – Insecure Design** →
   Flaws in how an app is planned or designed, like missing security checks. It leads to attacks like CAPTCHA bypass or session hijacking.

5. **A05 – Security Misconfiguration** →
   This happens when systems are not properly set up. Using default passwords, showing error messages with too much info, or not updating software can make apps easy to hack.

6. **A06 – Vulnerable and Outdated Components** →
   Using old software parts (like plugins, libraries, etc.) with known bugs lets attackers exploit them. These weak parts often run with full access and can lead to data theft.

7. **A07 – Identification and Authentication Failures** →
   Weak login systems can be bypassed. Attackers may guess passwords or hijack sessions if tokens and credentials aren't protected properly.

8. **A08 – Software and Data Integrity Failures** →
   If software updates or data are not verified properly, attackers can inject malware. For example, insecure auto-update features or untrusted plugins.

9. **A09 – Security Logging and Monitoring Failures** →
   If the app doesn’t log activities or alert about unusual actions (like failed logins), attacks can go unnoticed. This gives hackers more time to do damage.

10. **A10 – Server-Side Request Forgery (SSRF)** →
    When an app fetches a URL without checking if it's safe, attackers can use it to access internal systems behind firewalls or steal sensitive info.

---
## 
