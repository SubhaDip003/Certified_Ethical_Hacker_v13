# 🔍📝Footprinting and Reconnaissance
Footprinting and Reconnaissance is the process of collecting information about a target system or network to identify potential security weaknesses, typically done in the early phase of a cyberattack or penetration test.
## Types of Reconnaissance 
### Passive 
Gathering information about the target without direct interaction 
It involves: 
- Open-source Intelligence (OSINT) gathering 
- Proprietary databases and paid services 
- Sharing intelligence with partner organizations or industry groups
### Active 
Gathering information about the target with direct interaction 
It involves: 
- DNS interrogation 
- Social engineering 
- Network/port scanning 
- User and service enumeration

# 🔍Footprinting through Search Engines
- 🔗Source: [https://www.googleguide.com]
- 🔗GHDB: [https://www.exploit-db.com/google-hacking-database]

Attackers use search engines to **extract information about a target**, such as employed technology platforms, employee details, login pages, and intranet portals, which help the attacker to perform social engineering and other types of advanced system attacks. 

Google hacking refers to the use of advanced Google search operators for creating complex search queries to extract sensitive or hidden information that helps attackers find vulnerable targets.

## Popular Google advanced search operators
- **site:** This operator restricts search results to the specified site or domain. For example, the [games site: www.certifiedhacker.com] query gives information on games from the certifiedhacker site. 
- **allinurl:** This operator restricts results to only the pages containing all the query terms specified in the URL. For example, the [allinurl: google career] query returns only pages containing the words "google" and "career" in the URL. 
- **inurl:** This operator restricts the results to only the pages containing the specified word in the URL. For example, the [inurl: copy site:www.google.com] query returns only Google pages in which the URL has the word "copy." 
- **intext:** This operator displays the results containing the specific keyword within the body of the webpage. For example, the [intext:"vpn configuration"] query returns the pages containing the phrase "vpn configuration" in their body text.
- **allintitle:** This operator restricts result to only the page containing all the query terms sepecified in the title. For example, the [allintitle: detect malare] query returns only pages containing the words "detect" and "malware" in the title.
- **intitle:** This operator restricts results to only the pages containing the specified term in the title. For example, the [malware detection intitle:help] query returns only pages that have the term "help" in the title, and the terms "malware" and "detection" anywhere within the page.
- **inanchor:** This operator restricts results to only the pages containing the query terms specified in the anchor text on links to the page. For example, the [Anti-virus inanchor: Norton] query returns only pages with anchor text on links to the pages containing the word "Norton" and the page containing the word "Anti-virus."
- **allinanchor:** This operator restricts results to only the pages containing all query terms specified in the anchor text on links to the pages. For example, the [allinanchor: best cloud service provider] query returns only pages for which the anchor text on links to the pages contains the words "best," "cloud," "service," and "provider."
- **cache:** This operator displays Google's cached version of a web page instead of the current version of the web page. For example, [cache:www.eff.org] will show Google's cached version of the Electronic Frontier Foundation home page.
- **link:** This operator searches websites or pages that contain links to the specified website or page. For example, [link:www.googleguide.com] finds pages that point to Google Guide's home page.
- **Note:** According to Google's documentation, "you cannot combine a link: search with a regular keyword search." Also note that when you combine link: with another advanced operator, Google may not return all the pages that match.
- **related:** This operator displays websites that are similar or related to the URL specified. For example, [related:www.microsoft.com] provides the Google search engine results page with websites similar to microsoft.com.
- **info:** This operator finds information for the specified web page. For example, [info:gothotel.com] provides information about the national hotel directory GotHotel.com home page.
- **location:** This operator finds information for a specific location. For example, [location: 4 seasons restaurant] will give you results based on the term "4 seasons restaurant."
- **filetype:** This operator allows you to search for results based on a file extension. For Example, [jasmine:jpg] will provide jpg files based on jasmine.
- **source:** This operator displays information from a specific website in Google News. For example, [Malware news source:"Hacker News"] returns articles from Hacker News containing the word "Malware".
- **phonebook:** This operator finds the residential and business phone numbers of a person or organization. For example, [phonebook: Sundar Pichai] will provide Sundar Pichai's phone number.
- **before:** This operator filters search results to include only content published before a specified date. For example, [ransomware before:2020-06-29] will give results about the ransomware that occurred before June 29, 2020.
- **after:** This operator finds information that was published after a certain date. For example, [site:wikipedia.org after:2023-01-01 artificial intelligence] will retrieve Wikipedia articles about artificial intelligence published after January 1, 2023.


## VPN Footprinting through Google Hacking Database
```
# →  Finds pages containing login portals
inurl:"/sslvpn_logon.shtml" intitle:"User Authentication" "WatchGuard Technologies" 							

# →  Finds VPN login portals
inurl:/sslvpn/Login/Login 
site:vpn.*.*/intitle:"login"														

# →  Finds hosts with the Zyxel hardcoded password vulnerability 
inurl:weblogin 
intitle:("USG20-VPN" | "USG20W-VPN" | USG40|USG40W|USG60|USG60W|USG110|USG210|U SG310|USG1100|USG1900 | USG2200|"ZyWALL110" | "ZyWALL 310" | "ZYWALL1100" | ATP100|ATP100W|ATP200 ATP500|AT P700 ATP800|VPN50|VPN100|VPN300|VPN000|"FLEX") 

# → Finds Fortinet VPN login pages 
intext:Please Login SSL VPN inurl:remote/login 
intext:FortiClient

# → Retrieves various VPN login pages
site:vpn.*.*/intext:"login" intitle:"login" 

# → Retrieves juicy information and sensitive directories 
intitle:"index of"/etc/openvpn/

# → Finds OpenVPN static keys. 
*-----BEGIN OpenVPN Static key V1---" ext:key

# → Retrieves juicy information about the vpn-config file 
intitle:"index of" "vpn-config.*"

# → Finds OpenVPN configuration files, some certificates, and keys 
Index of /*.ovpn

# → Finds Netscaler and Citrix Gateway VPN login portals 
inurl:"/vpn/tmindex.html" vpn

# → Finds Cisco Adaptive Security Appliance (ASA) login web pages
intitle:"SSL VPN Service" + intext:"Your system administrator provided the following information to help understand and remedy the security conditions:" 
```

## Footprinting through SHODAN Search Engine
🔗 Source: [https://www.shodan.io]

Shodan is a search engine that enables attackers to perform footprinting at various levels. It is used to detect devices and networks with vulnerabilities. A search in Shodan for VoIP and VPN footprinting can deliver various results, which will help gather VPN- and VoIP-related information. 

## Others Techniques for Footprinting through Search Engines
Gathering information using **Google Advanced Search**, **Advanced Image Search**, and **Reverse Image Search**.

- Google Advanced Search:🔗 Source: [https://www.google.com/advanced_search]
- Google Advanced Image Search: 🔗 Source: [https://www.google.com/advanced_image_search]
- Reverse Iamge Search: 🔗 Source: [https://www.google.com/imghp]

## Gathering Information from File Transfer Protocol (FTP) Search Engines
- NAPALM FTP Indexer 🔗Source:[https://www.searchftps.net/]
- FreewareWeb FTP File Search 🔗 Source: [https://www.freewareweb.com/ftpsearch.shtml]
- Mamont 🔗 Source: [https://www.mmnt.ru/int/]
- Globalfilesearch.com 🔗 Source:[http://ww1.globalfilesearch.com/]

Some of the important advanced Google search queries for finding FTP servers
```
# → Finds files containing juicy information 
site:.in .com | .net intitle:"index of" ftp 
intitle:"index of" "*/ftp.txt" 
intext:"index of" "ftp" 
inurl:WS_FTP.log 
intitle:index.of/cftp/robots.txt 

# → Finds files containing passwords 
intitle: "Index of ftp passwords" 

# → Detects the web server 
inurl: /ftp intitle:"office" 

# → Finds pages containing login portals 
inurl:/web-ftp.cgi 
site:sftp.*.*/ intext:"login" intitle:"server login" 

# → Finds the "ws_ftp.ini" file, which contain usernames and passwords of FTP users 
intitle:"Index of" ws_ftp.ini 

# → Finds archived email conversations, at times revealing full credit-card numbers and customer information as well as private company emails 
inurl:ftp-inurl:(http|https) intext:"@gmail.com" intext:subject fwd confidential | important | CARD|cvw 

# → Detects various pages of CrushFTP WebInterface, which includes login portals as well password reset/recovery page 
allintitle:"CrushFTP WebInterface" 

# → Finds sensitive directories. 
"ws_ftp.log" ext:log 

# → Shows websites that use the FTP service of Monsta FTP 
intitle:"Monsta ftp" intext:"Lock session to IP"

# → Finds potential log files 
"index of" /ftp/logs 

# → Lists admin folders on FTP servers
intitle:"index of" inurl:ftp intext:admin 
```

# 🌐Footprinting through Internet Research Services 
Internet Research Services are online applications or sources that provide a varity of publicly accessible information related to the target organization. Some examples of information of: Domains, Subdomain, Hosts, etc.

- Netcraft 🔗Source: [https://www.netcraft.com]
- DNSdumpster 🔗Source: [https://dnsdumpster.com]
- Pentest-Tools 🔗Source: [https://pentest-tools.com]

## Extracting Website Information from archive.org 
🔗Source: [https://archive.org]
Internet Archive's Wayback Machine allows one to visit archived versions of websites.

## Footprinting through People Search Services
People search service, such as **Spokeo**, **Intelius**, and **Pipl** can provide critical information about a person or an organization, including location, emails, websites, blogs, contacts, importent dates, address, etc.

Job sites such as Dice, LinkedIn, and Glassdoor can reveal detials about a company's infrastructure, potentially aiding attackers in identifying vulnerabilities within the target's IT environment.

- Spokeo 🔗Source: [https://www.spokeo.com]

## 💀Dark Web Footprinting

### Dark web or Darknet 
- The dark web or Darknet is a deeper layer of the online cyberspace, that enables anyone to navigate anonymously without being traced
- Attackers use dark web searching tools, such as Tor Browser and ExoneraTor, to gather confidential information about the target
- Attackers can also use advanced search parameters to refine searches in the Dark Web to find specific data 

### TOR Browser 
🔗Source: [https://www.torproject.org]
- It is used to access the dark web where it acts as a default VPN for the user and bounces the network IP address through several servers before interacting with the web

### Searching the Dark Web with Advanced Search Parameters
```
Type of Information 			Search Query 						Explanation
-------------------			------------						-----------
Sensitive PDFs 				filetype:pdf site:onion confidential 			Finds PDF documents marked as confidential on .onion sites. 
Passwords in Config Files 		inurl:config filetype:txt password 			Searches for text files in configuration URLs containing passwords. 
Financial Documents 			filetype:xlsx site:onion financial 			Locates Excel files related to financial data on .onion sites. 
Database Dumps 				filetype:sql site:onion dump 				Finds SQL database dump files on.onion sites. 
Email Lists 				filetype:csv site:onion email 				Searches for CSV files containing email lists on .onion sites. 
Login Credentials 			intitle:"login credentials" filetype:docx 		Locates Word documents with login credentials in the title. 
Server Configurations 			filetype:xml inurl:config server 			Finds XML files related to server configurations. 
Private Keys 				filetype:key site:onion private 			Searches for private key files on .onion sites. 
Medical Records 			filetype:pdf site:onion "medical records" 		Locates PDF documents containing medical records on .onion sites. 
Business Plans 				filetype:ppt site:onion "business plan" 		Finds PowerPoint files with business plans on .onion sites. 
Source Code 				filetype:py site:onion "def" 				Searches for Python source code files on .onion sites. 
Legal Documents 			filetype:docx site:onion "legal document" 		Locates Word documents related to legal matters on .onion sites. 
Bank Statements 			filetype:pdf site:onion "bank statement"		Finds PDF documents containing bank statements on .onion sites. 
Intellectual Property 			filetype:pdf inurl:patent confidential 			Searches for patent documents marked as confidential in PDFs. 
Security Vulnerabilities		filetype:txt inurl:exploit 				Finds text files detailing security
```

## Determinning the Operation System
- Netcraft 🔗Source: [https://www.netcraft.com/tools]
- SHODAN 🔗Source: [https://www.shodan.io]
- Censys 🔗Source: [https://censys.io]

## Competitive Intelligence Gathering 
- Competitive intelligence gathering is the process of identifying, gathering, analyzing, verifying, and using information about your competitors from resources, such as the Internet
- Competitive intelligence is non-interfering and subtle in nature
  
Sources of Competitive Intelligence 
1. Company websites and employment ads
2. Social engineering employees
3. Search engines, Internet, and online database
4. Product catalogs and retail outlets
5. Press releases and annual reports
6. Analyst and regulatory reports
7. Trade journals, conferences, and newspapers
8. Customer and vendor interviews
9. Patent and trademarks
10. Agents, distributors, and suppliers

### Information Resources Sites
- EDGAR Database 🔗Source: [https://www.sec.gov/edgar]
- D&B Hoovers 🔗Source: [https://www.dnb.com]
- LexisNexis 🔗Source: [https://www.lexisnexis.com]
- Business Wire 🔗Source: [https://www.businesswire.com]
- Factiva 🔗Source: [https://www.dowjones.com]

Information resource sites that help attackers gain a company's plans include:
- MarketWatch 🔗Source: [https://www.marketwatch.com]
- The Wall Street Transcipt 🔗Source: [https://www.twst.com]
- Euromonitor 🔗Source: [https://www.eurominitor.com]
- Experian 🔗Source: [https://www.experian.com]
- The Search monitor 🔗Source: [https://www.thesearchmonitor.com]
- USPTO 🔗Source: [https://www.uspto.gov]

Information resource sites that help the attcker to obtain expert opinions about the target company include:
- SEMRush 🔗Source: [https://www.semrush.com]
- ABI/INFORM Global 🔗Source: [https://www.proquest.com]
- SimilarWeb 🔗Source: [https://www.similarweb.com]
- SeRanking 🔗Source: [https://seranking.com]

## Other Techniques for Footprinting through Internet Research Services
- Finding the Geographical ocation of the Target. Tool: Google Earth 🔗Source: [http://earth.google.com]
- Gathering information from Financial Services. Tool: Google Finance 🔗Source: [https://www.google.com/finance]
- Gathering information from Business Profiles Sites. 🔗Source: [opencorporates.com]
- Monitoring targets Using Alerts. Tool: Google Alerts 🔗Source: [https://www.google.com/alerts]
- Tracking the Online Reputation of the Target Tool: 🔗Source: Mention 🔗Source: [https://mention.com]
- Gathering information from Groups, Forums, and Blogs.
- Gathering information from Public Source-Code Repositories.

# 🧑‍🤝‍🧑Footprinting through Social Networking Sites 
Social Netwoking Services are online services, platforms, or sites that focus on facilitating the building of social networks or social relations among people.

## Using Sherlock
🔗Source: [https://github.com/sherlock-project/sherlock]

Sherlock is a python-based tool that is used to gather information about a target person over various social networking sites. Sherlock searches a vast number of social networking sites for a given target user, locates the person, and displays the results along with the complete URL related to the target person.

```
sherlock <"target_name">
sherlock "Elon Musk"
```

## Social Searcher 
🔗Source: [https://www.social-searcher.com ]

Social Searcher allows attackers to search for content on social networks in real time and provides deep analytics data. Attackers use this tool to track a target user on various social networking sites and obtain information such as complete URLs to their profiles, their postings, and other personal information.

## TheHarvester
🔗Source: [https://www.kali.org/tools/theharvester/]

theHarvester is a tool designed to be used in the early stages of a penetration test. It is used for open-source intelligence gathering and helps to determine a company's external threat landscape on the Internet. Attackers use this tool to perform enumeration on the LinkedIn social networking site to find employees of the target company along with their job titles.
```
theharvester -d microsoft.com -l 200 -b linkedin        # → Collects up to 200 email/usernames related to microsoft.com from LinkedIn.
theharvester -d eccouncil.org -l 200 -b baidu           # → Collects up to 200 email/usernames related to eccouncil.org from Baidu search engine.
theharvester -d microsoft.com -l 200 -b baidu -f Microsoft_email.xml  # → Collects up to 200 email/usernames related to microsoft.com from Baidu and saves the result in an XML file named Microsoft_email.xml.
```

## BuzzSumo 
🔗Source: [https://buzzsumo.com ]

BuzzSumo's advanced social search engine finds the most shared content for a topic, author, or domain. It shows the shared activity across all the major social networks including Twitter, Facebook, LinkedIn, Google Plus, and Pinterest.

## Social Searcher 
🔗Source: [https://www.social-searcher.com]

Social Searcher allows attackers to search for content on social networks in real time and provides deep analytics data. Attackers use this tool to track a target user on various social networking sites and obtain information such as complete URLs to their profiles, their postings, and other personal information.

# 🔎🌐Whois Footprinting
- 🔗Source: [https://whois.domaintools.com]
- 🔗Source: [https://www.tamos.com]
- 🔗Source: [http://www.sabsoft.com]

Whois databases are maintained by Regional Internet Registries and contain personal information of domain owners.

### Whois query returns 
- Domain name details
- Contact details of domain owners
- Domain name servers
- NetRange
- When a domain was created
- Expiry records
- Last updated record
  
### Information obtained from Whois database assists an attacker to 
- Gather personal information that assists in social engineering
- Create a map of the target organization's network
- Obtain internal details of the target network
  
### Regional Internet Registries (RIRs) 
The RIRs include the following: 
- American Registry for Internet Numbers (ARIN) [https://www.arin.net]
- African Network Information Center (AFRINIC) [https://www.afrinic.net]
- Asia Pacific Network Information Center (APNIC) [https://www.apnic.net]
- Réseaux IP Européens Network Coordination Centre (RIPE) [https://www.ripe.net]
- Latin American and Caribbean Network Information Center (LACNIC) [https://www.lacnic.net]

## Finding IP Geolocation Information 
🔗Source: [https://www.ip2location.com/]

IP geolocation helps to identify information, such as country, region/state, city, ZIP/postal code, time zone, connection speed, ISP (hosting company), domain name, IDD country code, area code, mobile carrier, and elevation. 

IP geolocation lookup tools, such as **IP2Location** and **IP Location Finder**, help to collect IP geolocation information about the target, which in turn helps attackers in launching social engineering attacks, such as spamming and phishing.

# 🧭📡DNS Footprinting


- DNS records provide important information about the location and types of servers. 
- Attackers can gather DNS information to determine key hosts in the network and can perform social engineering attacks 
```
Record Type	Description
-----------	-----------
A 		Points to a host's IP address 
MX 		Points to domain's mail server 
NS 		Points to host's name server 
CNAME 		Canonical naming allows aliases to a host 
SOA 		Indicate authority for a domain 
SRV 		Service records 
PTR 		Maps IP address to a hostname 
RP 		Responsible person 
HINFO 		Host information record includes CPU type and OS 
TXT 		Unstructured text records
```
Attackers query DNS servers using DNS interrogation tools, such as **Security Trails**, **Fierce**, **DNSChecker**, and **zdns**, to retrieve the record structure that contains information about the target DNS

### DNS Interrogation Tools 
- **nslookup:** 🔗Source: [https://www.nslookup.io/]
- **SecurityTrails:** 🔗Source: [https://securitytrails.com]
- **Fierce:** 🔗Source: [https://www.kali.org/tools/fierce/]
```
fierce --domain certifiedhacker.com                          		# → Performs a basic DNS reconnaissance on certifiedhacker.com to find subdomains and related hosts.
fierce --domain certifiedhacker.com --subdomains write admin mail  	# → Checks if subdomains like write.certifiedhacker.com, admin.certifiedhacker.com, and mail.certifiedhacker.com exist.
fierce --domain certifiedhacker.com --subdomains mail --traverse 10  	# → Attempts to find adjacent subdomains near mail.certifiedhacker.com using 10 brute-force steps.
fierce --domain certifiedhacker.com --subdomains mail --connect      	# → Checks connectivity (e.g., open ports) for mail.certifiedhacker.com.
fierce --domain certifiedhacker.com --wide                    		# → Performs a wide/deep DNS scan on certifiedhacker.com, expanding the brute-force subdomain range.
```
- **DNSChecker:** 🔗Source: [https://dnschecker.org/]
- **zdns:** 🔗Source: [https://github.com/zmap/zdns]
- **dnsdumpster:** 🔗Source: [https://dnsdumpster.com/]

## Reverse DNS Lookup
- Attackers perform a reverse DNS lookup on IP ranges in an attempt to locate a DNS record for those IP addresses.
- Attackers use various tools such as DNSRecon, Reverse Lookup, puredns, Reverse IP Domain Check, and Reverse IP Lookup to perform reverse DNS lookup on the target host. When we obtain an IP address or a range of IP addresses, we can use these tools to obtain the domain name.

### Tools
- **DNSRecon:** 🔗Source: [https://github.com/darkoperator/dnsrecon]
- **Reverse Lookup:** 🔗Source: [https://mxtoolbox.com]

# 🌐📬Network and Email Footprinting
## ARIN.net
ARIN.net helps ethical hackers know who owns an IP, which is useful for mapping the target network and performing reconnaissance without touching the target system. 🔗Source: [https://www.arin.net/]

## Traceroute
Traceroute programs work on the concept of ICMP protocol and use the TTL field in the header of ICMP packets to discover the routers on the path to a target host.

- **ICMP Traceroute (Windows):** Windows operating systems by default uses ICMP traceroute.
  ```
  tracert <target>
  ``` 
- **TCP Traceroute (Linux):** Many devices in any network are generally configured to block ICMP traceroute messages.
  ```
  sudo tcptraceroute <target>
  ```
- **UDP Traceroute (Windows|Linux):**
  ```
  traceroute <target>
  ```

## Traceroute Tools
### NetScanTool Pro: 🔗Source: [https://www.netscantools.com]
Attackers can use NetScan Tools Pro to trace the route packets traverse from their machine to the target device on a local area network or across the Internet. The tool offers ICMP, UDP, or TCP traceroute methods and allows attackers to identify the intermediate devices along the route. Also, it helps attackers locate the country assigned to each IPv4 address in each hop.

### PingPlotter: 🔗Source: [https://www.pingplotter.com]
PingPlotter allows attackers to collect traceroute data for target hosts using ICMP, UDP, and TCP packets. It automatically discovers the network hops and tracks latency and packet loss over time. Using this tool, attackers can visualize the traceroute data in readable graphs. This tool aids attackers in identifying bandwidth bottlenecks, WiFi interference, or hardware faults on the target network.

### Others tools
- **Traceroute NG** 🔗Source: [https://www.solarwinds.com/free-tools/traceroute-ng]
- **tracert**

## Email Tracking Tools 
Email tracking tools such as IP2LOCATION's Email Header Tracer, MxToolbox, eMailTrackerPro, Holehe, DNS Checker Email Header Analyzer, and Social Catfish allow an attacker to track an email and extract information such as sender identity, mail server, sender's IP address, location, and so on. Attackers use the extracted information to track the email path from the attacker's location to the target mail server using IP addresses in the email header.
- **eMailTrackerPro** 🔗Source: [https://www.emailtrackerpro.com]
- **IP2LOCATION's Email Header Tracer** 🔗Source: [https://www.ip2location.com]

# 🎭📞Footprinting through Social Engineering
Social engineering is a non-technical process in which an attacker misleads a person into providing confidential information inadvertently. In other words, the target is unaware of the fact that someone is stealing confidential information. The attacker takes advantage of the gullible nature of people and their willingness to provide confidential information.

Social engineering can be performed in many ways, such as eavesdropping, shoulder surfing, dumpster diving, impersonation, tailgating, third-party authorization, piggybacking, reverse social engineering, and so on.

## Collecting Information Using Eavesdropping, Shoulder Surfing, Dumpster Diving, and Impersonation 
- **Eavesdropping:**
  - Unauthorized listening of conversations or reading of messages
  - It is the interception of any form of communication, such as audio, video, or text 
- **Shoulder Surfing:**
  - Secretly observing the target to gather critical information, such as passwords, personal identification number, account numbers, and credit card information 
- **Dumpster Diving:**
  - Looking for treasure in someone else's trash 
  - It involves the collection of phone bills, contact information, financial information, operations-related information, etc. from the target company's trash bins, printer trash bins, user desk for sticky notes, etc. 
- **Impersonation:**
  - Pretending to be a legitimate or authorized person and using the phone or other communication medium to mislead targets and trick them into revealing information

# 🤖🧰Footprinting Tasks using Advanced Tools and AI
- **Maltego:** Maltego can be used to determine the relationships and real world links between people, groups of people, organizations, websites, Internet infrastructure, documents, etc. 🔗Source: [https://www.maltego.com]
- **Recon-ng:** Recon-ng is a Web Reconnaissance framework with independent modules and database interaction, which provides an environment in which open source, web-based reconnaissance can be conducted. 🔗Source: [https://github.com/lanmaster53/recon-ng]
- **FOCA:** **Fingerprinting Organizations with Collected Archives** (FOCA) is a tool used mainly to find metadata and hidden information in the documents that its scans. FOCA is capable of scanning and analyzing a wide variety of documents, with the most common ones being Microsoft Office, Open Office, or PDF files. 🔗Source: [https://www.elevenpaths.com]
- **SubFinder:** subfinder is a subdomain discovery tool that helps attackers find valid subdomains for websites. 🔗Source: [https://github.com/projectdiscovery/subfinder]
- **OSINT Framework:** OSINT Framework is an open source intelligence gathering framework that helps security professionals in performing automated footprinting and reconnaissance, OSINT research, and intelligence gathering. It is focused on gathering information from free tools or resources. This framework includes a simple web interface that lists various OSINT tools arranged by category, and it is shown as an OSINT tree structure on the web interface. 🔗Source: [https://osintframework.com ]
  - (T) - Indicates a link to a tool that must be installed and run locally
  - (D) - Google dork
  - (R) - Requires registration
  - (M) - Indicates a URL that contains the search term and the URL itself must be edited manually
- **Recon-Dog:** Recon-Dog is an all-in-one tool for all basic information gathering needs. It uses APIs to collect information about the target system. 🔗Source: [https://github.com/s0md3v/ReconDog]
- **BillCipher:** BillCipher is an information gathering tool for a website or IP address. It can work on any operating system that supports Python 2, Python 3, and Ruby. This tool includes various options such as DNS lookup, Whois lookup, port scanning, zone transfer, host finder, and reverse IP lookup, which help to gather critical information. 🔗Source: [https://github.com/bahatiphill/BillCipher]

### Some additional footprinting tools are listed below: 
- Sudomy 🔗Source:[https://github.com/screetsec/Sudomy]
- theHarvester 🔗Source: [https://www.edge-security.com]
- whatweb 🔗Source: [https://github.com/urbanadventurer/WhatWeb]
- Raccoon 🔗Source: [https://github.com/evyatarmeged/Raccoon]
- Orb 🔗Source: [https://github.com/orb-community/orb]
- Web Check 🔗Source: [https://web-check.xyz]
- OSINT.SH 🔗Source:[https://osint.sh]

## Al-Powered OSINT Tool: 
- **Taranis AI:** Taranis Al is an advanced OSINT tool uses Al to enhance information gathering and situational analyses. It uses NLP and Al to improve the quality of data received from data sources, such as websites, to gather unstructured news articles. Analysts then transform these Al-enhanced articles into organized reports that are used as the basis for deliverables such as PDF files that are eventually published. 🔗Source: [https://taranis.ai]
- **OSS Insight:** OSS Insight leverages Al to delve deep into the GitHub ecosystem by analyzing an extensive dataset of over five billion GitHub events. This capability enables it to offer comprehensive insights and tools to enhance the understanding and navigation of the open-source world. From detailed repository analytics encompassing metrics such as stars, forks, and commits to insights into developer productivity and collaboration patterns, OSS Insight is equipped with powerful resources for informed decision-making and strategic planning in open-source software development. 🔗Source: [https://ossinsight.io]

## Additional AI-Powered OSINT Tools
- **DorkGPT:** DorkGPT is an Al-powered tool designed to assist Google Dorking, a technique used to find information that is not easily accessible through regular search queries. It leverages the capabilities of GPT (Generative Pre-trained Transformer) models to generate and refine search queries, helping users uncover sensitive information, hidden pages, and other data that may be relevant to cybersecurity, ethical hacking, or research purposes. 🔗Source: [https://dorkgpt.com]
- **DorkGenius:** DorkGenius is an Al-powered tool that automates Google Dorking and helps users generate advanced search queries to find specific information on the internet. It is useful for uncovering hidden files, directories, sensitive information, and security vulnerabilities, particularly in the case of ethical hackers. 🔗Source: [https://dorkgenius.com ]
- **Google Word Sniper:** Google Word Sniper helps to refine search queries for more effective Google results. It identifies targeted keywords and phrases, making it easier to find specific information, hidden content, and niche data. This tool is valuable for researchers, marketers, and cybersecurity professionals, as it enhances their ability to uncover valuable buried information in search results. 🔗Source: [https://googlewordsniper.eu ]
- **Cylect.io:**  Cylect.io is an advanced Al-powered OSINT tool that integrates multiple databases into a user-friendly interface, providing a vast collection of resources for ethical hackers and enabling efficient and confident OSINT investigations. Developed to address the inefficiencies of traditional search engines, Cylect.io simplifies the search process and enhances the speed and accuracy of data collection in investigative contexts. 🔗Source: [https://cylect.io]
- **ChatPDF:** ChatPDF is an OSINT tool that leverages Al to analyze and extract information from PDF documents through a conversational interface. Users can upload PDF files and interact with the tool to quickly retrieve specific data, summaries, and insights, making it a valuable resource for ethical hacking. 🔗Source: [https://chatpdf.com]
- **Bardeen.ai:** Bardeen.ai is an automation tool that can be used for OSINT by enabling users to streamline and automate data collection and analysis processes from various online sources. This enhances the speed and accuracy of OSINT activities, making them useful assets for cybersecurity professionals, researchers, and investigators.  🔗Source: [https://www.bardeen.ai]
- **DarkGPT:** DarkGPT is an Al assistant that uses GPT-4-200K to query leaked databases, aiding in efficient and targeted searches within compromised data sources. This enables users to extract vital information and insights, enhancing the OSINT capabilities of cybersecurity analysts and researchers. 🔗Source: [https://github.com/luijait/DarkGPT]
- **PenLink Cobwebs:** PenLink Cobwebs is an advanced Al-powered OSINT tool that specializes in gathering and analyzing data from various online sources. It offers comprehensive capabilities for collecting, processing, and visualizing information to support cybersecurity investigations. 🔗Source: [https://cobwebs.com]
- **Explore Al:** Explore Al is an Al-powered YouTube search engine that uses artificial intelligence to search for and extract information from YouTube videos, making it easier to access information for ethical hacking purposes.  🔗Source: [https://exploreai.vercel.app]
- **AnyPicker:** AnyPicker is a powerful visual web scraper and AI OSINT tool designed to extract data from websites without requiring coding skills. This tool supports scraping multiple pages simultaneously and provides a real-time preview of the extraction results, offering flexibility and efficiency in web data collection. 🔗Source: [https://app.anypicker.com] 
