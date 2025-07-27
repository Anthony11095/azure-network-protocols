<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

## 🔧 Prerequisites

Before starting the osTicket installation, make sure the following requirements are met:

- Operating System: Windows 10 Pro or higher  
- Virtualization Platform: Hyper-V, VirtualBox, or VMware  
- Internet Connection  
- Virtual Machine (VM) setup completed  
- osTicket installation ZIP file downloaded from the official site  
- Web Server: IIS (Internet Information Services)  
- PHP (version 7.3+ recommended)  
- MySQL Server (or MariaDB)  
- SMTP Email Relay (optional, for email functionality)

Ensure that all tools are installed and available on your system before beginning the installation steps.
environment.

<h2>Actions and Observations</h2>

<p>
<img width="1897" height="866" alt="creating Azure virtual machine lab 2" src="https://github.com/user-attachments/assets/af2a197b-49c4-4e71-acf5-b10fac6242df" />

<img width="1904" height="857" alt="as you see above, we have created 2 virtual machines on the same network" src="https://github.com/user-attachments/assets/197d994e-1953-4e71-aced-ddbcbe27750d" />

<img width="1889" height="864" alt="opening the network security group to my obunto vm  using   disabiling (inbound) ICMP traffic" src="https://github.com/user-attachments/assets/616f75de-4f8d-49b8-99ef-abcd444a9e44" />

<img width="1901" height="835" alt="network security group ubuntu vm is using   disabiling inbound ICMP traffic" src="https://github.com/user-attachments/assets/ee0f19a7-8636-4a03-9a88-96aa038eddee" />

<img width="1900" height="867" alt="lab clean up deleting resource groups and VM's" src="https://github.com/user-attachments/assets/4f56c5e9-81dc-42ce-88ef-5dbfe7d2cb32" />

![image](https://github.com/user-attachments/assets/e5d3b7fb-90c7-4120-8594-ec46e6ca3688)


![image](https://github.com/user-attachments/assets/f72a3287-5e7b-43e0-8c45-fefcd76b1a91)

![image](https://github.com/user-attachments/assets/a3ef4226-247a-4585-b6f1-beb46ab31f7a)

![image](https://github.com/user-attachments/assets/d4790b3e-0ceb-48ab-9357-622a7c630f03)

![image](https://github.com/user-attachments/assets/65e7350a-95f2-4fd8-802f-e580f5925342)

![image](https://github.com/user-attachments/assets/5118e430-4071-452d-97b5-4ed6a0ffc601)

![image](https://github.com/user-attachments/assets/e11d3ed1-1b36-4c2f-8d01-18a692359818)

![image](https://github.com/user-attachments/assets/6ebbd7f8-7163-4d80-ba26-04366be9948b)

![image](https://github.com/user-attachments/assets/5589b034-d8aa-4c5a-99b8-ba4620f69f24)


































<img width="1900" height="867" alt="lab clean up deleting resource groups and VM's" src="https://github.com/user-attachments/assets/4f56c5e9-81dc-42ce-88ef-5dbfe7d2cb32" />











