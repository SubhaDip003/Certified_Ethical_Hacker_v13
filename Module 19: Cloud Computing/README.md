# ☁️ Cloud Computing Concepts 
Cloud computing delivers various types of services and applications over the Internet. These services enable users to utilize software and hardware managed by third parties at remote locations. Major cloud service providers include Google, Amazon, and Microsoft. <br>
This section introduces cloud computing, the types of cloud computing services, the separation of responsibilities, the cloud deployment models, the NIST reference architecture and its benefits, the cloud storage architecture, and the cloud service providers.

---
## Introduction to Cloud Computing 
Cloud computing is the on-demand delivery of IT resources like storage, servers, and applications over the internet, where users pay only for what they use. Popular examples include Gmail, Dropbox, Facebook, and Salesforce, which provide scalable services without needing local infrastructure.

### Characteristics of Cloud Computing 
Discussed below are the characteristics of cloud computing that attract many businesses today to adopt cloud technology. 
1. **On-Demand Self-Service** → Users can get cloud resources like storage, computing power, or network instantly without needing help from the provider.
2. **Distributed Storage** → Data is stored across multiple servers for better availability, scalability, and reliability, though it may raise security and compliance concerns.
3. **Rapid Elasticity** → Cloud allows quick scaling of resources up or down based on demand, giving the impression of unlimited availability.
4. **Automated Management** → Most processes are automated, reducing human involvement, lowering costs, and minimizing errors.
5. **Broad Network Access** → Cloud resources can be accessed anytime, anywhere, using devices like laptops, mobiles, or tablets via standard internet connections.
6. **Resource Pooling** → Providers share pooled physical and virtual resources among multiple users, assigning them dynamically as needed.
7. **Measured Service** → Customers pay only for what they use (storage, bandwidth, processing power) with complete usage tracking and transparency.
8. **Virtualization Technology** → Virtualization helps create multiple virtual systems on one physical server, making resource scaling fast and efficient.

### Limitations of Cloud Computing
- Limited control and flexibility of organizations
- Proneness to outages and other technical issues
- Security, privacy, and compliance issues
- Contracts and lock-ins
- Dependence on network connections
- Potential vulnerability to attacks as every component is online
- Difficulty in migrating from one service provider to another

---
## Types of Cloud Computing Services 
Cloud services are divided broadly into the following categories: 

### Infrastructure-as-a-Service (IaaS) 
Infrastructure-as-a-Service (IaaS) is a cloud model that provides on-demand IT resources like servers, storage, networking, and virtualization. Users can create and manage virtual machines and operating systems via APIs, while the provider handles the physical infrastructure. This reduces hardware and staffing costs, making it flexible and scalable for businesses. Examples include Amazon EC2, Microsoft OneDrive, and Rackspace.

- **Advantages:**
  - Dynamic infrastructure scaling
  - Guaranteed uptime
  - Automation of administrative tasks
  - Elastic load balancing (ELB)
  - Policy-based services
  - Global accessibility

- **Disadvantages:**
  - Software security is at high risk (third-party providers are more prone to attacks)
  - Performance issues and slow connection speeds 

### Platform-as-a-Service (PaaS)
Platform-as-a-Service (PaaS) is a cloud model that provides a ready-made environment for building and deploying applications without managing the underlying infrastructure. It offers tools for development, configuration, and deployment on demand. Developers can focus on creating applications while the platform handles scalability, backups, and maintenance. Examples include Google App Engine, Microsoft Azure, and Salesforce.

- **Advantages:**
  - Simplified deployment
  - Prebuilt business functionality
  - Lower security risk compared to IaaS
  - Instant community
  - Pay-per-use model
  - Scalability 

- **Disadvantages:**
  - Vendor lock-in
  - Data privacy
  - Integration with the rest of the system applications
 
### Software-as-a-Service (SaaS)
Software-as-a-Service (SaaS) delivers application software over the Internet, allowing users to access tools like Google Docs or Salesforce without installing them locally. It follows models such as pay-per-use or subscription and is managed by the provider, who handles updates, maintenance, and security. SaaS offers flexibility and scalability but requires strong security controls to protect data stored and processed in the cloud.

- **Advantages:**
  - Low cost
  - Easy administration
  - Global accessibility
  - High compatibility (no specialized hardware or software is required)

- **Disadvantages:**
  - Security and latency issues
  - Total dependency on the Internet
  - Switching between SaaS vendors is difficult
 
### Identity-as-a-Service (IDaaS)
Identity-as-a-Service (IDaaS) is a cloud-based solution that provides enterprises with secure identity and access management handled by a third-party vendor. It includes features like Single Sign-On (SSO), Multi-Factor Authentication (MFA), and Identity Governance to ensure only authorized users can access systems and data. Popular services such as Okta, Microsoft Azure AD, and OneLogin help organizations protect sensitive information across both on-premises and cloud environments.

- **Advantages:**
  - Low cost
  - Improved security
  - Simplify compliance
  - Reduced time
  - Central management of user accounts

- **Disadvantages:**
  - Single server failure may disrupt the service or create redundancy on other authentication servers
  - Vulnerable to account hijacking attacks 

### Security-as-a-Service (SECaaS)
Security-as-a-Service (SECaaS) is a cloud-based model that delivers security tools and services without the need for physical hardware, making it cost-effective for organizations. It offers solutions like penetration testing, authentication, intrusion detection, anti-malware, and SIEM. Providers such as eSentire MDR, Switchfast Technologies, OneNeck IT Solutions, and Foundstone Managed Security Services help businesses strengthen security while reducing costs and complexity.

- **Advantages:**
  - Low cost
  - Reduced complexity
  - Continuous protection
  - Improved security through best security expertise
  - Latest and updated security tools
  - Rapid user provisioning
  - Greater agility
  - Increased time on core competencies
 
- **Disadvantages:**
  - Increased attack surfaces and vulnerabilities
  - Unknown risk profile
  - Insecure APIs
  - No customization to business needs
  - Vulnerable to account hijacking attacks

### Container-as-a-Service (CaaS)
Container-as-a-Service (CaaS) is a cloud model that delivers container engines, clusters, and management tools as a service. It lets organizations build, deploy, and scale containerized applications easily through web portals or APIs, either in the cloud or on-premises. CaaS combines features of IaaS and PaaS, with examples including Amazon EC2 and Google Kubernetes Engine (GKE).

- **Advantages:**
  - Streamlined development of containerized applications
  - Pay-per-resource
  - Increased quality
  - Portable and reliable application development
  - Low cost
  - Few resources
  - Crash of application container does not affect other containers
  - Improved security
  - Improved patch management
  - Improved response to bugs
  - High scalability
  - Streamlined development

- **Disadvantages:**
  - High operational overhead
  - Platform deployment is the developer’s responsibility

### Function-as-a-Service (FaaS) 
Function-as-a-Service (FaaS) is a serverless cloud model that lets developers run specific application functions without managing servers. It is widely used for microservices, IoT, mobile, and web apps, as well as batch or stream processing. FaaS runs code only when needed, turning off infrastructure when idle, so users pay only for execution time. Common examples include AWS Lambda, Google Cloud Functions, Azure Functions, and Oracle Functions.

- **Advantages:**
  - Pay-per-use
  - Low cost
  - Efficient security updates
  - Easy deployment
  - High scalability

- **Disadvantages:**
  - High latency
  - Memory limitations
  - Monitoring and debugging limitations
  - Unstable tools and frameworks
  - Vendor lock-in

### Anything-as-a-Service (XaaS
Anything-as-a-Service (XaaS) is a cloud-based model where a wide range of services and resources are delivered to users over the internet on demand. Instead of buying or licensing traditional products, users pay only for what they use. XaaS goes beyond common cloud services like SaaS (software), PaaS (platform), and IaaS (infrastructure), and extends to offerings such as Network-as-a-Service (NaaS), Storage-as-a-Service (STaaS), Testing-as-a-Service (TaaS), Malware-as-a-Service (MaaS), and Disaster Recovery-as-a-Service (DRaaS).

This model allows organizations to access advanced tools, applications, and technologies without managing complex infrastructure. It also extends to non-digital services such as food delivery, healthcare, and transportation through cloud-enabled platforms. Well-known providers like AWS Elastic Beanstalk, NetApp, Heroku, and Apache Stratos offer such scalable and flexible services.

- **Advantages:**
  - Highly scalable
  - Independent of location and devices
  - Fault tolerance and reduced redundancy
  - Reduced capital expenditure
  - Enhances business process by supporting rapid elasticity and resource sharing

- **Disadvantages:**
  - Chances of service outage as XaaS is dependent on the Internet
  - Performance issues due to high utilization of the same resources
  - Highly complex and difficult to troubleshoot at times

### Firewalls-as-a-Service (FWaaS)
Firewalls-as-a-Service (FWaaS) is a cloud-based security solution that filters and monitors network traffic to protect against internal and external threats. It offers features like packet filtering, network analysis, IPsec support, and advanced malware detection. Popular solutions include Zscaler Cloud Firewall, SecurityHQ, Secucloud, Fortinet, Cisco, and Sophos.

- **Advantages:**
  - Blocks malicious web traffic
  - Protects multiple cloud deployments
  - Standardized policy implementation
  - Improved network visibility
  - Enhanced reliability
  - Simpler architecture
  - Easier maintenance

- **Disadvantages:**
  - Resistance to acceptance
  - Network latency issues

### Desktop-as-a-Service (DaaS)
Desktop-as-a-Service (DaaS) delivers virtual desktops and applications from the cloud on demand. The provider manages the infrastructure, storage, updates, and security, while users access desktops remotely. It follows a multi-tenant, pay-as-you-go model, making it cost-effective and scalable. Examples include Amazon WorkSpaces, Citrix Managed Desktops, and Azure Virtual Desktop.

- **Advantages:**
  - Global accessibility
  - Simplified management
  - Reduced downtime
  - Low cost
  - High flexibility
  - High scalability

- **Disadvantages:**
  - Security issues
  - Network connectivity issues
  - High licensing costs

### Mobile Backend-as-a-Service (MBaaS) 
Mobile Backend-as-a-Service (MBaaS) is a cloud service that helps developers quickly connect mobile apps to backend systems using APIs and SDKs. It saves time by handling backend tasks like user authentication, push notifications, cloud storage, databases, and location services. Popular examples include Google Firebase, AWS Amplify, Kinvey, Apple CloudKit, and Backendless Cloud.

- **Advantages:**
  - Improved development efficiency
  - Highly flexible
  - Scalability
  - Pay-as-you-go model

- **Disadvantages:**
  - Security issues
  - High initial costs

### Machines-as-a-Service (MaaS) Business Model
Machines-as-a-Service (MaaS), also called Equipment-as-a-Service (EaaS), is a cloud-based model where manufacturers lease machines to clients and earn revenue based on the profits those machines generate. It enables both manufacturers and clients to benefit by tracking machine performance and production in real time, improving efficiency and reducing upfront costs for clients.

- **Advantages:**
  - Low investment cost
  - Improved adaptability
  - Reliable and cost-effective income source
  - Improved product quality and quantity

- **Disadvantages:**
  - Maintenance and repairs are expensive
  - Machines replace human workers, resulting in unemployment

---
## Shared Responsibilities in Cloud 
In cloud computing, the separation of responsibilities of subscribers and service providers is essential. Separation of duties prevents conflict of interest, illegal acts, fraud, abuse, and error and helps in identifying security control failures, including information theft, security breaches, and evasion of security controls. It also helps in restricting the amount of influence held by any individual and ensures that there are no conflicting responsibilities. <br>
There are mainly three types of cloud services; namely, IaaS, PaaS, and SaaS. It is essential to know the limitations of each cloud service delivery model when accessing specific clouds and their models. The figure below illustrates the separation of cloud responsibilities specific to service delivery models.

<p align="center">
  <img width="646" height="286" alt="image" src="https://github.com/user-attachments/assets/2f629b4b-b46e-4c26-bbe1-17b2dd65c67d" />
</p>

---
## Cloud Deployment Models 
Cloud deployment model selection is based on enterprise requirements. One can deploy cloud services in different ways, according to the factors given below:
- Host location of cloud computing services
- Security requirements
- Sharing of cloud services
- Ability to manage some or all of the cloud services
- Customization capabilities

The four standard cloud deployment models are 

### Public Cloud 
A public cloud is a model where a provider delivers services like applications, servers, and storage over the Internet for anyone to use. The provider manages the setup, security, and maintenance of these resources. Public clouds can be free or pay-as-you-go, with popular examples including Amazon EC2, Google App Engine, Microsoft Azure, and IBM Bluemix.

- **Advantages:**
  - Simplicity and efficiency
  - Low cost
  - Reduced time (when server crashes, needs to restart or reconfigure cloud)
  - No maintenance (public cloud service is hosted off-site)
  - No contracts (no long-term commitments)

- **Disadvantages:**
  - Security is not guaranteed
  - Lack of control (third-party providers are in charge)
  - Slow speed (relies on Internet connections; the data transfer rate is limited)

<p align="center">
  <img width="362" height="329" alt="image" src="https://github.com/user-attachments/assets/3c2010d8-da2d-4059-b1cf-df5f879ea877" />
</p>

### Private Cloud 
A private cloud is a cloud setup used by a single organization and secured within its own firewall. It gives full control over data, resources, and security, making it suitable for businesses that handle sensitive information. Solutions like BMC Software, VMware vRealize Suite, and SAP Cloud Platform are common examples of private cloud deployments.

- **Advantages:**
  - Security enhancement (services are dedicated to a single organization)
  - Increased control over resources (organization is in charge)
  - High performance (cloud deployment within the firewall implies high data transfer rates)
  - Customizable hardware, network, and storage performances (as the organization owns private cloud)
  - Sarbanes Oxley, PCI DSS, and HIPAA compliance data are much easier to attain

- **Disadvantages:**
  - High cost
  - On-site maintenance

<p align="center">
  <img width="418" height="383" alt="image" src="https://github.com/user-attachments/assets/0051e338-68ed-491d-92ed-367114391cc3" />
</p>

### Community Cloud
A community cloud is a shared cloud environment where multiple organizations with similar needs, such as security, compliance, or performance, use the same infrastructure. It can be hosted on-premises or by a third-party provider and is managed collectively or externally. This model is often used in industries like healthcare or government to meet strict regulatory and data security requirements.

- **Advantages:**
  - Less expensive compared to the private cloud
  - Flexibility to meet the community’s needs
  - Compliance with legal regulations
  - High scalability
  - Organizations can share a pool of resources from anywhere via the Internet

- **Disadvantages:**
  - Competition between consumers in resource usage
  - Inaccurate prediction of required resources
  - Lack of legal entity in case of liability
  - Moderate security (other tenants may be able to access data)
  - Trust and security concerns between tenants

<p align="center">
  <img width="459" height="348" alt="image" src="https://github.com/user-attachments/assets/51393604-e2e4-42fc-80ed-29fb36866118" />
</p>

### Hybrid Cloud
A hybrid cloud combines private, public, or community clouds into one environment, allowing organizations to use both in-house and external resources. This model offers flexibility, scalability, and cost efficiency while keeping sensitive data secure in private systems and using public cloud services like Microsoft Azure for broader needs. (e.g., Microsoft Azure, Zymr, Parangat Cloud Computing, Logicalis). <br>
**Example:** An organization performs its critical activities on the private cloud (e.g., operational customer data) and non-critical activities on the public cloud. 

- **Advantages:**
  - High scalability (contains both public and private clouds)
  - Offers both secure and scalable public resources
  - High level of security (comprises private cloud)
  - Allows to reduce and manage the cost according to requirements

- **Disadvantages:**
  - Communication at the network level may be conflicted as it uses both public and private clouds
  - Difficult to achieve data compliance
  - Organization reliant on the internal IT infrastructure in case of outages (maintain redundancy across data centers to overcome)
  - Complex service level agreements (SLAs) 

<p align="center">
  <img width="421" height="323" alt="image" src="https://github.com/user-attachments/assets/9a0d7697-5fe4-46fe-9b42-9e760df259af" />
</p>

### Multi Cloud
Multi-cloud is an environment where organizations use services from multiple cloud providers to run workloads, store data, and manage applications. It can be all-private, all-public, or a mix of both. By spreading resources across different vendors, multi-cloud improves performance, increases storage and computing power, and reduces the risk of downtime or data loss. Examples include Microsoft Azure Arc and Google Cloud Anthos.

- **Advantages:**
  - High reliability and low latency
  - Flexibility to meet business needs
  - Cost-performance optimization and risk mitigation
  - Low risk of distributed denial-of-service (DDoS) attacks
  - Increased storage availability and computing power
  - Low probability of vendor lock-in

- **Disadvantages:**
  - Multi-cloud system failure affects business agility
  - Using more than one provider causes redundancy
  - Security risks due to complex and large attack surface
  - Operational overhead

<p align="center">
  <img width="331" height="278" alt="image" src="https://github.com/user-attachments/assets/2c82d013-d533-4b32-b58b-4798991264ed" />
</p>

Other cloud deployment models include the following. 
### Distributed Cloud 
A distributed cloud is a centralized cloud system that uses multiple public or private clouds spread across different locations but managed under one control plane. It allows users to access data and services as if they were stored locally, improving speed, privacy, and compliance with local regulations. This model supports edge computing and is useful for AI, ML, and IoT applications. Examples include Google Distributed Cloud and Cloudflare CDN.

- **Advantages:**
  - High performance
  - Reduced latency
  - High management and operational consistency compared to hybrid and multi cloud
  - On-site modernization
  - Edge computing capabilities
  - On-premises data processing capability
  - Stringent data security
  - Automation applications (AI, ML, IoT etc.)

- **Disadvantages:**
  - Security-related vulnerabilities may arise
  - High cost (network infrastructure deployment cost)
  - Limited software assistance
  - Complex troubleshooting

<p align="center">
  <img width="382" height="243" alt="image" src="https://github.com/user-attachments/assets/a2f778a9-efbb-41b4-a267-da66ecb16b5e" />
</p>

### Poly Cloud
Poly Cloud is a cloud model that combines features from different cloud providers into a single platform. Unlike multi-cloud, where separate clouds are used, poly cloud lets businesses choose and use specific services from multiple providers, such as AI from Google Cloud or ML from AWS. This approach gives flexibility, better automation, and optimized performance based on business needs.

- **Advantages:**
  - High flexibility
  - Environmental choice
  - Infrastructure and return on investment (ROI) optimization
  - Provides specialized AI and ML services
  - Cost effective
  - High performance

- **Disadvantages:**
  - Time-consuming for initial setup
  - Lack of a fixed tool
  - High R&D cost prior to implementation of the tool
  - Not affordable by small-and medium-cap companies
  - Lack of a fixed model

<p align="center">
  <img width="416" height="270" alt="image" src="https://github.com/user-attachments/assets/48b65d97-81fd-4a86-ab18-9b2364b4290d" />
</p>

---
## NIST Cloud Deployment Reference Architecture 





