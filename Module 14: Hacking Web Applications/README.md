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

