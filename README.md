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


# Azure Virtual Machines & ICMP Traffic Analysis Lab

This lab consists of three parts: creating Windows and Linux virtual machines (VMs) in Azure, and analyzing ICMP traffic using Wireshark, and Configuring a firewall.

## Part 1: Create Virtual Machines

🔗 [Go to Azure Portal](https://portal.azure.com/)

### Steps:
1. **Create a Resource Group**
2. **Create a Windows 10 Virtual Machine (VM)**
   - While creating the VM:
     - Select the previously created Resource Group
     - Allow it to create a new Virtual Network (VNet) and Subnet
3. **Create a Linux (Ubuntu) VM**
   - While creating the VM:
     - Select the same Resource Group and **Virtual Network** as the Windows VM  
       > ⚠️ The Virtual Network **MUST** be the same!
   - Authentication type: Username/Password
4. **Ensure both VMs are in the same Virtual Network / Subnet**
5. **End the lab, but keep both VMs for Part 2**

---

## Part 2: Observe ICMP Traffic

🔗 [Return to Azure Portal](https://portal.azure.com/)

### Steps:
6. If using macOS, install **Microsoft Remote Desktop**
7. Use Remote Desktop to connect to your **Windows 10 VM**
8. Within the Windows 10 VM, install **Wireshark**
9. Open Wireshark and **start packet capture**
10. In Wireshark, apply a filter for:
11. Retrieve the private IP address of the **Ubuntu VM (`linux-vm`)**
12. From the Windows 10 VM:
 - Open Command Line or PowerShell
 - Ping a public website (e.g., `www.google.com`)
 - Observe ping requests and replies in Wireshark

 ## Part 3: Configuring a firewall 
 
(network security group)
13. Git & Version Control Basics
- Understand what Git is and how it differs from GitHub
- Be able to:
  - Clone a repository: `git clone`
  - Commit changes: `git commit -m "message"`
  - Push changes to remote: `git push`
  - Pull updates from remote: `git pull`

14. Command Line Proficiency
- Use CLI tools such as:
  - Windows PowerShell
  - Linux Bash
- Execute scripts and navigate files via terminal

15. GitHub Platform Familiarity
- Create and manage GitHub repositories (public or private)
- Use issues, pull requests, forks, and branches effectively
- Navigate GitHub web UI and integrate with tools like GitHub Desktop or VS Code

16. Scripting and Automation
- Write and store reusable scripts in Bash, PowerShell, or Python
- Understand file structures and configuration management

17. Remote Systems Access
- Use `ssh` for accessing remote Linux servers
- Use Remote Desktop Protocol (RDP) for accessing Windows VMs
- Configure firewall rules or NSGs in cloud platforms

18. Cloud Fundamentals
- Experience deploying virtual machines (VMs) on platforms like:
  - Microsoft Azure
  - AWS or GCP (optional but useful)
- Know basic networking: VNet, Subnet, NSG, and IP management

19. Network Traffic Analysis (Optional but Valuable)
- Use tools like **Wireshark** to capture and analyze:
  - ICMP traffic (ping)
  - SSH connections
  - DHCP/DNS queries

20. Documentation Best Practices
- Maintain clear README.md files
- Use GitHub for documenting and version-controlling lab steps and results

21.Operating System Proficiency
- Navigate and operate both:
  - Windows (PowerShell, Command Prompt)
  - Linux (Bash shell)
- Basic file management and permissions handling

22. Networking & Protocols Knowledge
- Understand and work with protocols such as:
  - ICMP (ping)
  - SSH (tcp/22)
  - DHCP
  - DNS
  - RDP (tcp/3389)
- Use networking tools like `ipconfig`, `nslookup`, `ping`, `ssh`

23. Packet Capture & Analysis
- Install and use **Wireshark** to:
  - Apply filters (e.g., `icmp`, `tcp.port == 3389`)
  - Analyze live packet streams
  - Interpret protocol-level communication

24. Remote Access & VM Management
- Use **Remote Desktop (RDP)** to access Windows VMs
- Use **SSH** to connect to Linux VMs
- Handle private IP addressing and secure authentication

25. ☁️ Cloud Platform Experience
- Work with cloud services (e.g., Microsoft Azure) to:
  - Deploy and configure VMs
  - Manage Resource Groups and Virtual Networks
  - Configure Network Security Groups (NSGs) and firewall rules
  - Perform lab cleanup to avoid charges

26. Documentation & Repository Management
- Write and maintain README.md files for labs/projects
- Document lab steps, results, and configurations using markdown
- Use GitHub to share, track, and version technical work

27. Critical Thinking & Troubleshooting
- Diagnose issues using command-line tools and packet inspection
- Understand protocol behaviors (e.g., why RDP generates constant traffic)
- Follow best practices for cloud cost control and security
  
---

## Tools & Requirements

- Azure account with permissions to create VMs
- Microsoft Remote Desktop (if on macOS)
- Wireshark installed on Windows 10 VM
- Basic understanding of network protocols (ICMP)

---

## Notes

- This lab is intended for educational purposes and should be used within a controlled virtual environment.

<h2>Actions and Observations</h2>

<p>
<img width="1897" height="866" alt="creating Azure virtual machine lab 2" src="https://github.com/user-attachments/assets/af2a197b-49c4-4e71-acf5-b10fac6242df" />

## 🖥️ Azure VM Creation - Ready to Begin

The Azure portal currently shows **no virtual machines deployed**. You are at the **Virtual Machines dashboard**, ready to create a new VM.
- No VMs listed
- "Create" button is available to launch VM setup

### 🔜 Next Step
Click **"Create"** to start configuring a new virtual machine (OS, size, region, authentication, and network settings).

<img width="1904" height="857" alt="as you see above, we have created 2 virtual machines on the same network" src="https://github.com/user-attachments/assets/197d994e-1953-4e71-aced-ddbcbe27750d" />

## 🖥️ Virtual Machines Deployed

Two virtual machines are now active in the Azure environment.

### ✅ VM Overview

| Name          | OS             | Status  | Region          | IP Address       |
|---------------|----------------|---------|------------------|------------------|
| win10-vm      | Windows 10     | Running | Canada Central   | 20.202.168.85     |
| ubuntu-vm     | Ubuntu Server  | Running | Canada Central   | 20.202.127.180    |

Both VMs are ready for lab activities including traffic monitoring, protocol testing, and connectivity validation.


<img width="1889" height="864" alt="opening the network security group to my obunto vm  using   disabiling (inbound) ICMP traffic" src="https://github.com/user-attachments/assets/616f75de-4f8d-49b8-99ef-abcd444a9e44" />

## NSG Configuration in Azure – Inbound Security Rules

![Azure Portal - Add Inbound Security Rule](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This screenshot displays the **Azure Network Security Group (NSG)** configuration process, specifically the **inbound security rule setup** for a virtual machine named `linux-vm` running in the `Canada Central` region.

The user is in the process of adding a new **inbound security rule** to allow specific traffic into the VM for lab-related purposes such as protocol testing, traffic monitoring, and connectivity validation.

### Key Elements Displayed:
- The NSG is associated with `linux-vm-nsg`, which is tied to an **Ubuntu Server**.
- The **Add inbound security rule** pane is open.
- Configuration fields include:
  - **Source:** Any
  - **Source port ranges:** *
  - **Destination:** Any
  - **Destination port ranges:** 22 (SSH)
  - **Protocol:** TCP
  - **Action:** Allow
  - **Priority:** Customizable
  - **Name and Description:** Not fully visible in the screenshot

- Current activity shown at the bottom confirms: `SSH (port 22) is allowed`.

---

### Steps That Led to This Point:

1. **Deployed a Virtual Machine**
   - A Linux-based virtual machine (Ubuntu Server) was deployed in Azure, located in `Canada Central`.

2. **Created or Assigned a Network Security Group (NSG)**
   - During VM creation or afterward, a **Network Security Group** was attached to manage traffic rules for the VM’s network interface or subnet.

3. **Navigated to NSG Settings**
   - From the VM's **Networking** tab or the NSG blade directly, the user accessed the **Inbound security rules** section.

4. **Initiated a New Rule**
   - Clicked on **"Add inbound port rule"** to configure access permissions.
   - Configured the rule to allow **SSH traffic (TCP Port 22)**, which is necessary for secure remote access to Linux VMs.

---

### Purpose of This Configuration

This step ensures secure, rule-based traffic flow to the virtual machine. Allowing TCP traffic on port 22 enables administrators to:
- Remotely connect to the Ubuntu server using SSH
- Perform lab activities like protocol testing and traffic monitoring
- Validate end-to-end connectivity for networking and security exercises

Proper NSG configuration is critical for maintaining both accessibility and security in cloud-based virtual environments.

<img width="1901" height="835" alt="network security group ubuntu vm is using   disabiling inbound ICMP traffic" src="https://github.com/user-attachments/assets/ee0f19a7-8636-4a03-9a88-96aa038eddee" />

## Viewing Inbound Security Rules – NSG for Ubuntu VM

![Azure Portal - NSG Inbound Rules for linux-vm-nsg](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This screenshot shows the **Inbound Security Rules** for a **Network Security Group (NSG)** named `linux-vm-nsg`, which is attached to an Ubuntu virtual machine in Azure. This view displays the current access control rules that govern allowed and denied traffic to the VM.

### Key Elements Displayed:
- NSG Name: `linux-vm-nsg`
- The NSG is actively being managed from within the **Azure Portal**.
- The **Inbound security rules** tab is selected.
- A rule allowing SSH traffic (`Port 22`, `Protocol TCP`, `Action: Allow`) is visible and active.
- Additional default rules for services like RDP, HTTPS, and platform-level access are listed with varying priorities.
- The bottom status pane confirms:
  - ✅ **SSH (port 22) is allowed (priority 1000)**

---

### Steps That Led to This Screen:

1. **Deployed an Ubuntu Virtual Machine**
   - A virtual machine running Ubuntu was provisioned in Azure using the VM wizard.
   - Region selected: `Canada Central`.

2. **Assigned/Created a Network Security Group (NSG)**
   - An NSG named `linux-vm-nsg` was either created during VM setup or applied afterward via the Networking tab.

3. **Navigated to NSG Configuration**
   - Opened the NSG directly or through the VM’s “Networking” settings.
   - Accessed the **Inbound security rules** section to manage permitted traffic.

4. **Added a Custom Rule**
   - A new rule was created to allow **TCP traffic on port 22**, which is required for **SSH access** to the VM.
   - Priority was set (e.g., 1000) to ensure this rule took precedence over broader deny rules.

---

### Purpose of This Step

This screen confirms that:
- The NSG is correctly configured to allow remote administrative access to the VM.
- Security rules are actively enforced, controlling which ports and protocols can reach the VM.
- The environment is ready for secure connections, testing, or further protocol-specific monitoring.

Proper NSG configuration is essential to strike a balance between access and security in cloud environments, especially during networking or cybersecurity labs.

<img width="1900" height="867" alt="lab clean up deleting resource groups and VM's" src="https://github.com/user-attachments/assets/4f56c5e9-81dc-42ce-88ef-5dbfe7d2cb32" />

## Network Protocol Testing Lab – Full Workflow Overview

![Azure Portal - Resource Group Deletion Confirmation](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This lab series demonstrates the full cycle of deploying, configuring, testing, analyzing, and cleaning up an Azure-based network environment involving both **Windows** and **Linux (Ubuntu)** virtual machines. The final screenshot confirms that the resource group `RG-Network-Activities` is being deleted, signaling the completion of all lab tasks.

---

### ✅ Objectives Achieved:

- Deployed two VMs in a shared virtual network (Windows 10 and Ubuntu)
- Analyzed traffic behavior across ICMP, SSH, DHCP, DNS, and RDP protocols
- Modified NSG rules to simulate real-time network conditions
- Used Wireshark for live packet analysis
- Cleaned up all resources to prevent charges

---

### 🛠️ Full Step-by-Step Breakdown:

#### 🖥️ Part 1 – Virtual Machine and Network Setup

1. Log in to the Azure Portal: [https://portal.azure.com](https://portal.azure.com)
2. Create a new **Resource Group** for the lab environment.
3. Deploy a **Windows 10 Virtual Machine**:
   - Assign it to the resource group
   - Allow it to create a new **Virtual Network** and **Subnet**
4. Deploy a **Linux (Ubuntu) VM**:
   - Select the same Resource Group and Virtual Network as the Windows VM
   - Ensure both machines are on the same subnet

---

#### 🌐 Part 2 – Packet Capture and Protocol Behavior (using Wireshark)

5. Use **Remote Desktop** to connect to the Windows VM.
6. Install **Wireshark** on the Windows VM.
7. Start a packet capture session.

##### ICMP (Ping) Test:
8. Filter for **ICMP traffic only** in Wireshark.
9. Ping the private IP of the Ubuntu VM from the Windows VM.
10. Observe ICMP traffic in Wireshark.

##### Simulating Firewall Blocking:
11. Disable ICMP in the Ubuntu VM's NSG settings.
12. Attempt the ping again and confirm no response in Wireshark.
13. Re-enable ICMP in the NSG.
14. Ping once more and confirm packets are seen again.

##### SSH Protocol Observation:
15. From the Windows VM, open a terminal and SSH into the Ubuntu VM.
16. Filter for **SSH traffic only** in Wireshark.
17. Observe the constant packet flow during SSH session.
18. Type a few commands, then exit the SSH session.

##### DHCP Behavior:
19. Filter for **DHCP traffic** in Wireshark.
20. Use PowerShell to request a new IP address using `ipconfig /renew`.
21. Observe DHCP request/acknowledgment traffic in Wireshark.

##### DNS Behavior:
22. Filter for **DNS traffic** in Wireshark.
23. Use `nslookup` to query IP addresses of domains like `google.com` or `disney.com`.
24. Confirm the DNS queries are captured and visible in the packet capture.

##### RDP Analysis:
25. Filter for **RDP traffic only** (`tcp.port == 3389`) in Wireshark.
26. Observe consistent, non-stop packet traffic as the RDP session remains active—even when idle.
   - This demonstrates how RDP maintains constant communication to deliver a real-time screen stream.

---

### 🧹 Final Cleanup

27. Close the Remote Desktop session to the Windows VM.
28. Delete the resource group (`RG-Network-Activities`) from the Azure Portal.
   - This action permanently removes all associated resources (VMs, NSGs, Public IPs).
   - A confirmation window is shown prior to deletion.

---

### 🧠 Summary

This hands-on network lab provided a full walkthrough of:
- Deploying and networking Azure VMs
- Observing real-time traffic using Wireshark
- Manipulating NSG rules to simulate access control
- Interpreting common protocols in use across Windows/Linux platforms
- Practicing cloud resource hygiene by performing proper teardown

The exercise effectively bridges foundational networking concepts with practical Azure-based cloud infrastructure.

