# 🛡️ Web Application Security
After learning the hacking methodologies adopted by attackers of web applications and the tools they use, it is important to learn how to secure these applications from such attacks. A careful analysis of security will help you, as an ethical hacker, to secure your applications. To do so, one should design, develop, and configure web applications using the countermeasures and techniques discussed in this section. 

---
## Web Application Security Testing 
Web application security testing is the process of assessing an application to identify vulnerabilities, measure its resistance to threats, and evaluate overall performance under potential attacks. It is carried out by security professionals and developers to detect weaknesses early, generate reports, and apply fixes to strengthen the application’s security.

### Manual Web Application Security Testing
Manual web application security testing is the process of checking a web application by using custom test data, code, and tools to find vulnerabilities. Unlike automated scans, it focuses on business logic flaws and detailed threat analysis. Tools like SecApps, Selenium, JMeter, LoadRunner, QTP, Bugzilla, and Acunetix are often used to support this testing.

### Automated Web Application Security Testing 
Automated web application security testing uses specialized tools to quickly detect vulnerabilities during development. These tools are integrated into each stage of the process, continuously analyzing code changes and alerting developers to security issues. This ensures faster fixes and stronger protection, with tools like Ranorex Studio, TestComplete, Leapwork, Katalon Studio, and Testsigma commonly used for such testing.

### Static Application Security Testing (SAST) 
Static Application Security Testing (SAST), also known as white-box testing, analyzes an application’s source code to find security flaws before it is run. It helps developers identify vulnerabilities, check compliance with coding standards, and fix issues early in the development cycle. Tools like Codacy, JFrog, Klocwork, Checkmarx One, and PT Application Inspector are commonly used for SAST.

> Check more about SAST [here](https://medium.com/@subhadipsardar866/web-application-security-static-application-security-testing-sast-2c6204caf42b)

### Dynamic Application Security Testing (DAST) 
Dynamic Application Security Testing (DAST) is a black-box testing method where the application is tested from the outside without knowing its internal structure. It analyzes running code to find vulnerabilities in areas like authentication, sessions, inputs, and scripts. DAST tools also use fuzzing by sending unexpected inputs to detect flaws. Common tools for DAST include Invicti, Acunetix, HCL AppScan, Fortify On Demand, and StackHawk.

> Check more about DAST [here](https://medium.com/@subhadipsardar866/web-application-security-dynamic-application-security-testing-dast-13765723c3a6)

---
## Web Application Fuzz Testing 
Web application fuzz testing is a black-box testing method used to find coding errors and security flaws by sending large amounts of random data, called fuzz, to the application. This helps uncover vulnerabilities like buffer overflows, XSS, SQL injection, and DoS. While attackers use fuzzing to crash applications, developers and security teams use it to test the strength and reliability of web applications against such attacks.

### Steps of Fuzz Testing 
Web application fuzz testing involves the following steps:
- Identify the target system
- Identify inputs
- Generate fuzzed data
- Execute the test using fuzz data
- Monitor system behavior
- Log defects

### Fuzz Testing Strategies 
- **Mutation-Based:** In this type of testing, the current data samples create new test data, and the new test data will again mutate to generate further random data. This type of testing starts with a valid sample and keeps mutating until the target is reached.
- **Generation-Based:** In this type of testing, the new data will be generated from scratch, and the amount of data to be generated is predefined based on the testing model
- **Protocol-Based:** In this type of testing, the protocol fuzzer sends forged packets to the target application that is to be tested. This type of testing requires detailed knowledge of the protocol format being tested. It involves writing a list of specifications into the fuzzer tool and then performing the model-based test generation technique to go through all the listed specifications and add the irregularities in the data contents, sequence, etc.

### Fuzz Testing Scenario
The diagram below shows an overview of the main components of the fuzzer. An attacker script is fed to the fuzzer, which in turn translates the attacks to the target as http requests. These http requests will get responses from the target and all the requests and their responses are then logged for manual inspection.

<p align="center">
  <img width="826" height="224" alt="image" src="https://github.com/user-attachments/assets/6042425e-b606-4a20-8c26-f4b41c4eec0f" />
</p>

### Fuzz Testing Tools:
- **WebScarab** [https://owasp.org]
- **Burp Suite** [https://portswigger.net]
- **AppScan Standard** [https://www.hcl-software.com]
- **Defensics** [https://www.synopsys.com]
- **ffuf** [https://github.com/ffuf/ffuf]

---
## Web Application Fuzz Testing with AI 
An attacker can also use ChatGPT to perform this task by using an appropriate prompt such as: 
- `“Fuzz the target url www.moviescope.com using Wfuzz tool”`
  <p align="center">
    <img width="660" height="427" alt="image" src="https://github.com/user-attachments/assets/ad40e613-978f-4204-b7b6-4b331c385baf" />
  </p>

---
## AI-Powered Fuzz Testing 
AI-powered fuzz testing represents a significant advancement in automated vulnerability discovery compared to traditional fuzzing methods. Key features of AI-powered fuzz testing include the following: 
1. **Automated Crafting of Complex Inputs** → AI uses smart algorithms to create test inputs that are more likely to trigger hidden bugs, instead of relying on random data.
2. **Pattern Recognition and Effective Input Prediction** → AI studies how software reacts to past tests, then predicts and sends inputs that have a higher chance of finding serious issues.
3. **Continuous Learning and Real-time Feedback** → AI learns as it tests, improving its strategy in real time to dig deeper and uncover vulnerabilities missed by manual methods.
4. **Enhanced Testing Efficiency and Coverage** → AI focuses on risky parts of the code, saving time, improving coverage, and increasing the chances of finding bugs compared to traditional fuzzing.

### AI-Powered Fuzz Testing Tool: Prompt Fuzzer 
🔗Source [https://github.com/prompt-security/ps-fuzz] <br>
Prompt Fuzzer is an AI-powered fuzz testing tool for GenAI applications that helps identify and fix security issues in system prompts. It simulates attacks like prompt injection, analyzes responses with LLMs, and assigns security scores. By testing prompts in an interactive way, it helps ethical hackers detect critical vulnerabilities, improve prompt defenses, and strengthen overall security in GenAI systems.

<p align="center">
  <img width="761" height="366" alt="image" src="https://github.com/user-attachments/assets/bab54362-a671-44d6-95ee-8a60f88266bf" />
</p>

---
## AI-Powered Static Application Security Testing (SAST) 
AI-powered SAST improves traditional static code analysis by using machine learning and advanced algorithms to detect vulnerabilities more accurately. This approach strengthens application security during development, helping organizations identify and fix issues early with greater efficiency and reliability.

1. **Better Pattern & Anomaly Detection** → AI-powered SAST can spot hidden and unusual code patterns that normal tools might miss, helping find unknown security flaws.
2. **Zero-Day Threat Detection** → AI can detect new, unpatched vulnerabilities before hackers exploit them, adding an extra security layer.
3. **Instant Code Analysis & Feedback** → Developers get real-time alerts about security issues while coding, making it easier to fix problems early and save time.
4. **Fewer False Alerts** → AI understands code context, reducing unnecessary warnings so security teams focus only on real threats.

AI-powered SAST tools use threat intelligence and continuous learning to detect new and evolving security risks. With AI’s strengths in pattern recognition, anomaly detection, and automation, these tools go beyond traditional methods, helping organizations build stronger and more secure software. This makes application security more adaptive and resilient in today’s digital landscape.

### AI-Powered Static Application Security Testing (SAST) Tool: Code Genie AI 
🔗Source: [https://www.rohanhall.com]
Code Genie AI is an innovative solution that leverages the power of AI to bolster the safety and resilience of smart contracts. Integrating AI into SAST transforms the approach to vulnerability detection and remediation within a blockchain ecosystem.

**Key Features** 
1. **Automated Vulnerability Scanning** → Automatically checks smart contract code for security flaws, saving time and reducing human errors.
2. **Advanced Pattern Recognition** → Uses AI trained on past vulnerabilities to detect hidden risks and unusual code patterns.
3. **Prioritized Risk Assessment** → Rates each issue by severity so developers can fix the most dangerous problems first.
4. **Actionable Recommendations** → Gives clear, step-by-step advice on how to fix the detected vulnerabilities.

<p align="center">
  <img width="747" height="352" alt="image" src="https://github.com/user-attachments/assets/37b45f83-dd8c-4ccd-b813-4a44d8afc2f6" />
</p>

### AI-Powered Static Application Security Testing (SAST) Tool: Codiga 
🔗Source: [https://www.codiga.io] <br>
Codiga's AI-powered static code analysis platform combines customizable rules, automated vulnerability detection, real-time feedback, and adherence to industry standards, enabling organizations to identify and mitigate security risks proactively. 

1. **Customizable Static Code Analysis with AI** → Codiga uses AI to give real-time code feedback and suggestions directly in your coding tool, making development faster and easier.
2. **Automated Vulnerability Detection and Fixes** → Codiga’s AI automatically finds security issues, suggests fixes, and even applies them, reducing errors and speeding up secure development.

<p align="center">
  <img width="618" height="359" alt="image" src="https://github.com/user-attachments/assets/0831b8f4-7ea7-4306-bf2e-9caa61cae1d3" />
</p>

### Additional AI-Powered Static Application Security Testing Tools 
- **Corgea** [https://corgea.com] <br>
  Corgea is an innovative AI-powered SAST tool that automates the generation of precise fixes, streamlines the remediation process, and ensures code integrity.

- **Checkmarx SAST** [https://checkmarx.com] <br>
  Checkmarx CxSAST is a SAST solution that leverages AI by automating and streamlining the vulnerability remediation process.

- **Snyk Code** [https://snyk.io] <br>
  The Snyk Code, powered by DeepCode AI, is a SAST tool that harnesses the power of purpose-built AI specifically trained on security-specific data and curated by top security researchers, ensuring unmatched accuracy and reliability.

- **CodeThreat** [https://www.codethreat.com] <br>
  Code Intelligence is a ground-breaking AI-driven application security testing platform designed to empower developers and security teams to build more reliable and secure embedded software. By leveraging AI-driven white-box fuzz testing, Code Intelligence enables early detection of critical bugs and vulnerabilities.

- **DryRun Security** [https://www.dryrun.security] <br>
  Dryrun Security is a powerful AI-powered SAST tool that prioritizes contextual security analysis and generative AI. It empowers developers to write secure code.

- **CodeIntelligence** [https://www.code-intelligence.com] <br>
  Code Intelligence is an AI-powered SAST platform designed to enhance the security of embedded software systems. By harnessing the capabilities of AI and fuzz testing, Code ntelligence enables developers to uncover hidden vulnerabilities and bugs early in the development lifecycle, ultimately enhancing the reliability and resilience of their software.

---
## AI-Powered Dynamic Application Security Testing (DAST) 
AI-powered DAST utilizes ML and advanced algorithms to automate and enhance the process of identifying vulnerabilities while running applications. This allows for a more comprehensive security assessment by simulating real-world attack scenarios and analyzing application behavior. However, the traditional DAST tools often lack accuracy when responding to modern attacks. <br>
Some key benefits of AI-powered DAST are as follows: 
1. **Simulate Complex Attack Scenarios** → AI adapts its testing to explore deeper and more complex vulnerabilities in applications.
2. **Increase Detection Accuracy** → AI reduces false positives, making vulnerability detection faster and more precise.
3. **Intelligent Test Case Generation and Prioritization** → AI creates and focuses on test cases for the most high-risk areas first.
4. **Reduced False Positives with Context-Aware Analysis** → AI understands application behavior to separate real threats from harmless actions.
5. **Self-Learning and Adaptation** → AI learns from past results to improve and keep up with new cyber threats.
6. **Automation and Integration with Development Pipelines** → AI automates testing tasks and fits easily into development workflows for early security checks.

AI-powered DAST represents a significant advancement in the field of application security testing. It offers a more realistic and effective way of identifying and mitigating vulnerabilities, ultimately improving the overall security of web applications. 

### AI-powered Dynamic Application Security Testing Tool: ZeroThreat.ai 
🔗Source: [https://zerothreat.ai] <br>
ZeroThreat.ai is an AI-powered dynamic application security testing (DAST) tool that detects and addresses vulnerabilities in real time. Unlike static analysis, it tests live applications by simulating attacks, finding weaknesses, and adapting to new threats with machine learning to deliver accurate, context-aware security insights.

**Key Features of ZeroThreat.ai**
1. **Intelligent Crawling** → AI-powered crawler scans complex websites and APIs quickly and thoroughly to find security flaws.
2. **Threat Intelligence Integration** → Uses live threat data to spot unusual activity and detect new attack methods before they cause harm.
3. **Minimizing False Positives** → AI filters out fake alerts so security teams focus only on real and dangerous issues.
4. **Integration Capabilities** → Easily connects with CI/CD pipelines for continuous and automated security checks during development.
5. **Fast Scanning Speeds** → Quickly finds critical vulnerabilities so they can be fixed early, reducing the risk window for attackers.

<p align="center">
  <img width="720" height="463" alt="image" src="https://github.com/user-attachments/assets/99bff00a-045f-4443-92f4-fdafb765bf1b" />
</p>

### Additional AI-Powered Dynamic Application Security Testing Tools 
Some additional AI-powered tools that assist in DAST include the following: 

- **VoltSec.io** [https://www.voltsec-io.com] <br>
  VoltSec.io combines AI-driven analyses with the knowledge and experience of certified ethical hackers. This collaborative approach ensures that vulnerabilities are not only identified but also thoroughly analyzed and prioritized based on potential risks. Ethical hackers leverage AI findings to delve deeper, providing actionable insights and a clear understanding of the security posture.

- **AppCheck** [https://appcheck-ng.com] <br>
  AppCheck is a vulnerability scanning tool designed for automated penetration testing on a scale that leverages advanced AI algorithms to deliver comprehensive and efficient vulnerability detection.

- ▪ **Aptori** [https://aptori.dev] <br>
  Aptori initiates the process with a reconnaissance phase. During this phase, AI algorithms gather and analyze information regarding the target system or network from various sources. This information gathering helps identify potential attack vectors that malicious actors might exploit.
  
- **Pentest Copilot** [https://copilot.bugbase.ai] <br>
  This tool leverages AI to streamline penetration testing by offering automated testing, real-time vulnerability detection, and detailed reporting.

- **Hackules**  [www.hackules.com] <br>
  Hackules utilizes AI to enhance web application security testing by automating vulnerability detection and prioritizing critical issues, thereby streamlining the process for security professionals.

- **Beagle Security** [www.beaglesecurity.com] <br>
  This platform focuses on automated vulnerability assessment for web applications. By integrating it with CI/CD pipelines, it delivers continuous testing, detailed vulnerability reports, and remediation guidance, facilitating robust security throughout the development lifecycle.

- **Veracode** [https://www.veracode.com] <br>
  Veracode, a leading application security platform, utilizes a combination of static, dynamic, and software composition analyses to proactively identify vulnerabilities within the software. By integrating automated testing into the development process, Veracode enables the early detection and remediation of security flaws. The platform offers comprehensive scanning of various vulnerabilities, detailed reporting, and remediation guidance, ultimately strengthening the overall application security posture of an organization.

- **Vigilocity** [https://www.vigilocity.com] <br>
  This platform prioritizes real-time security monitoring and incident response. It leverages advanced threat intelligence for the swift detection and response to security incidents. Vigilocity enhances the overall cybersecurity resilience by providing comprehensive threat visibility, automated response capabilities, and detailed incident reports.

- **DevOps Security** [https://www.devops.security] <br>
  DevOps.Security seamlessly integrates security practices into the DevOps lifecycle for application protection. It offers automated vulnerability scanning, secret management, and access control to proactively address security risks. DevOps.Security ensures secure software delivery while maintaining DevOps’ agility by fostering collaboration between the development, security, and operations teams.

---
## Source Code Review 
Source code review is the process of checking an application’s code to find bugs, insecure coding practices, and vulnerabilities. Done manually or with automated tools, it focuses on areas like authentication, session management, and data validation to detect issues such as unvalidated inputs or weak coding that attackers could exploit.

<p align="center">
  <img width="781" height="241" alt="image" src="https://github.com/user-attachments/assets/7c7c4e3b-1b8a-4e02-955e-7a56995dd55d" />
</p>

---
## Encoding Schemes 
Encoding schemes convert data into a symbolic form to hide its original meaning and ensure it is handled safely by web applications. At the receiving end, the data is decoded back to its original format. This helps applications process special characters and binary data without errors.

### Types of Encoding Schemes 
- **URL Encoding** <br>
  URL encoding is the process of converting characters in a URL into a valid ASCII format so they can be safely transmitted over HTTP. Since some characters have special meanings in URLs, they are replaced with “%” followed by their hexadecimal ASCII code. For example, “=” becomes %3d, a space becomes %20, and a new line becomes %0a. This ensures the URL is correctly interpreted by browsers and servers.

- **HTML Encoding** <br>
  HTML encoding is a method used to safely display special characters in web pages without breaking the page structure. Characters like `<`, `>`, and `&` are replaced with HTML entities such as `&lt;`, `&gt;`, and `&amp;`, ensuring they are shown as text instead of being treated as HTML code. This prevents errors and helps protect against issues like code injection.

- **Unicode Encoding** <br>
  Unicode encoding is of two types: 16-bit Unicode encoding and UTF-8.
  - **16-bit Unicode Encoding** <br>
    It replaces unusual Unicode characters with "`%u`" followed by the character’s Unicode codepoint expressed in the hexadecimal format like this: `%u2215 /`
  - **UTF-8** <br>
    It is a variable-length encoding standard that expresses each byte in the hexadecimal format and prefixes it with `%`.
    - `%c2%a9` `©`
    - `%e2%89%a0`

- **Base64 Encoding** <br>
  The Base64 encoding scheme represents any binary data using only printable ASCII characters. In general, it is used for encoding email attachments for safe transmission over SMTP and also for encoding user credentials. <br>
  For example: The binary value of cake is `cake = 01100011011000010110101101100101` <br>
  converting this binary value to Base64 encoding (binary format) <br>
  Base64 Encoding: `01011001 00110010 01000110 01110010 01011010 01010001 00111101 00111101`

- **Hex Encoding** <br>
  The HTML encoding scheme uses the hex value of every character to represent a collection of characters for transmitting binary data. For, example:
  ```hex
  Hello 48 65 6C 6C 6F
  Jason 4A 61 73 6F 6E
  ```

---
## Whitelisting vs. Blacklisting Applications 
Whitelisting and blacklisting are security strategies used to control which applications or entities can access a system. Whitelisting allows only trusted applications, while blacklisting blocks known malicious or unwanted ones. By applying these lists, organizations can reduce the risk of attacks and keep their applications, networks, and infrastructure secure.

### Application Whitelisting 
Application whitelisting allows only approved software, libraries, plugins, and configuration files to run on a system. This prevents unauthorized or malicious programs from executing, reduces the risk of installing vulnerable applications, and offers strong protection against threats like ransomware and other malware attacks.

### Application Blacklisting 
Application blacklisting is a security method where known malicious software is blocked from running on a system or network. It works by listing harmful applications and preventing their execution, either through firewalls or specialized blocking tools. Since it focuses only on known threats, it may miss new or advanced attacks, making regular updates to the blacklist essential for protection.

### Blacklisting and whitelisting for basic URL management
URL blacklisting prevents the user from loading web pages from the blacklisted URLs. The user can access all URLs except those in the blacklist. URL whitelisting permits the users to access only specific URLs as exclusions to those that are added to the URL blacklist.

URL whitelisting is performed using the following methods:
- **Allow access to all URLs except the blocked ones:** Whitelisting can allow the users to access the rest of the network applications
- **Block access to all URLs except permitted ones:** Whitelisting can permit access to a limited list of URLs
- **Define exceptions to very restrictive blacklists:** Whitelisting lets users access schemes, subdomains of other domains, specific paths, or ports
- **Allow the browser to open applications:** Whitelisting is performed only for specific external protocol handlers so that the browser can automatically execute applications

URL blacklisting is performed using the following methods:
- **Allow access to all URLs except the blocked ones:** Blacklisting prevents users from accessing blocked websites
- **Block access to all URLs except permitted ones:** Blacklisting blocks access to all malicious URLs
- **Define exceptions to very restrictive blacklists:** Blacklisting restricts access to all URLs that are vulnerable to attacks
- **Allow the browser to open apps:** Blacklisting prevents the browser from automatically executing applications

### Application Whitelisting and Blacklisting Tools 
Various tools that help security professionals in application whitelisting and blacklisting are discussed below. 
- **ManageEngine Application Control Plus** [https://www.manageengine.com]
- **BitDefender** [https://www.bitdefender.com]
- **Cisco Umbrella** [https://umbrella.cisco.com]
- **Symantec Endpoint Application Control** [https://www.broadcom.com]
- **BrowseControl** [https://www.currentware.com]
- **Sucuri WAF** [https://sucuri.net]

### Content Filtering Tools 
Content filtering tools are software or hardware solutions designed to control and manage access to web content based on predefined criteria. The tools enable organizations to enforce policies regarding Internet usage, blocking or allowing access to specific websites, applications, or specific types of content. 

Some additional application content filtering tools are as follows: 
- **TitanHQ WebTitan** [https://www.titanhq.com]
- **NG Firewall Complete** [https://edge.arista.com]
- **Smoothwall Filter** [https://smoothwall.com]
- **FortiGuard URL Filtering Service** [https://www.fortinet.com]
- **Barracuda Web Security Gateway** [https://www.barracuda.com]
- **OpenDNS** [https://www.opendns.com]
