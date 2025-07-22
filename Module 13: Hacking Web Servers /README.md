# 🌐🖥️ Web Server Concepts
To understand web server hacking, it is essential to understand web server concepts, including what a web server is, how it functions, and other elements associated with it. <br>
This section provides a brief overview of a web server and its architecture. It will also explain common factors or mistakes that allow attackers to hack a web server. This section also describes the impact of attacks on web servers. 

---
## Web Server Operations 
A **web server** is a computer that delivers websites, images, or videos to users through the internet using **HTTP**. When a user opens a website, their browser sends an HTTP request to the web server. The server then fetches the requested content and sends it back. If the content isn't found, it returns an error message.

<img width="523" height="383" alt="image" src="https://github.com/user-attachments/assets/deff2981-caa9-4404-9e80-75d80d60f881" />

### Components of a Web Server 
A web server consists of the following components: 

#### Document Root 
The **document root** is the main folder on a web server where a website's HTML files are stored. When someone visits a website, the server looks in this folder to find and send the correct page. For example, if the site is `www.certifiedhacker.com` and the document root is `/admin/web/certroot`, then a request to `www.certifiedhacker.com/P-folio/index.html` will fetch the file from `/admin/web/certroot/P-folio/index.html`.

#### Server Root
The server root is the top-level directory in the directory tree, where the server configuration files, log files, and executable files are stored. This is the root directory for the web server configuration. Typically, it contains several sub-directories:
- **conf:** This directory holds the server's configuration files.
- **logs:** This directory stores server log files, including access and error logs.
- **cgi-bin:** This directory is where common gateway interface (CGI) scripts or other server-side executables are located.

The server root may also contain other directories or files depending on the specific server software and its configuration.

#### Virtual Document Tree
A virtual document tree provides storage on a different machine or disk after the original disk becomes full. It is case-sensitive and can be used to provide object-level security. <br>
In the above example under document root, for a request of `www.certifiedhacker.com/P-folio/index.html`, the server can also search for the file path `/admin/web/certroot/P-folio/index.html` if the directory `admin/web/certroot` is stored in another disk.

#### Virtual Hosting
It is a technique of hosting multiple domains or websites on the same server. This technique allows the sharing of resources among various servers. It is employed in large-scale companies, in which company resources are intended to be accessed and managed globally. <br>
The following are the types of virtual hosting:
- Name-based hosting
- Internet Protocol (IP)-based hosting
- Port-based hosting

#### Web Proxy 
**Web Proxy** acts as a middleman between a user and a website. It forwards user requests to the web server, helping to hide the user’s IP address. This keeps the user anonymous and helps avoid IP blocking by websites.

---
## Web Server Security Issues 
A **web server** is a system (hardware or software) that stores and delivers website content over the internet. It works on a client–server model, where the browser is the client and the web server is the server. Web servers like Apache, Nginx, IIS, and Tomcat can host one or more websites and must be connected to the internet with the right software.

Attackers often target **vulnerabilities** in server software or **misconfigurations** to hack into web servers. So, it's important to keep web servers properly configured and secure.

<img width="691" height="252" alt="image" src="https://github.com/user-attachments/assets/a8fb1c22-1271-4d36-9843-e3588e4a6aca" />

Web servers are common targets for attackers because they are open to the internet. Even if a network is protected by firewalls, IDS, or IPS, a poorly configured web server can create security gaps. Attackers exploit these misconfigurations and known vulnerabilities to break into web applications, risking the entire organization’s security. Proper configuration and regular updates are crucial to keep web servers secure. As shown in the below figure, organizational security includes seven levels from stack 1 to stack 7.

<img width="609" height="268" alt="image" src="https://github.com/user-attachments/assets/13c68f4a-ca9c-41b6-9e62-dec2df87d891" />

### Common Goals behind Web Server Hacking
**Common Goals Behind Web Server Hacking:**
Attackers hack web servers for various reasons—some for money, others out of curiosity or challenge. Common goals include:

* **Stealing sensitive data** like credit card info via phishing
* **Using the server in botnets** for DDoS attacks
* **Accessing or damaging databases**
* **Getting secret software (closed-source apps)**
* **Redirecting traffic or hiding malicious activity**
* **Gaining higher-level access (privilege escalation)**
  Sometimes, attacks are done just for fun, curiosity, or to harm a company’s image.

### Dangerous Security Flaws Affecting Web Server Security
A web server configured by poorly trained system administrators may have security vulnerabilities. Inadequate knowledge, negligence, laziness, and inattentiveness toward security can pose the greatest threats to web server security.<br>
The following are some common oversights that make a web server vulnerable to attacks: 
- Failing to update the web server with the latest patches
- Using the same system administrator credentials everywhere 
- Allowing unrestricted internal and outbound traffic 
- Running unhardened applications and servers 
- Providing complete error messages with server version information 
- Using outdated SSL/TLS encryption algorithms 
- Using third-party plugins in the web application

### Impact of Web Server Attacks 
Attackers can cause various kinds of damage to an organization by attacking a web server. The following are some of the types of damage that attackers can cause to a web server. 
1. **Compromise of User Accounts** - 
   Attackers can hack user accounts and steal sensitive information or use them for more attacks.

2. **Website Defacement** - 
   Hackers can change the website’s look and content to display their own messages.

3. **Launching Secondary Attacks** - 
   A hacked web server can be used to attack other websites or user devices.

4. **Root Access to Server** - 
   If attackers get root access, they can fully control the server and do anything they want.

5. **Data Tampering** - 
   Hackers can change, delete, or replace the server’s data—sometimes even add malware.

6. **Data Theft** - 
   They can steal sensitive data like financial info, business plans, or code.

7. **Reputation Damage** - 
   If customer data is leaked, people lose trust in the company, harming its reputation.

---
## Why are Web Servers Compromised? 
Web servers are often targeted because they connect internal networks (LANs) to the internet, exposing them to risks like malware, bugs, or hacker attacks.

* **Webmaster's View**: Bugs in server software and insecure scripts (like CGI) can create security holes.
* **Network Admin's View**: Poorly configured servers can weaken LAN security or block legit access if too strict.
* **End User's View**: Users may unknowingly allow threats like malware through risky content (JavaScript, WebAssembly) in websites, bypassing firewalls and harming their systems.

The following are some oversights that can compromise a web server:
- Improper file and directory permissions
- Installing the server with default settings
- Unnecessary services enabled, including content management and remote administration
- Security conflicts with the business’ ease-of-use requirements
- Lack of proper security policy, procedures, and maintenance
- Improper authentication with external systems
- Default accounts with default or no passwords
- Unnecessary default, backup, or sample files
- Misconfigurations in the web server, OS, and networks
- Bugs in server software, OS, and web applications
- Misconfigured Secure Sockets Layer (SSL) certificates and encryption settings
- Administrative or debugging functions that are enabled or accessible on web servers
- Use of self-signed certificates and default certificates
- Not using dedicated server for web services
- Granting excessive privileges to users or processes, or failing to implement the principle of least privilege.

---
## Apache Web Server Architecture 
