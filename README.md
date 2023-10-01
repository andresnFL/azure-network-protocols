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

- Windows 10 (22H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Set up resources
- Observe traffic through different ports
- Clean up lab

<h2>Actions and Observations</h2>

<p>
<p align="center"> <img src="https://imgur.com/aI6ktaj.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
Welcome to Microsoft Azure! After creating a free account, create a new resource group. Then create 2 virtual machines, 1 with Windows 10 (22h2) and 1 with Ubuntu. Make sure they're in the same resource group. Use network watcher to ensure connection, if necessary. 
</p>
<br />

<p>
<p align="center"><img src="https://imgur.com/ngrOqlq.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> <p align="center"><img src="https://imgur.com/FDlKKKr.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
(ICMP) After connecting to Virtual Machine 1, go into any browser and search for Wireshark. Download the appropiate version. After accessing Wireshark, filter for ICMP traffic and plug in the Private IP address of Virtual Machine 2 (PIC 1). Observe traffic. Go back to Powershell and engage a nonstop ping (PIC 2).
</p>
<br />

<p>
<p align="center"><img src="https://imgur.com/QaIM6qE.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
(SSH) In Wireshark, filter for SSH traffic. In powershell, "SSH Into" the Virtual Machine 2 Private IP address. When prompted, log in with credentials and observe SSh traffic in Wireshark. Type "exit" and press enter in Powershell to leave. 
</p>
<br />

<p>
<p align="center"><img src="https://imgur.com/KSlbHYX.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>

(DHCP) Filter for DHCP traffic in Wireshark. Use IPConfig /renew issue a new IP address. Observe traffic.
</p>
<br />

<p>
<p align="center"><img src="https://imgur.com/nQ4DfpI.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> 
</p>
<p>

(DNS) Filter for DNS traffic in Wireshark. Use command nslookup with any website you'd like (Try www.google.com or www.disney.com). Observe traffic and IPs in both Powershell and Powershell.
</p>
<br />

<p>
<p align="center"><img src="https://imgur.com/BGudZSy.png" height="70%" width="70%" alt="Disk Sanitization Steps"/> 
</p>
<p>

(RDP) Remember that RDP is recognized as tcp.port == 3389 in Wireshark. Filter for RDP and observe the constant flow of traffic. This is the constant noise between both your computer and the Virtual Machine. It's always active in the background to ensure connection. This is the end of this experiment, please do not forget to delete this resource group and practice when you can!
</p>
<br />




