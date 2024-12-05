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
- Ubuntu Server 24.04

<h2>High-Level Steps</h2>

- Create 2 Virtual Machines (VM), one Windows and one Linux, on the same Virtual Network (VNet).
- Establish a Remote Desktop Connection to the Windows Virtual Machine (windows-vm).
- Install [Wireshark](https://www.wireshark.org/).
- Open Wireshark and begin unfiltered packet capture.

<p>
<img src="https://github.com/user-attachments/assets/e39eebe2-7af4-4517-8875-9d4aa5d9c7bb" height="80%" width="80%" alt="High-Level Steps Reference Image"/>
</p>

<h2>Actions and Observations</h2>

- Filter Wireshark for ICMP (Internet Control Message Protocol).
- Retrieve linux-vm private IP address and ping it from the Command Line Interface(CLI = Powershell(Win), Terminal(Mac), or Bash(Lin)).
- Observe the network traffic in Wireshark and CLI.

<p>
<img src="https://github.com/user-attachments/assets/6ce8a734-f615-485d-98c2-2eaa3e0a175c" height="80%" width="80%" alt="ICMP Filtered in Wireshark and Network ping"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
