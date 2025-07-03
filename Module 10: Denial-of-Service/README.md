# 🛑 Denial-of-Service (DoS/DDoS)

## What is a DoS Attack?
A DoS attack is an attack on a computer or network that reduces, restricts, or prevents access to system resources for legitimate users. In a DoS attack, attackers flood a victim’s system with nonlegitimate service requests or traffic to overload its resources and bring down the system, leading to the unavailability of the victim’s website or at least significantly reducing the victim’s system or network performance. The goal of a DoS attack is to keep legitimate users from using the system, rather than to gain unauthorized access to a system or to corrupt data.

### The following are examples for types of DoS attacks:
- Flooding the victim’s system with more traffic than it can handle
- Flooding a service (e.g., Internet Relay Chat (IRC)) with more events than it can handle
- Crashing a TCP/IP stack by sending corrupt packets
- Crashing a service by interacting with it in an unexpected manner
- Hanging a system by causing it to go into an infinite loop

![image](https://github.com/user-attachments/assets/7569c35b-7490-4109-8ce4-193aa6cfdaea)

### DoS attacks have various forms and target various services. The attacks may cause the following:
- Consumption of resources
- Consumption of bandwidth, disk space, CPU time, or data structures
- Actual physical destruction or alteration of network components
- Destruction of programming and files in a computer system

**DoS (Denial of Service) attacks** are cyberattacks that overload a system or network to make it unavailable to legitimate users. These attacks don’t usually steal data but can cause serious disruptions by consuming resources like **bandwidth, CPU, or storage**, or by sending too many connection requests.

Just like blocking all the phone lines of a catering business would stop customer calls, a DoS attack floods the system so real users can't access it. The damage may include **network outages, service downtime, financial losses, and even file destruction**. In severe cases, DoS attacks can cause long-term harm to a company's reputation and operations.

---
## What is a DDoS Attack?
A **DDoS (Distributed Denial-of-Service) attack** is a large-scale cyberattack that floods a target system or network with massive traffic using many compromised computers, called **botnets**. This overloads the system, making it crash or become unavailable to real users.

Attackers first take control of vulnerable systems (called **secondary victims**) and use them to attack the main target (**primary victim**). Since the attack comes from many sources, it’s hard to trace back to the real attacker.

DDoS attacks are popular because they are easy to launch using available tools and scripts, but they can be very powerful—capable of shutting down even the biggest online services.

---
## How do DDoS Attacks Work?
**DDoS (Distributed Denial of Service) attacks** work by overwhelming a target system—like a website or network—with fake traffic, making it slow or completely unavailable. The attacker uses a **C\&C server** to control many infected devices called **zombie agents**. These zombies send fake connection requests to other systems (called **reflectors**) using the victim’s IP address.

The reflectors think the victim made the request and send all the responses back to the victim’s system. As a result, the victim gets flooded with unwanted traffic, which can slow it down or crash it completely.

![image](https://github.com/user-attachments/assets/fe64fd4d-ebdd-4886-978e-71a875f8e397)
