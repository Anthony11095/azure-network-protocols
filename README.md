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


