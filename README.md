<h1>#Active Directory Infrastructure Set Up 

<p align="center">
  
![download (1)](https://github.com/user-attachments/assets/07458653-d995-4134-98ce-f9a2854ea0eb)

</p>

This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Windows Powershell 86x
- Windows Firewall
- DNS Server
- Network Interface Card

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create 2 VM in azure with different images (Operating Systems)
- Next configure the IP settings of AD to be "STATIC", ensures unchanged IP
- Next you will configure the windows firewall of Active Directory as off, allows data traffic inbound
- Copy AD private IP address and connect it with Client-1 computer by going to the NIC>DNS SERVER and pasting the private IP
- Check connectivity with Powershell with commands 

<h2>Deployment and Configuration Steps</h2>

![RESOURCEGROUP](https://github.com/user-attachments/assets/6c276e64-4f97-41b1-aabc-b64e560375a7)

<P>Create two resource groups named</P>
</p>

<br />
![NETWORKVM](https://github.com/user-attachments/assets/4c858ff4-41d9-4c23-bfff-7ca156e6689a)


<p>
Now Create the Virtual Machines, client-1 with Windows 10 and active with Windows Server 2022
</p>
<br />

![SERVERIMAGE](https://github.com/user-attachments/assets/e59705ff-b27b-42b3-96b0-b5ff59d826b5)


![CLIENT1](https://github.com/user-attachments/assets/92e197e6-2861-4eb7-84e5-7eee1a2a3477)

<br />

<p>

</p>
<br />
