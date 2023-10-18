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

<h2>High-Level Steps</h2>

- Create VMs on Azure and download Wireshark
- Ping VM2 from VM1 and see it on Powershell and Wireshark
- Create and toggle ICMP deny rule on Azure and see it on Wireshark and Powershell
- SSH from VM1 to VM2 and see it on Wireshark
- Renew IP address of VM and see it on Wireshark
- Look up IP address of websites and see it on Wireshark
- See RDP traffic between computer and VM on Wireshark

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/urKDP7t.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
Our first step is to create our resources: VM1 and VM2 on Microsoft Azure and download Wireshark. Wireshark will allow us to inspect the traffic between the virtual machines. Filtering for ICMP, we can reduce all the traffic data we are seeing to just the VMs.
</p>
<br />

<p>
<img src="https://i.imgur.com/8m4CLfG.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
Using Powershell, we can ping from VM1 to VM2 on the private network and see it in both Powershell and Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/6oJgdNK.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
While testing for ICMP traffic, we can go to Microsoft Azure and create a security rule for VM2 to deny any ICMP traffic. When this rule is created, we can see it being executed in Wireshark and Powershell, and it can also be toggled off and on.
</p>
<br />

<p>
<img src="https://i.imgur.com/zHZ3g0M.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we’re going to look at SSH traffic and filter for this on Wireshark. On Powershell, we can SSH from VM1, and log into VM2, and this data can be seen on Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/cFE47in.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
After checking for SSH traffic, we are going to look at DHCP traffic. We can do this by filtering on Wireshark and typing the “ipconfig /renew” command. This will give our VM a new IP address. This can be seen on Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/2x4QSNl.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
We can also filter for DNS on Wireshark and observe this traffic by going on Powershell and typing the “ns lookup” command. We can use that command to look up the IP address of various websites like Google or Disney.
</p>
<br />

<p>
<img src="https://i.imgur.com/YhxVDGi.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lastly, we are looking at RDP traffic. This protocol is what is being used for the remote desktop connection between our computer and the VM, so there will be a non-stop amount of data being shown in Wireshark.
</p>
<br />
