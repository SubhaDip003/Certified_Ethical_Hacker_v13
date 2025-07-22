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
The Apache web server is an open-source HTTP server used to deliver web content over the Internet. It is widely used owing to its robustness, flexibility, and support for various web technologies. Apache can host websites, handle HTTP requests, and serve both static and dynamic content. It benefits users by providing high performance, security features, extensive customization through modules, and a large support community. These attributes render Apache a popular choice for web hosting and development. <br>
The block diagram of the Apache web server architecture is shown below:

<img width="675" height="193" alt="image" src="https://github.com/user-attachments/assets/4ab2a499-f1cf-42f9-9521-460fe83377eb" />

The functionalities of the various components of the Apache webserver architecture are discussed below: 
- **HTTP Client:** It is a browser or software that initiates requests to the Apache server, asking for web pages, files, or other resources.
- **HTTP Server (Core):** The core module handles HTTP(S) requests and responses, interfacing with modules such as mod_ssl, mod_rewrite, mod_proxy, and mod_auth to provide additional functionalities.
    - **mod_auth:** Manages user authentication, ensuring that only authorized users can access specific web resources based on the configured credentials.
    - **mod_ssl:** Provides SSL/TLS encryption to secure communication between the server and the clients.
    - **mod_rewrite:** Enables URL rewriting, customized URLs, and redirection based on specified rules.
    - **mod_proxy:** Functions as a proxy and gateway, enabling the forwarding of requests to other servers and load balancing.
- BMMTM Extensible Agent: Intercepts HTTP(S) requests and responses to gather detailed transaction data. It enhances monitoring and performance analysis by providing insights into the interactions between clients and servers.
- **Application Server:** Executes backend applications, processes data, and generates dynamic content, functioning separately from the web server that handles the HTTP requests. It is used to run applications written in various programming languages (e.g., PHP, Java, and Python), generating dynamic content that is subsequently served by the Apache web server

### Apache Vulnerabilities 
🔗Source: [https://httpd.apache.org] <br>
The following are some of the common vulnerabilities found in Apache Servers: 

#### HTTP response splitting
- This vulnerability occurs when improperly validated input allows attackers to inject malicious headers into HTTP responses.
- Attackers can leverage this to manipulate web traffic, potentially leading to cross-site scripting (XSS), cache poisoning attacks or sensitive information disclosure.

#### HTTP/2 DoS by memory exhaustion on endless continuation frames
- This vulnerability occurs when attackers send continuous HTTP/2 headers, leading to excessive memory consumption and a potential denial of service (DoS).
- Attackers take advantage of this by exhausting the server's memory, which results in the server becoming unresponsive or crashing

#### mod_macro buffer over-read
- This vulnerability occurs when the mod_macro module improperly handles macro expansion, causing it to read beyond the buffer's end.
- Attackers exploit this by sending specially crafted requests that trigger the over-read, potentially revealing sensitive information stored in adjacent memory locations.

#### DoS in HTTP/2 with initial window size 0
- This vulnerability arises when an attacker sets the HTTP/2 initial window size to 0, which blocks the server from sending data.
- Attackers exploit this by sending requests that set the window size to 0, causing the server to wait indefinitely for window size updates, leading to a denial of service (DoS).

#### HTTP/2 stream memory not reclaimed right away on RST
- This vulnerability occurs when memory allocated for an HTTP/2 stream is not immediately freed upon receiving a stream reset (RST) frame.
- Attackers exploit this by repeatedly creating and resetting streams, causing memory to be consumed without being released, eventually leading to memory exhaustion and a denial of service (DoS).

#### Insecure default configuration
- This vulnerability arises from insecure default admin credentials, leading to remote code execution (RCE).
- Attackers exploit this by using the default credentials to gain admin access and execute arbitrary code.

#### Improper authorization
- This vulnerability arises from improper authorization mechanisms within the server's core components.
- Attackers can leverage this by exploiting the faulty authorization checks to gain unauthorized access or escalate their privileges to access and perform restricted actions.

#### DNS rebinding in import functionality
- This vulnerability occurs because of inadequate input validation in the import functionality of Apache Allura.
- It allows attackers to manipulate DNS responses and access internal services, potentially exposing sensitive information.

#### Environment variable injection
- This vulnerability arises from improper handling of environment variables, allowing attackers to override configurations such Environment variable injection `ZEPPELIN_INTP_CLASSPATH_OVERRIDES` Zeppelin.
- Attackers leverage this by injecting malicious code or commands into these variables, leading to arbitrary code execution on the server.

#### Code injection
- This vulnerability arises when connecting to a MySQL database via the JDBC driver in Apache Zeppelin.
- Attackers can inject sensitive configuration or malicious code during the database connection setup, leading to remote code execution.

#### Improper certificate validation
- This vulnerability arises from improper certificate validation in FTP_TLS connections of Apache Airflow.
- Attackers can leverage this by intercepting or manipulating FTP traffic, potentially leading to man-in-the-middle (MITM) attacks

#### Cross-site scripting (XSS)
- This vulnerability arises due to improper input handling which attackers can leverage to perform cross-site scripting (XSS) attacks by injecting malicious scripts into log entries.
- This vulnerability enables an attacker to insert harmful data into the task instance logs in Apache Airflow.

#### Path-traversal vulnerability
- This vulnerability arises due to improper limitation of pathname to a restricted directory, allowing attackers to access files and directories outside the intended directory in Apache OFBiz.
- Attackers leverage this vulnerability to potentially execute arbitrary code or access sensitive information by navigating to unintended directories.

#### SQL injection
- This vulnerability is caused by improper neutralization of special elements in SQL commands of Apache Submarine Server Core.
- This allows attackers to execute arbitrary SQL queries, leading to unauthorized access, data retrieval, or modification of the database.

---
## IIS Web Server Architecture
Internet Information Services (IIS), a web server application developed by Microsoft, runs on a server and responds to browser requests. It supports HTTP, HTTP Secure (HTTPS), File Transfer Protocol (FTP), FTP Secure (FTPS), Simple Mail Transfer Protocol (SMTP), and Network News Transfer Protocol (NNTP). An IIS application uses HTML to present its user interface and the compiled Visual Basic code to process requests and respond to events in the browser. IIS for Windows is a flexible and easy-to-manage web server for web hosting.

<img width="735" height="396" alt="image" src="https://github.com/user-attachments/assets/2a5e8bf8-f50d-48f1-8a7c-0ee734e7cc93" />

IIS includes the following components:
- Protocol listeners (known as HTTP.sys)
- World Wide Web Publishing Service (known as WWW service)
- Windows Process Activation Service (WAS)

The responsibilities of the IIS components include the following:
- Listening to requests coming from the server
- Managing processes
- Reading configuration files

### How IIS Server Components Function 
- When an HTTP request for a resource is sent from the client browser to the web server, it is intercepted by HTTP.sys.
- HTTP.sys communicates with WAS to collect data from ApplicationHost.config, the root file in the configuration system in the IIS web server.
- WAS raises a request for configuration information, such as that of the site and application pool, to ApplicationHost.config, which is then sent to the WWW Service.
- The WWW Service utilizes the configuration information obtained to configure HTTP.sys
- A worker process is initiated by WAS for the application pool to which the request is intended.
- The request is then processed by the worker, and the response is returned to HTTP.sys.
- The client browser receives a response.

IIS depends mostly on a group of DLLs that work collectively with the main server process (inetinfo.exe), capturing different functions such as content indexing, server-side scripting, and web-based printing. 

### IIS Vulnerabilities 
🔗Source: [https://cve.mitre.org] <br>
The following are some of the vulnerabilities associated with Microsoft IIS servers: 

#### Trust boundary violation vulnerability
- This vulnerability results from inadequate separation of privilege boundaries, allowing an unauthenticated entity to access restricted functionality in the Telerik Report Server.
- Exploiting this flaw may lead to unauthorized server operations manipulation.

#### Authentication bypass vulnerability
- It occurs due to specific issues in the implementation of the authentication process where an insecure endpoint allows unauthenticated access to restricted server functionality.
- Attackers can leverage this vulnerability to circumvent authentication and execute arbitrary code on the server.

#### CRLF cross-site scripting vulnerability
- This vulnerability arises due to certain misconfigurations in the SiteMinder Web Agent for IIS Web Server.
- Attackers can execute arbitrary JavaScript code in a client’s browser by exploiting this vulnerability.

#### CCURE passwords exposed to administrators
- This vulnerability arises due to improper handling and logging of sensitive information within the Microsoft Internet Information Server (IIS) while hosting the C•CURE 9000 Web Server.
- Attackers can exploit this vulnerability and access these logs to retrieve sensitive Windows credentials.

#### Arbitrary file path access vulnerability
- This vulnerability occurs due to the default configuration of the Aquaforest TIFF Server, which improperly restricts access to file paths.
- Attackers can exploit this vulnerability to access, enumerate, or traverse directories and files, potentially bypassing authentication or accessing restricted files.

#### Windows IIS server elevation of privilege vulnerability
- This vulnerability occurs due to the server’s improper handling of specific user requests in Windows IIS server.
- Attackers can leverage this vulnerability to obtain unauthorized access and take control of the system.

#### File and directory permissions vulnerability
- This vulnerability arises due to incorrect default permissions in the Hitachi JP1/Performance Management software on Windows.
- Attackers can leverage this vulnerability to manipulate files and directories unauthorizedly

#### TYPO3 cross-site scripting (XSS) vulnerability
- This vulnerability occurs due to unfiltered use of the server environment variable PATH_INFO in the GeneralUtility::getIndpEnv() component of the TYPO3 Content Management Framework.
- Attackers exploit this vulnerability by injecting malicious HTML code into uncached pages, potentially affecting other visitors

#### MailEnable vulnerability
- This vulnerability occurs due to improper handling of file paths in certain conditions.
- This vulnerability allows authenticated mail users to add files with unsanitized content in public folders where the IIS user has permission to access, potentially leading to arbitrary code execution.

#### XSS in password manager
- This vulnerability occurs due to the improper neutralization of user-controllable input within the /isapi/PasswordManager.dll ResultURL parameter.
- Attackers can exploit this vulnerability to inject malicious scripts and steal sensitive information. 

---
## Nginx Web Server Architecture
Nginx is a high-performance scalable web server, reverse proxy, and load balancer that operates on a master-worker architecture. It employs a single-threaded, event-driven, asynchronous, and non-blocking model to efficiently manage multiple connections. The core of Nginx's architecture comprises a master process that oversees various worker processes responsible for handling client requests. <br>
This modular architecture allows extensive customization through various HTTP, streams, mail, and third-party modules. Nginx supports advanced load balancing, robust caching, SSL/TLS termination, and detailed logging. Its security features, including access control, authentication, and rate-limiting, make it suitable for high-traffic and mission-critical applications.

<img width="519" height="350" alt="image" src="https://github.com/user-attachments/assets/504f6741-e3b6-4db8-900a-4b84c9b6e804" />

The various components of the Nginx architecture are discussed below: 
1. **Master Process** - 
   Controls and manages worker processes, reads config files, and handles sockets.

2. **Worker Processes** - 
   Handle client requests using non-blocking I/O, allowing thousands of connections at once.

3. **Proxy Cache** - 
   Stores copies of web content to serve it faster and reduce backend load.

   * **Cache Loader** - 
     Loads cache info into memory during startup so content is ready quickly.

   * **Cache Manager** - 
     Deletes expired or unused cache data to save space and keep cache fresh.

4. **Web Server** - 
   Handles HTTP requests, serves static files, and passes dynamic requests to app servers.

5. **Application Server** - 
   Runs backend scripts or apps to deliver dynamic content to the client.

6. **Memcache** - 
   Stores data in RAM for fast access, reducing database load and speeding up performance.

### Nginx Vulnerabilities 
🔗Source: [https://cve.mitre.org] <br>
Some of the common vulnerabilities found in Nginx servers are discussed below: 

#### NULL pointer dereference in HTTP/3
- This vulnerability occurs due to a NULL pointer dereference in Nginx's QUIC module when handling HTTP/3 requests, causing worker processes to terminate.
- Attackers can trigger this flaw by sending crafted requests to a vulnerable Nginx server, causing denial of service or potential remote code execution.

#### Server-side request forgery (SSRF) vulnerability
- This vulnerability occurs due to Server-side request forgery (SSRF) in the upload link feature of mintplex-labs/anything-llm.
- Attackers can exploit this vulnerability by hosting a malicious website, allowing them to perform internal port scanning, access non-public web applications, execute arbitrary file deletion, and carry out local file inclusion.

#### Remote code execution vulnerability
- This vulnerability arises due to the exposed configuration settings via Nginx-UI.
- Attackers can exploit this vulnerability to perform remote code execution, privilege escalation, or information disclosure.

#### Improper certificate validation
- This vulnerability occurs due to the improper validation of user input in the Import Certificate feature of Nginx-UI.
- Attackers can exploit this vulnerability to perform arbitrary file writes

#### SQL injection vulnerability
- This vulnerability occurs due to improper neutralization of special SQL elements, allowing unsanitized user-controlled parameters to be appended to queries.
- Attackers can exploit this vulnerability to execute arbitrary SQL queries for unauthorized access or data breaches.

#### Unauthenticated private keys access
- This vulnerability occurs due to the reliance on .htaccess for security, which fails on Nginx servers that do not support .htaccess files.
- Attackers can exploit this vulnerability to read private keys by accessing the site on a server that does not support .htaccess files.

#### Excessive memory usage and CPU exhaustion in HTTP/2
- This vulnerability arises from improper memory handling and excessive CPU usage in HTTP/2 requests.
- By exploiting this vulnerability, attackers flood the server with HTTP/2 requests to consume server memory and CPU, disrupting normal operations.

#### OS command injection in nginxWebUI
- This vulnerability occurs due to improper handling of file arguments in the upload feature.
- Attackers exploit this vulnerability to manipulate file arguments to inject and execute OS commands remotely on the server.

#### Default file permissions vulnerability
- This vulnerability occurs because the Nginx Management Suite sets default file permissions that allow authenticated modification of sensitive files.
- Attackers leverage this vulnerability to modify sensitive files on the Nginx Instance Manager and Nginx API Connectivity Manager.
