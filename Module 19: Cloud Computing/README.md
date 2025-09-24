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

