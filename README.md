# vms-firewall-config-with-ufw

A personal virtual lab project focused on configuring a secure firewall on a minimal Alpine Linux VM using ufw. This repository documents the process of setting default policies, opening essential ports (SSH, DNS, NTP), and enabling the firewall for a secure, persistent environment.

## Virtual Machine Setup: Firewall Configuration with UFW

### 1. Overview of the Project

This project focused on implementing a basic firewall within my Alpine Linux VM to gain hands-on experience with network security principles. To secure the virtual environment, I chose to use ```ufw``` (Uncomplicated Firewall). I also installed ```tcpdump``` and ```nmap``` as essential tools for network monitoring and discovery. The date of this project was 08 August 2025.

### 2. Key Concepts & Learning Outcomes

Throughout this project, I gained practical experience and a deeper understanding of the following areas:

**Default-Deny Principle:** Implemented the fundamental security practice of denying all incoming traffic by default, only allowing what is explicitly needed.

**Firewall Configuration:** Learned how to configure a firewall to allow specific traffic, such as SSH, DNS, and NTP, to maintain essential functionality while keeping the system secure.

**Network Monitoring Tools:** Gained familiarity with tools like ```tcpdump``` for packet analysis and ```nmap``` for network scanning, which are crucial for auditing and understanding network traffic.

**Service Management:** Learned how to enable a service (```ufw```) to start automatically on system boot, ensuring the firewall remains active after a reboot.

### 3. Hands-on Experience & Practical Application

The firewall setup involved a series of practical steps that put security concepts into practice:

**Tool Installation:** I installed the necessary tools with ```sudo apk add ip6tables ufw``` for the firewall and verified its installation using ```ufw --version```. I also installed ```tcpdump``` and ```nmap``` to monitor and scan the network.

**Default Policies:** To establish a secure baseline, I used ```sudo ufw default deny incoming``` to block all incoming connections by default and ```sudo ufw default allow outgoing``` to permit outgoing traffic for internet access.

**Rule Configuration:** I configured specific rules to allow necessary services, including ```sudo ufw allow ssh``` for remote access, ```sudo ufw allow out 53``` for DNS resolution, and ```sudo ufw allow out 123/udp``` for network time protocol (NTP) synchronization.

**Enabling the Firewall:** After configuring the rules, I enabled the firewall with ```sudo ufw enable``` and ensured it would persist across reboots using ```sudo rc-update add ufw```.

**Verification:** I confirmed that the firewall was active and the rules were correctly applied by running ```sudo ufw status verbose```.

### 4. Tools Used

* **Guest Operating System:** ```Alpine Linux```
* **Firewall Tool:** ```ufw```
* **Network Tools:** ```tcpdump```, ```nmap```
* **Commands:** ```apk```, ```ufw```, ```rc-update```

### 5. Conclusion & Key Takeaways

This project successfully implemented a basic but effective firewall on the Alpine Linux VM. The use of ```ufw``` was an excellent starting point for understanding firewall concepts without unnecessary complexity. The experience reinforced the importance of a default-deny policy and the need to explicitly allow only the traffic required for a system to function. The process from installation to configuration and verification provided invaluable hands-on experience that will serve as a strong foundation for future, more advanced security projects.
