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

<P> STEP 1: Create two resource groups named Active Directory Lab and Client-1</P>

![RESOURCEGROUP](https://github.com/user-attachments/assets/6c276e64-4f97-41b1-aabc-b64e560375a7)


<br />

<p>
STEP 2: Now Create the Virtual Machines, client-1 with Windows 10 Pro and active directory with Windows Server 2022. Make sure to write your credientials for the log in. 
</p>

<br />

![NETWORKVM](https://github.com/user-attachments/assets/4c858ff4-41d9-4c23-bfff-7ca156e6689a)

![Screenshot 2025-02-10 102013](https://github.com/user-attachments/assets/711a9783-8431-47e1-97c6-64ff5c809ff2)


<br />


![CLIENT1](https://github.com/user-attachments/assets/92e197e6-2861-4eb7-84e5-7eee1a2a3477)


![SERVERIMAGE](https://github.com/user-attachments/assets/e59705ff-b27b-42b3-96b0-b5ff59d826b5)

<br />
<p>
STEP 3: Once done configure the IP address setting in the NIC to 'STATIC'. The image below showcases where to find the Network Interface Card. Select the VM with active directory and open the networking> click on Network Settings.
</p>
<br />

![Screenshot 2025-02-06 042039](https://github.com/user-attachments/assets/64057762-36fc-4edd-9203-015b49bf3031)

<br />

<p> STEP 4: Hover over to the green tab "NIC".</p>


![Screenshot 2025-02-06 042110](https://github.com/user-attachments/assets/fdd91368-a6f8-4dc2-8acf-17ba97a989af)

<p> STEP 5: Next select settings> IP configuration> and click the blue ipconfig1 in this table change IP setting to Static.</p>
<p>This will ensure that the private IP doesnt change.</p>


![Screenshot 2025-02-06 042144](https://github.com/user-attachments/assets/92ed45d6-9446-4326-88ed-893e50316178)

<p> STEP 6: Open Remote Desktop from the home tab. Copy the IP address from active directory azure. Once logged in> open the Run command and type wf.msc We will be turning off windows firewall to allow inbound traffic into the DNS SERVER <p/>

![Screenshot 2025-02-06 042228](https://github.com/user-attachments/assets/094f254c-8b63-4dd4-bb4c-cdb4b5b03197)

![Screenshot 2025-02-06 042304](https://github.com/user-attachments/assets/dd7f5252-698d-43cb-93b5-1d0e84a60186)

<br />
<p>STEP 7: In windows defender firewall CLICK "WINDOWS DEFENDER FIREWALL PROPERTIES" and turn off </p>

![Screenshot 2025-02-06 042355](https://github.com/user-attachments/assets/656f78b7-616f-4e46-acb0-30e500240ef5)


![Screenshot 2025-02-06 042521](https://github.com/user-attachments/assets/6a867a47-bf0f-44c9-98a6-ae7ee4d87073)

<p>STEP 8: Go back to azure and copy the PRIVATE IP address from the Active Directory VM Next we will connect client-1 computer into the server by using the dns option. In the NIC settings click on DNS Server and paste it by selection the custome option. Once saved RESTART both virtual machines to update their configurations</p>

![clientNIC](https://github.com/user-attachments/assets/1e69ccd8-9b40-44db-9d56-8adc02a4c509)


![CLIENTDNSSERVER](https://github.com/user-attachments/assets/327adafb-3880-4d16-b1ec-2d4c5d9f645e)


<p>STEP 9: Ensure that both computers have a network connectivty with each other by using the powershell application. Type in SSH the command PING and if the configurations were done correctly the image below should appear. <p>

![Screenshot 2025-02-06 042716](https://github.com/user-attachments/assets/76cb8112-e536-4e8c-be6f-33c6b50dc922)

![Screenshot 2025-02-10 100150](https://github.com/user-attachments/assets/b8c4dc31-4a24-4f61-9161-c4166ff631f5)

<p>For more network data use the command IPCONFIG /all, to check the IP address and the private IP, but as well to check the DNS SERVER IP if it matches</p>


![Screenshot 2025-02-06 042804](https://github.com/user-attachments/assets/3f966d22-c490-4f7e-a082-d4d6b69d6d00)









