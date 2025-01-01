# **Active Directory Lab Project: A Hands-On Approach to Cybersecurity**

## **Objective**
The **Active Directory Lab Project** is designed to build a hands-on, virtualized environment that replicates a professional Active Directory (AD) setup. The project integrates tools like **Splunk**, **Sysmon**, and **Kali Linux** for system monitoring, log analysis, and attack simulations. This lab allows you to practice both defensive (blue team) and offensive (red team) cybersecurity strategies by mimicking real-world AD scenarios.

## **Skills Learned**
- **Active Directory Configuration**: Learn how to set up and manage an AD environment using **Windows Server** and **Windows 10**.
- **Security Monitoring**: Configure and use **Sysmon** for detailed system activity logging and **Splunk** for log ingestion and analysis.
- **Red Team Exercises**: Simulate cyberattacks using **Kali Linux** tools like **Crowbar** and **Atomic Red Team**.
- **SIEM Analysis**: Use **Splunk** for correlating events, identifying attack patterns, and generating dashboards for attack monitoring.
- **Hands-On Cybersecurity**: Gain practical experience in defending and attacking a networked system using industry-standard tools.

## **Tools Used**
- **Windows Server 2022**: Set up as the domain controller in the AD environment.
- **Windows 10 Pro**: Configured as a client machine within the AD domain.
- **Kali Linux**: Used to simulate red team attacks on the Windows 10 machine.
- **Ubuntu Server**: Hosts **Splunk Enterprise** for log collection, monitoring, and analysis.
- **VMware**: Virtualizes the entire lab setup to create a modular and reusable platform for testing.

## **Steps**

### **1. Setting Up the Environment**
The lab environment was created using the following virtual machines (VMs):

- **Windows Server 2022**: Configured as the AD domain controller.
- **Windows 10 Pro**: Configured as a client machine joined to the domain.
- **Kali Linux**: Used as the attacker system to simulate various cyberattacks.
- **Ubuntu Server**: Hosts **Splunk** for log ingestion and analysis.

VMware was used for virtualization to create and manage these VMs in an isolated environment.

![Network Diagram](imgsrc)  
*Ref 1: Network Diagram*  
*Screenshot of the network layout used in the AD lab, showing the interconnected systems and components.*

### **2. Configuring Sysmon and Splunk**
To capture and monitor system activity, **Sysmon** was installed on both the Windows Server and Windows 10 machines. **Splunk Universal Forwarder** was set up on both machines to forward logs to the **Splunk** server. This allows for the centralized collection and analysis of security logs.

- **Sysmon**: Captures detailed system events, such as process creation, network connections, and file modifications.
- **Splunk Forwarder**: Sends Sysmon logs and Windows Event Logs to the Splunk server for analysis.
- **Splunk Server**: Configured to receive and index the logs for analysis.

![Sysmon Configuration](imgsrc)  
*Ref 2: Sysmon Configuration Screenshot*  
*Screenshot of the Sysmon configuration used to capture detailed logs from the Windows machines.*

### **3. Active Directory Setup**
The **Windows Server** was promoted to a domain controller, and a new domain (`aadhav.local`) was created. Organizational Units (OUs) were created, and domain users (`jsmith` and `tsmith`) were added.

- **Promoting Windows Server**: Installed the Active Directory Domain Services (AD DS) role and promoted the server to a domain controller.
- **Creating Domain Users**: Users were created in the Active Directory and added to the domain.
- **Joining Windows 10**: The Windows 10 machine was joined to the AD domain using the created credentials.

![AD Configuration](imgsrc)  
*Ref 3: AD Configuration Screenshot*  
*Screenshot showing the Active Directory setup on Windows Server, including domain creation and user management.*

### **4. Red Team Attack Simulation**
Red team exercises were conducted to simulate a brute force attack and other malicious activities on the AD environment.

- **Brute Force Attack**: Using **Kali Linux’s** **Crowbar** tool, a brute force attack was launched against the RDP service on the Windows 10 machine.
- **Atomic Red Team**: **Atomic Red Team** tests were run to simulate tactics like unauthorized user creation. These tests were executed using PowerShell scripts to simulate common attack techniques.

![Brute Force Attack](imgsrc)  
*Ref 4: Brute Force Attack Screenshot*  
*Screenshot showing the brute force attack logs captured in Splunk.*

### **5. Analyzing Telemetry in Splunk**
Once the attacks were executed, **Splunk** was used to ingest and analyze the telemetry data from the **Windows 10** machine.

- **Data Ingestion**: Logs from Sysmon and Windows Event Logs were ingested into **Splunk** for detailed analysis.
- **Search Queries**: **SPL (Search Processing Language)** was used to query logs for suspicious activities, such as failed login attempts and unauthorized access events.
- **Dashboards**: Visualizations were created to display attack patterns and system activities, helping to identify and respond to security incidents.

![Splunk Dashboard](imgsrc)  
*Ref 5: Splunk Dashboard Screenshot*  
*Screenshot of the Splunk dashboard, showing visualizations of detected attack patterns and suspicious activities.*

### **6. Conclusion and Next Steps**
By completing this project, I built a fully functional Active Directory lab environment that not only replicates real-world enterprise environments but also provides the tools for learning and practicing cybersecurity techniques. This setup allows for both attacking and defending network systems, offering hands-on experience in real-world attack detection and mitigation.

---

## **Lessons Learned**
- **Active Directory Management**: Understanding how to configure and manage Active Directory is crucial for network security.
- **Importance of Logging**: Sysmon and Splunk allow for detailed logging and effective monitoring of security events.
- **Red and Blue Team Activities**: Simulating cyberattacks (red team) and defending against them (blue team) is essential for improving overall cybersecurity knowledge.
- **Hands-On Experience**: The lab environment provides an opportunity to practice and enhance technical skills in a controlled setting.

## **Final Thoughts**
This project is a valuable resource for anyone interested in building foundational cybersecurity skills, especially in system administration and network defense. The knowledge gained from setting up, monitoring, and attacking the AD environment is essential for tackling real-world cybersecurity challenges.
