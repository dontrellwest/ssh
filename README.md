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

<h2>What is SSH (Secure Shell Protocol)?</h2>
•	SSH is a secure protocol for remotely logging into and managing computers over a network. It encrypts all transmitted data, preventing unauthorized access and interception.
<br>
•	System administrators frequently use SSH to access remote servers securely, making it a safer alternative to older protocols like Telnet, which send data in plaintext.
<br>
•	Port Number: 22 (TCP)
<br>
•	In Wireshark: Filtering for ssh will show SSH traffic, but since SSH encrypts communication, you won’t see the actual commands—only the fact that an SSH session is active.
<br>

<h2>Actions and Observations</h2>

<h3>Step 1 - Log Into the Windows 10 VM</h3>
	•	If you are not already connected, use Remote Desktop to access your Windows 10 VM in Azure.

<h3>Step 2 - Start Capturing SSH Traffic in WiresharkVM</h3>

  •	Open Wireshark and start a new packet capture. <br>
	•	In the Wireshark filter bar, enter: ssh <br>
	•	This filters the capture to show only SSH traffic (TCP port 22). <br>
 
 <h3>Step 3 - Establish an SSH Connection to the Ubuntu VM</h3>
 	•	In PowerShell, initiate an SSH session by typing: ssh labuser@<Ubuntu_VM_Private_IP> <br>
	•	Replace <Ubuntu_VM_Private_IP> with the private IP address of your Ubuntu VM. <br>
	•	When prompted, enter the password for the labuser account. <br>

 <h3>Step 4 - Interact with the SSH Session and Observe Traffic</h3>

  •	Run basic Linux commands, such as:  <br>
      - ls <br>
      - pwd <br>
      - whoami <br>
	•	As you type, you should see SSH traffic appearing in Wireshark, confirming encrypted communication between the Windows and Ubuntu VMs.

 
<h3>Step 5 - Close the SSH Session</h3>
	•	To exit the SSH session, type: exit <br>
 	•	Press [Enter], and the SSH connection will close. <br>

<img width="1512" alt="Step 5a - SSH" src="https://github.com/user-attachments/assets/87a769b9-da10-4142-b94d-0cae56e622f1" />
<img width="1512" alt="Step 5b - SSH" src="https://github.com/user-attachments/assets/0ab654a4-225f-4198-8c22-29b30e60ddbf" />
<img width="544" alt="Step 5c - SSH" src="https://github.com/user-attachments/assets/044b1028-7958-424c-9397-3bb27f0ab289" />


<h2>Summary & Significance</h2>

<h3>What You Did</h3>
	•	Used Wireshark to capture and filter SSH traffic (TCP port 22). <br>
	•	Established an SSH connection from the Windows 10 VM to the Ubuntu VM using PowerShell. <br>
	•	Observed the encrypted SSH traffic in Wireshark while interacting with the remote Linux system. <br>
	•	Closed the SSH session properly using the exit command. <br>

<h3>Why This Matters</h3>
	•	SSH is a secure protocol for remote administration – understanding how it works is essential for managing cloud resources and Linux systems. <br>
	•	Wireshark helps analyze SSH activity – though SSH encrypts data, capturing the packets still allows you to verify connections, detect unauthorized access attempts, and troubleshoot connectivity. <br>
	•	Filtering specific protocol traffic (like SSH) is a key skill in network security – it helps administrators and security professionals monitor and analyze network behavior efficiently. <br>
 <br>
By completing this tutorial, you’ve gained hands-on experience with using SSH in Azure, analyzing encrypted traffic in Wireshark, and understanding how secure remote connections work in a cloud environment
