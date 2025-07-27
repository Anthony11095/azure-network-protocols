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

## 🔧 Installation Steps

---

### 1. Open Virtual Machines in Azure Portal
<img width="1897" height="866" alt="creating Azure virtual machine lab 2" src="https://github.com/user-attachments/assets/af2a197b-49c4-4e71-acf5-b10fac6242df" />
Go to **Microsoft Azure Portal**, navigate to **Virtual Machines** under **Compute**, and click **+ Create** to begin creating a new virtual machine.

---

### 2. View Deployed Virtual Machines
<img width="1904" height="857" alt="as you see above, we have created 2 virtual machines on the same network" src="https://github.com/user-attachments/assets/197d994e-1953-4e71-aced-ddbcbe27750d" />
After deployment, go back to the **Virtual Machines** list to confirm your machines are running.

---
### 3. Confirm Virtual Machines Are Running
<img width="1904" height="857" alt="as you see above, we have created 2 virtual machines on the same network" src="https://github.com/user-attachments/assets/197d994e-1953-4e71-aced-ddbcbe27750d" />
From the **Azure Portal**, go to the **Virtual Machines** section. Confirm that your VMs (e.g., Linux and Windows) are listed as "Running" under the **Status** column.

---

### 4. Add an Inbound Security Rule
<img width="1889" height="864" alt="opening the network security group to my obunto vm  using   disabiling (inbound) ICMP traffic" src="https://github.com/user-attachments/assets/616f75de-4f8d-49b8-99ef-abcd444a9e44" />
In the **Network Security Group (NSG)** settings for your VM, go to **Inbound security rules**. Click **+ Add** to create a new rule. Choose your protocol, port, and action, then save it.



---


<img width="1901" height="835" alt="network security group ubuntu vm is using   disabiling inbound ICMP traffic" src="https://github.com/user-attachments/assets/ee0f19a7-8636-4a03-9a88-96aa038eddee" />


![image](https://github.com/user-attachments/assets/e5d3b7fb-90c7-4120-8594-ec46e6ca3688)


![image](https://github.com/user-attachments/assets/f72a3287-5e7b-43e0-8c45-fefcd76b1a91)

![image](https://github.com/user-attachments/assets/a3ef4226-247a-4585-b6f1-beb46ab31f7a)

![image](https://github.com/user-attachments/assets/d4790b3e-0ceb-48ab-9357-622a7c630f03)

![image](https://github.com/user-attachments/assets/65e7350a-95f2-4fd8-802f-e580f5925342)

![image](https://github.com/user-attachments/assets/5118e430-4071-452d-97b5-4ed6a0ffc601)

![image](https://github.com/user-attachments/assets/f1d295e8-635f-4a62-8aba-1e54fba4fe5b)

![image](https://github.com/user-attachments/assets/fcc542c3-1be1-4b6b-85fb-020f051c723b)

![image](https://github.com/user-attachments/assets/f3512797-5df5-4bcb-8ca1-937a583414a0)

![image](https://github.com/user-attachments/assets/b43a34c3-57f7-4620-8818-d75e975b4c00)

![image](https://github.com/user-attachments/assets/91921ef0-3258-49ed-b65a-31c2d4ccc42c)

![image](https://github.com/user-attachments/assets/8ad74040-ecfe-4dbf-9304-65bea7429d7c)

![image](https://github.com/user-attachments/assets/564d46cf-1c04-4c3a-a14d-a00fde77f2f6)

![image](https://github.com/user-attachments/assets/d68a554e-4870-436f-b9e8-7eba1280a2ab)

![image](https://github.com/user-attachments/assets/d2db0bd3-c818-4f6f-afd2-17c4b5e8f4ae)

![image](https://github.com/user-attachments/assets/9f79d1d6-77ed-4701-a9f4-50a40c3b8d6f)

![image](https://github.com/user-attachments/assets/16ab0822-0942-4ffc-9181-ff2d89562f21)

![image](https://github.com/user-attachments/assets/4901f4a2-00d8-4d5a-98a0-ef78bd747e36)

![image](https://github.com/user-attachments/assets/bfc7912c-e253-4633-881e-8e5704a901a0)

![image](https://github.com/user-attachments/assets/9ff43898-410f-4605-83c7-af5b11195b40)

![image](https://github.com/user-attachments/assets/24ad47e0-50d9-4cc4-a706-f76bdc6ffb15)


![image](https://github.com/user-attachments/assets/e06a9188-a10c-4125-91ce-874128293e0a)

























<img width="1900" height="867" alt="lab clean up deleting resource groups and VM's" src="https://github.com/user-attachments/assets/4f56c5e9-81dc-42ce-88ef-5dbfe7d2cb32" />











