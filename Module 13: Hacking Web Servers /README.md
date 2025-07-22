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
## 
