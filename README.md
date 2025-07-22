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

</p>
<p>
# 🚀 Git & GitHub Installation Guide

This guide explains how to install Git, configure GitHub, and verify everything is working properly for use in cloud/networking lab environments such as Azure VM setups.

---

## 🧰 Prerequisites

- Administrator access to your machine (Windows, macOS, or Linux)
- Internet connection
- A GitHub account: [Sign up here](https://github.com/join)

---

## 🪟 Windows Installation

1. **Download Git for Windows:**
   - [https://git-scm.com/download/win](https://git-scm.com/download/win)

2. **Run the Installer:**
   - Use default settings unless you have a specific need.
   - Ensure these options are selected:
     - "Git from the command line and also from 3rd-party software"
     - "Use bundled OpenSSH"
     - "Checkout Windows-style, commit Unix-style line endings"

3. **Verify Installation:**
   ```bash
   git --version
</p>
<br />

<p>
<img width="1880" height="865" alt="creating a virtual machine lab 2 " src="https://github.com/user-attachments/assets/49ee5509-6320-4641-83f6-06095e547cfc" />

</p>
<p>
# 📦 Git & GitHub Installation Instructions (for Windows 10 VM in Azure)

This guide provides step-by-step instructions to install Git on a Windows 10 Virtual Machine and connect it to GitHub, making it ready for version control and project collaboration.

---

## 🖥️ Step 1: Download Git for Windows

1. Go to the official Git website:
   👉 [https://git-scm.com/download/win](https://git-scm.com/download/win)

2. The download should begin automatically.

---

## ⚙️ Step 2: Install Git

1. Run the downloaded `.exe` installer.
2. Go through the setup using default settings, unless customization is needed.
3. Ensure the following key options are selected:
   - **Use Git from the command line and also from 3rd-party software**
   - **Use bundled OpenSSH**
   - **Checkout Windows-style, commit Unix-style line endings**

4. Complete the installation and click **Finish**.

---

## ✅ Step 3: Verify Git Installation

Open **Command Prompt** or **PowerShell** and run:

```bash
git --version
</p>
<br />

<p>
<img width="1876" height="842" alt="creating virtual machines number 2, linux virtual machine" src="https://github.com/user-attachments/assets/4bca1d0f-d63a-448c-8f98-d69798a19b09" />

</p>
<p>
## ✅ Virtual Machines Deployment Status

As part of the Azure Network Protocols Lab, two virtual machines have been deployed successfully in the same resource group.

### 🚀 Deployment Summary

| VM Name                                | OS              | Status     | Notes                      |
|----------------------------------------|------------------|------------|----------------------------|
| `CreateVm-MicrosoftWindowsDesktop...`  | Windows 10       | ✅ Complete | Used for Wireshark, RDP    |
| `CreateVm-canonical.0001-com-ubuntu...`| Ubuntu 22.04 LTS | ⏳ In Progress | For SSH, ICMP, DNS testing |

### 🔧 Details

- **Resource Group:** RG-Network-Activities  
- **Purpose:**
  - **Windows VM:** For RDP, Remote Desktop, Wireshark capture, PowerShell tools  
  - **Ubuntu VM:** For ping tests, SSH traffic observation, DNS/DHCP tests  

---

> ℹ️ Once the Ubuntu VM finishes deploying, both VMs will be configured on the **same Virtual Network and Subnet** for inter-VM traffic monitoring using Wireshark.
</p>
<br />



<img width="1904" height="857" alt="as you see above, we have created 2 virtual machines on the same network" src="https://github.com/user-attachments/assets/73904d40-737d-4f97-a064-13943447e30c" />

## ✅ Virtual Machines Deployment Status (Updated)

Both virtual machines have been successfully deployed and are now running in Azure. These will be used to complete the network protocol analysis lab (ICMP, SSH, RDP, DNS, and DHCP testing).

### 🔒 Active Virtual Machines

| VM Name             | OS             | Status  | Location      | IP Address        | Size           |
|---------------------|----------------|---------|---------------|-------------------|----------------|
| `win10-vm`          | Windows 10     | Running | Canada Central| 20.203.121.85     | Standard_D2s_v3 |
| `ubuntu-vm`         | Ubuntu Server  | Running | Canada Central| 20.203.121.80     | Standard_D2s_v3 |

> Both VMs are assigned public IP addresses and are within the same resource group and region.

---

### 🛠️ Next Steps

- ✅ Test connectivity between VMs (ping/ICMP)
- ✅ Install and configure **Wireshark** on Windows VM
- ✅ SSH into Ubuntu VM from Windows VM
- ✅ Capture and analyze ICMP, SSH, DNS, and DHCP traffic
- 🔄 Push lab scripts, captures, and notes to this GitHub repo

---

### 📁 Repo Purpose

This repository serves as a version-controlled documentation and evidence base for:

- Azure VM provisioning steps  
- Network protocol traffic analysis  
- Security group/firewall configuration  
- Cleanup automation steps

<img width="1889" height="864" alt="opening the network security group to my obunto vm  using   disabiling (inbound) ICMP traffic" src="https://github.com/user-attachments/assets/4297eb85-fdc9-4f00-9ed0-d0369a900520" />

## 🔐 Configuring Network Security Group (NSG) for Ubuntu VM

As part of the Azure lab setup, we configured inbound security rules to control network traffic to the Ubuntu VM. This step is essential to allow services such as SSH, ICMP (ping), and application-specific traffic.

### 🧱 NSG Configuration Details

- **NSG Name:** `linux-vm-nsg`
- **Scope:** Applied to the Ubuntu VM network interface
- **Location in Azure Portal:**  
  `Virtual machines → linux-vm → Networking → Network security group`

---

### ➕ Adding an Inbound Security Rule

We initiated the creation of a new inbound security rule to allow all traffic for testing purposes:

| Setting         | Value                  |
|----------------|------------------------|
| **Source**      | Any                    |
| **Source port** | * (Any)                |
| **Destination** | Any                    |
| **Destination port** | * (Any)           |
| **Protocol**    | Any                    |
| **Action**      | Allow                  |
| **Priority**    | Custom (lower is higher priority) |
| **Name**        | `DenyAnyCustomAnyInbound` |
| **Description** | Open rule for full traffic testing |

> ⚠️ **Important Note:** This rule should only be used temporarily during lab testing. For production environments, always restrict traffic using least-privilege principles (e.g., allow only port 22 for SSH).

---

### 🛠️ Next Steps

- Test **ping (ICMP)** from Windows VM to Ubuntu VM  
- Establish **SSH connection** from Windows to Ubuntu  
- Analyze traffic using **Wireshark**

---

### 📌 Best Practices Reminder

- Remove or tighten overly permissive rules after testing  
- Monitor NSG logs for unexpected access attempts  
- Use tags or service-specific ports when possible

<img width="1901" height="835" alt="network security group ubuntu vm is using   disabiling inbound ICMP traffic" src="https://github.com/user-attachments/assets/0acec414-0ff2-4e09-878c-e935bd2265e1" />

## 🔐 NSG Inbound Security Rules for `linux-vm-nsg`

This section documents the current inbound security rules applied to the Ubuntu VM in Azure through the associated Network Security Group (NSG).

### 📋 Current Rules Overview

| Priority | Name                          | Port Range | Protocol | Source       | Destination | Action |
|----------|-------------------------------|------------|----------|--------------|-------------|--------|
| 100      | `DenyAnyCustomAnyInbound`     | *          | Any      | Any          | Any         | Deny   |
| 65000    | `AllowVnetInBound` (Default)  | *          | Any      | VirtualNetwork | VirtualNetwork | Allow |
| 65001    | `AllowAzureLoadBalancerInBound` | *       | Any      | AzureLoadBalancer | Any      | Allow |
| 65500    | `DenyAllInBound` (Default)    | *          | Any      | Any          | Any         | Deny   |

> ℹ️ **Note:** The custom rule `DenyAnyCustomAnyInbound` with a priority of 100 overrides the default rules and **blocks all inbound traffic**.

---

### 🚨 Implication

Due to the high-priority deny rule (`DenyAnyCustomAnyInbound`), **all inbound connections are currently being blocked**, including:
- SSH (port 22)
- ICMP (ping)
- Any custom application traffic

---

### ✅ Recommendation

To proceed with testing protocols like SSH and ICMP between the Ubuntu and Windows VMs, you should:
- Temporarily disable or delete the `DenyAnyCustomAnyInbound` rule
- Or create **higher-priority allow rules** for specific traffic (e.g., SSH)

Example allow rule for SSH:

| Setting         | Value            |
|----------------|------------------|
| Priority        | 99               |
| Port            | 22               |
| Protocol        | TCP              |
| Source          | Any              |
| Destination     | Any              |
| Action          | Allow            |
| Name            | `Allow-SSH-Inbound` |

---

### 🛠️ Next Steps

- Add or adjust inbound rules to permit necessary test traffic
- Validate traffic flow using **Wireshark**
- Document any rule changes and their impact

<img width="1900" height="867" alt="lab clean up deleting resource groups and VM's" src="https://github.com/user-attachments/assets/d5077078-af21-4dce-b789-47d2dc1f415d" />

## 🧹 Lab Cleanup: Deleting Azure Resource Group

After completing all virtual machine testing and network traffic analysis, the final step is to **delete the resource group** to clean up all associated Azure resources.

---

### 🗂️ Resource Group Targeted for Deletion

- **Name:** `RG-Network-Activities`
- **Region:** Canada Central
- **Resources Contained:**  
  - Windows VM  
  - Ubuntu VM  
  - Virtual Network  
  - Network Security Groups  
  - Public IPs  
  - NICs and Disks

---

### 🛑 Confirmation Prompt

The Azure portal displays a confirmation message requiring manual input of the resource group name to proceed with deletion:

> _"Deleting this resource group and its dependent resources is a permanent action and cannot be undone."_

You must type:














