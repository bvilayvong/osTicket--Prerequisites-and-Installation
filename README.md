<img src="https://iili.io/dGyagHX.png">
<hr align="left" height="99%" width="99%"></hr>
 <h2>osTicket--Prerequisites-and-Installation</h2>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

<h3>Video Demonstration</h3>
<ul>
    <li><a href="https://www.youtube.com/watch?v=fWX1Lj-rOa0">YouTube: How to Install osTicket with Prerequisites</a></li>
</ul>
<hr align="left" height="99%" width="99%"></hr>
<h3>Environments and Technologies Used</h3>
<ul>
   <li>Microsoft Azure (Virtual Machines/Compute)</li>
   <li>Remote Desktop</li>
   <li>Internet Information Services (IIS)</li> 
</ul>
<hr height="99%" width="99%"></hr>
<h3>Operating Systems Used</h3>
<ul>
   <li>Windows 10 (21H2)</li>
</ul>
<hr align="left" height="99%" width="99%"></hr>
<h3>List of Prerequisites</h3>
<ul>
   <li>Microsoft Azure</li>
   <li>Virtual Machine</li>
   <li>osTicket Installation Files</li>

</ul>
<hr align="left" height="99%" width="99%"></hr>
<h3>Installation Steps</h3>
<p>
Open https//portal.azure.com
<br>Sign in to your Azure account
<br>Under the section Create a Resource Group, in Resource group* called RG-bv-osTicket
<br>Select Region*, to (Canada) Canada Central
<br>Click Review + Create, if Validation passed, Click Create. 
<br>In the search box, type in virtual machine. 

In Virtual machines, click + Create
<br>Under Project details, in Resource group*, select RG-bv-osTicket
<br>Under Instance details, in Virtual machine name*, type VM-osTicket
<br>In region*, Select (Canada) Canada Central
<br>In Image*, Select Windows 10 Pro version 22H2 - x64 Gen2 (free services eligible)
<br>In size*, select Standard_D4s_v3 - 4 vcpus, 16 GiB memory ($162.06/month)

In Administrator account:
<br>In username*, type bv-labuser
<br>In password*, type #Bv-12345678
<br>In Confirm password*, type #Bv-12345678

In Licensing:
<br>Check the box for "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights".
<br>Click Next for Disks. Click next for Networking. 

In Networking:
<br>Click Review + Create. If Validation passed, Click Create. 







</p>





<p>
Step 1: Connect to your Virtual Machine with Remote Desktop

Step 2: Install and Enable Internet Services (IIS) in Windows

Placeholder image
<img src="" height="80%" width="80%" alt="Disk Sanitization steps">
Lorem ipsum....
</p>
<p>
Placeholder image
<img src="">
Lorem ipsum....
</p>
<p>
Placeholder image
<img src="">
Lorem ipsum....
</p>



