# 🌐 Web Application Concepts
Web applications are software programs that run in web browsers and connect users to servers over the Internet. They let users perform tasks like searching, emailing, shopping, or accessing services by interacting with a graphical user interface (GUI). These applications use languages like HTML, CSS, and JavaScript on the browser side, and SQL or server-side scripts to interact with databases.

Users access web applications by entering a URL or URI in a browser, which sends a request to a server. The server then sends back the requested content to the browser. Popular web servers include Apache, Microsoft IIS, LiteSpeed, and others.

Web applications are widely used because they are secure, easy to develop and maintain, and offer better services than many desktop applications. Their growing use supports online businesses and services across the globe.

The advantages of web applications are listed below: 
1. **Cross-platform** → Works on any operating system, making development and fixing issues easier and cheaper.
2. **Accessible Anywhere** → Can be used anytime from any device with an internet connection.
3. **Customizable Interface** → Easy to update the user interface as per user needs.
4. **Device Independent** → Runs on smartphones, tablets, and any device with a browser.
5. **Centralized Data Storage** → Data is stored on secure servers managed by experts, improving reliability.
6. **Improved Security & Monitoring** → Servers in multiple locations boost security and reduce the need to monitor many desktops.
7. **Scalable Technologies** → Built with flexible and scalable tech like JSP, .NET, and SQL, which support various platforms.

---
## How Web Applications Work
The main function of web applications is to fetch user-requested data from a database. When a user clicks or enters a URL in a browser, the web application immediately displays the requested website content in the browser.


This mechanism involves the following steps: 
1. **User Request** → A user enters a website URL in the browser.
2. **Request to Web Server** → The browser sends this request to the web server.
3. **Web Page Type Check** →
   * If it’s a basic page (`.html`, `.htm`), the web server sends it directly to the browser.
   * If it's a dynamic page (`.php`, `.asp`, `.cfm`), the request goes to the web application server.
4. **Application Server Processing** → The web app server handles the request, often needing data from a database.
5. **Database Access** → The application server fetches or updates data in the database as needed.
6. **Response Back to User** → The processed result goes to the web server, which then delivers it to the user’s browser.

<img width="620" height="243" alt="image" src="https://github.com/user-attachments/assets/3c96aead-2ecc-499e-89d6-eabe35f5f499" />

---
## Web Application Architecture 
Web applications run on web browsers and use a set of server-side scripts (Java, C#, Ruby, PHP, etc.) and client-side scripts (HTML, JavaScript, etc.) to execute the application. <br>
**Web Application Architecture** refers to how a web application is structured and works behind the scenes. It involves both **client-side** and **server-side** components that handle user requests and deliver responses.

It is made up of **three main layers**:

1. **Client/Presentation Layer**:
   This is what the user sees and interacts with (browsers on devices like phones or laptops). When a user types a URL, a request goes to the web server, which then sends back the requested data (usually as a web page).

2. **Business Logic Layer**:
   This layer handles how the application functions. It has two parts:

   * **Web-server logic layer**: Handles tasks like request processing, security (firewall), caching, and user authentication. Servers like Apache or IIS are used here.
   * **Business logic layer**: Contains the code (using Java, .NET, etc.) that controls how data flows and how the application should respond based on user actions.

3. **Database Layer**:
   This layer stores all the application data, including transactions and user information. It uses servers like MySQL or MS SQL, and may involve cloud storage or external services.

In short, the web application architecture connects users, code, and data — ensuring requests are processed properly and users get the correct content.

<img width="750" height="411" alt="image" src="https://github.com/user-attachments/assets/bad1bde2-e9fc-45e3-bd1b-4575e15cbd2c" />

---
## Web Services 
A web service is an application or software that is deployed over the Internet. It uses a standard messaging protocol (such as SOAP) to enable communication between applications developed on different platforms. For instance, Java-based services can interact with PHP applications. These web-based applications are integrated with SOAP, UDDI, WSDL, and REST across the network.

### Web Service Architecture
Web service architecture shows how three parts work together: **service provider**, **service requester**, and **service registry**.

* The **provider** creates and shares (publishes) service details in the **registry**.
* The **requester** searches (finds) the needed service in the registry.
* Then, the requester connects (binds) to the **provider** to use the service.

These steps—**publish**, **find**, and **bind**—help systems communicate and use web services easily.

There are three roles in a web service:
- **Service Provider:** It is a platform from where services are provided.
- **Service Requester:** It is an application or client that is seeking a service or trying to establish communication with a service. In general, the browser is a requester, which invokes the service on behalf of a user.
- **Service Registry:** It is the place where the provider loads service descriptions. The service requester discovers the service and retrieves binding data from the service descriptions.

There are three operations in a web service architecture: 
1. **Publish** → The service provider shares details about their service so others can find and use it.
2. **Find** → The user (requester) searches for and retrieves the service details—first during development, and again at run-time to get connection info.
3. **Bind** → The user connects to and uses the service in real-time using the information gathered from the find step.

There are two artifacts in a web service architecture:
- **Service:** It is a software module offered by the service provider over the Internet. It communicates with the requesters. At times, it can also serve as a requester, invoking other services in its implementation.
- **Service Description:** It provides interface details and service implementation details. It consists of all the operations, network locations, binding details, datatypes, etc. It can be stored in a registry and invoked by the requester.

<img width="568" height="274" alt="image" src="https://github.com/user-attachments/assets/6b8dfd61-122d-42e6-a79c-3fc482913baf" />

### Characteristics of Web Services 
1. **XML-Based** → Web services use XML to share data, making them work across any OS or platform.
2. **Coarse-Grained Services** → They provide large, useful functions by combining smaller services into one.
3. **Loosely Coupled** → Systems connect through web APIs with XML messages, allowing flexibility and easy updates.
4. **Synchronous & Asynchronous Support** → They can respond immediately (sync) or later (async) depending on the user’s need.
5. **RPC Support** → They allow remote procedure calls like traditional apps, letting systems run functions on other machines.

These traits make web services **interoperable, flexible, and scalable** across different platforms.

### Types of Web Services 
Web services are of two types: 
- **SOAP web services** - The Simple Object Access Protocol (SOAP) defines the XML format. XML is used to transfer data between the service provider and the requester. It also determines the procedure to build web services and enables data exchange between different programming languages.
- **RESTful web services** - REpresentational State Transfer (RESTful) web services are designed to make the services more productive. They use many underlying HTTP concepts to define the services. It is an architectural approach rather than a protocol like SOAP.

### Components of Web Service Architecture: 
- **UDDI:** Universal Description, Discovery, and Integration (UDDI) is a directory service that lists all the services available.
- **WSDL:** Web Services Description Language is an XML-based language that describes and traces web services.
- **WS-Security:** Web Services Security (WS-Security) plays an important role in securing web services. It is an extension of SOAP and aims to maintain the integrity and confidentiality of SOAP messages as well as to authenticate users.

There are other important features/components of the web service architecture, such as WS-Work Processes, WS-Policy, and WS Security Policy, which play an important role in communication between applications.

---
## Vulnerability Stack 
The **Vulnerability Stack** refers to the different layers involved in running a web application—like custom code, third-party components, databases, web servers, OS, network, and security tools. Each layer plays a role in secure access but can also introduce vulnerabilities. Organizations must secure **all layers**, as web applications are common targets for attackers.

<img width="747" height="287" alt="image" src="https://github.com/user-attachments/assets/39501cb1-7e94-40fd-aee0-56dbe799682a" />

Attackers exploit the vulnerabilities of one or more elements among the seven levels to gain unrestricted access to an application or the entire network. 

🔹 **Layer 7 – Web Applications:** Attackers exploit business logic flaws (e.g., XSS) in custom apps built with Java/.NET.

🔹 **Layer 6 – Third-Party Components:** Attackers use insecure third-party services (e.g., payment gateways) to enter the main site.

🔹 **Layer 5 – Web Server:** They gather server info (via Nmap/banner grabbing) and exploit known CVEs.

🔹 **Layer 4 – Database:** They use tools like **sqlmap** to exploit DB flaws and steal sensitive data.

🔹 **Layer 3 – Operating System:** Attackers find open ports and send malware/backdoors to gain full access.

🔹 **Layer 2 – Network (Router/Switch):** They flood switches to sniff internal traffic like passwords and user data.

🔹 **Layer 1 – Security Devices (IDS/IPS):** They use evasion techniques to bypass security alerts and stay hidden.
