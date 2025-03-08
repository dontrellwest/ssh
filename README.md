<h1>Inspecting SSH Connections in Wireshark Using PowerShell and Azure VMs</h1>
Objective: Show how to initiate an SSH connection between an Azure Windows VM and a Linux VM using PowerShell, capture the encrypted traffic in Wireshark, and understand how SSH packets appear in a network capture.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Powershell
- Various Command-Line Tools
- Network Protocol SSH
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)
- Ubuntu Server 22.04


<h2>Actions and Observations</h2>

<br>
<h3>Step 1 - SSH (Secure Shell Protocol)</h3>
<br>
•	SSH is a secure protocol for remotely logging into and managing computers over a network. It encrypts all transmitted data, preventing unauthorized access and interception.
<br>
•	System administrators frequently use SSH to access remote servers securely, making it a safer alternative to older protocols like Telnet, which send data in plaintext.
<br>
•	Port Number: 22 (TCP)
<br>
•	In Wireshark: Filtering for ssh will show SSH traffic, but since SSH encrypts communication, you won’t see the actual commands—only the fact that an SSH session is active.
<br>
<img width="1512" alt="Step 5a - SSH" src="https://github.com/user-attachments/assets/1674d3a6-b241-45c8-851b-33c764dfba6b" />
<img width="1512" alt="Step 5b - SSH" src="https://github.com/user-attachments/assets/28183f48-cd89-42da-9a78-71cd9ad6230a" />
<img width="544" alt="Step 5c - SSH" src="https://github.com/user-attachments/assets/5c754751-2354-4adf-a25a-35c7e4fc541c" />
