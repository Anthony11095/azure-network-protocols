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

### 5. Review Inbound Security Rules
<img width="1901" height="835" alt="network security group ubuntu vm is using   disabiling inbound ICMP traffic" src="https://github.com/user-attachments/assets/ee0f19a7-8636-4a03-9a88-96aa038eddee" />
Once your inbound rule has been added, verify it appears in the list with correct settings under **Inbound security rules** for your VM's network security group.

---

### 6. Open PowerShell as Administrator
![image](https://github.com/user-attachments/assets/e5d3b7fb-90c7-4120-8594-ec46e6ca3688)
On your Windows VM, go to the Start Menu, search for **Windows PowerShell**, right-click it, and select **Run as administrator** to begin running commands.

---

### 7. Start Wireshark Packet Capture
![image](https://github.com/user-attachments/assets/f72a3287-5e7b-43e0-8c45-fefcd76b1a91)
Open **Wireshark** and choose your active network adapter (such as Ethernet or Wi-Fi). Then, click on it to begin capturing packets on the network.

---

### 8. Initiate Traffic from the Target VM
![image](https://github.com/user-attachments/assets/a3ef4226-247a-4585-b6f1-beb46ab31f7a)
Use the remote VM or device to generate traffic — like pinging an IP or logging into another system — so Wireshark has data to record. This verifies that communication is flowing through the adapter.

---

### 9. Monitor SSH Traffic in Wireshark
![image](https://github.com/user-attachments/assets/d4790b3e-0ceb-48ab-9357-622a7c630f03)
Use **PowerShell** to SSH into the target system (e.g., `ssh labuser@10.0.0.5`) and observe the traffic in Wireshark. Look for SSH packets to confirm encrypted communication is captured.

---

### 10. Verify SSH Access and System Info
![image](https://github.com/user-attachments/assets/65e7350a-95f2-4fd8-802f-e580f5925342)
After successfully connecting to the Linux VM via SSH, run commands like `id`, `hostname`, and `uname -a` to verify your access and view system details.

---

### 11. Inspect Encrypted Packet Traffic in Wireshark
![image](https://github.com/user-attachments/assets/5118e430-4071-452d-97b5-4ed6a0ffc601)
Look at the Wireshark capture. You should see SSHv2 protocol traffic labeled as **"Encrypted packet"** — confirming secure communication between devices.

---

### 12. Filter and View DHCP Packets
![image](https://github.com/user-attachments/assets/f1d295e8-635f-4a62-8aba-1e54fba4fe5b)
In Wireshark, use the **filter bar** to enter `dhcp`. This lets you isolate and examine Dynamic Host Configuration Protocol (DHCP) request and acknowledgment packets.

---
### 13. Apply UDP Port Filter to Isolate DHCP Traffic
![image](https://github.com/user-attachments/assets/f3512797-5df5-4bcb-8ca1-937a583414a0)
In Wireshark, enter the filter `udp.port == 67 || udp.port == 68` to focus only on DHCP traffic. This helps validate the exchange between client and server.

---

### 14. Save the Packet Capture File
![image](https://github.com/user-attachments/assets/b43a34c3-57f7-4620-8818-d75e975b4c00)
After capturing DHCP packets, save the capture session by selecting **File > Save As**, then name your file (e.g., `dhcp.pcap`) and choose a save location.

---

### 15. Confirm or Skip Saving Before Restarting
![image](https://github.com/user-attachments/assets/91921ef0-3258-49ed-b65a-31c2d4ccc42c)
If restarting the capture, Wireshark will prompt you to save. You may click **"Continue without Saving"** to skip or **"Save before Continue"** if you need the data.

---

### 16. Observe Full DHCP Handshake in Wireshark
![image](https://github.com/user-attachments/assets/8ad74040-ecfe-4dbf-9304-65bea7429d7c)
Use Wireshark to verify the full DHCP handshake: **Release**, **Discover**, **Offer**, **Request**, and **ACK** packets. This confirms that your DHCP process is functioning properly.

---

### 17. Execute DHCP Script in PowerShell
![image](https://github.com/user-attachments/assets/564d46cf-1c04-4c3a-a14d-a00fde77f2f6)
Run your DHCP batch script from the `C:\ProgramData` directory. This will release the old IP and request a new one. Use `ipconfig /release` followed by `ipconfig /renew` to see the new address assigned.

---

### 18. Capture DNS Traffic in Wireshark
![image](https://github.com/user-attachments/assets/d68a554e-4870-436f-b9e8-7eba1280a2ab)
Continue monitoring traffic in Wireshark to view DNS queries and responses. Look for standard query packets to confirm that name resolution is working (e.g., responses from Microsoft or cloud services).

---

### 19. Confirm DNS Query Responses in Wireshark
![image](https://github.com/user-attachments/assets/d2db0bd3-c818-4f6f-afd2-17c4b5e8f4ae)
Continue using Wireshark to validate DNS query and response traffic. Confirm successful domain name resolutions by checking for resolved IP addresses in the Info column.

---

### 20. Use PowerShell to Run `nslookup` Commands
![image](https://github.com/user-attachments/assets/9f79d1d6-77ed-4701-a9f4-50a40c3b8d6f)
In PowerShell, use `nslookup` to resolve domain names like `disney.com` and `pixar.com`. Verify that IP addresses are returned, indicating that DNS resolution is successful.

---

### 21. Trigger an HTTPS Security Warning
![image](https://github.com/user-attachments/assets/16ab0822-0942-4ffc-9181-ff2d89562f21)
Attempt to access a domain by IP in the browser. A privacy warning (e.g., “Your connection isn’t private”) will appear due to certificate name mismatch, which is expected when accessing by IP.

---

### 22. Observe Ongoing DNS Query Activity
![image](https://github.com/user-attachments/assets/4901f4a2-00d8-4d5a-98a0-ef78bd747e36)
Wireshark continues capturing standard DNS query and response packets. Confirm that name resolution is ongoing and includes traffic to services like Microsoft, Bing, and Azure.

---

### 23. Analyze TLS and TCP Traffic to a Target Host
![image](https://github.com/user-attachments/assets/bfc7912c-e253-4633-881e-8e5704a901a0)
TLSv1.2 and TCP packets are captured from the source to 125.105.25.178. These show encrypted application data flowing over secured channels. Look for proper handshake completion and consistent stream traffic.

---

### 24. Analyze TLSv1.2 Traffic for Secure Communication
![image](https://github.com/user-attachments/assets/9ff43898-410f-4605-83c7-af5b11195b40)
TLSv1.2 and TCP packets are captured between the client and 125.105.25.178. This indicates encrypted traffic over HTTPS. Look for signs of a successful TLS handshake and continued secure stream activity.

---

### 25. Review All Resources Within the Resource Group
![image](https://github.com/user-attachments/assets/24ad47e0-50d9-4cc4-a706-f76bdc6ffb15)
Navigate to your Azure portal and view the contents of the `RG-Network-Activities` resource group. Confirm that all lab-related resources (VMs, networks, IPs) are accounted for and ready for cleanup.

---

### 26. Delete the Resource Group to Clean Up
![image](https://github.com/user-attachments/assets/24ad47e0-50d9-4cc4-a706-f76bdc6ffb15)
Click **Delete resource group**, confirm the name, and proceed. This will permanently remove all listed resources, completing the network protocols lab and restoring your environment.

---


---





![image](https://github.com/user-attachments/assets/e06a9188-a10c-4125-91ce-874128293e0a)

























<img width="1900" height="867" alt="lab clean up deleting resource groups and VM's" src="https://github.com/user-attachments/assets/4f56c5e9-81dc-42ce-88ef-5dbfe7d2cb32" />











