# Footprinting through Search Engines
🔗Source: [https://www.googleguide.com]

🔗GHDB: [https://www.exploit-db.com/google-hacking-database]

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

## Others Techniques for Footprinting through Search Engines
Gathering information using **Google Advanced Search**, **Advanced Image Search**, and **Reverse Image Search**.

- Google Advanced Search:🔗 Source: [https://www.google.com/advanced_search]
- Google Advanced Image Search: 🔗 Source: [https://www.google.com/advanced_image_search]
- Reverse Iamge Search: 🔗 Source: [https://www.google.com/imghp]

