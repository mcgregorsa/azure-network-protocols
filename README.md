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

- Initiate continuous ping (ping -t) from windows-vm to linux-vm.
- Open linux-vm Network Security Group(NSG) in Azure and add rule to disple inbound ICMP.
- Observe traffic in Wireshark and CLI.
- Delete NSG rule to re-enable ICMP traffic.
- Observe traffic in Wireshark and CLI.
- Stop ping by typing 'exit' in CLI.

<p>
<img src="https://github.com/user-attachments/assets/ebb48b06-dc8c-456b-a442-a92309dfd46e" height="80%" width="80%" alt="SSH Visuals"/>
</p>
<br />

- Filter Wireshark for SSH (Secure Shell).
  - Note: Secure Shell uses TCP Port 22.
- From windows-vm SSH into linux-vm using CLI.
  - command: ssh <username>@<private IP> example: ssh samlab2@10.0.0.5
- Observe SSH traffic.
- Change filter to tcp.port == 22.
  - This allows viewing the acknowledgement in Wireshark as the connection is exited.
- Exit SSH by typing 'exit' in CLI.

<p>
<img src="https://github.com/user-attachments/assets/74ca821e-2722-4a3c-86ef-7f4fa026088f" height="80%" width="80%" alt="SSH Observations"/>
</p>
<br />

- Filter Wireshark for DHCP (Dynamic Host Configuration Protocol).
  - Note: DHCP uses UPD Ports 67 and 68.
- Open Notepad and create a .bat file. See image for contents.
  - Save file as dhcp.bat
  - In explorer, view>hidden to see ProgramData folder.
  - Save .bat to that location.
- In CLI use 'cd' command to change directory to ProgramData folder. (see image.)
  - Use 'ls command to list contents and verify .bat location.
  - Run .bat using the command '.\dhcp.bat.
- The remote desktop connection will be lost and will reconnect as the IP is released and renewed.
- Observe the DHCP traffic in Wireshark of the release and renewal of the IP.

<p>
<img src="https://github.com/user-attachments/assets/f5bb27af-6d5a-4ca1-a806-eb28b60ee5f0" height="80%" width="80%" alt="DHCP Visuals"/>
</p>
