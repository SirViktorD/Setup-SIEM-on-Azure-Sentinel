<h1>SIEM SET UP IN MICROSOFT AZURE (SENTINEL) TO ANALYZE FAILED RDP LOGON ATTACKS </h1>

 ### [YouTube Demonstration]

<h2>Description</h2>
In the ever-changing realm of cybersecurity, creating a solid Security Information and Event Management (SIEM) system is critical. This project explains how to create a cloud-native security setup for Azure Sentinel (SIEM) and connect it to a live virtual machine that acts as a honey pot. The configuring of a SIEM infrastructure on Microsoft Azure. We will watch real-time attacks (RDP Brute Force) from all around the world. I'll then develop a custom PowerShell script and using a third-party API to find the attacker's geolocation data and plot it on an Azure Sentinel Map!
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>ipgeolocation.io: IP Address to Geolocation API</b>

<h2>Environments Used </h2>

- <b>VM Windows 10</b> (21H2)

<h2>Project Step-by-Step walk-through:</h2>

<p align="center">
<b>1.	Create an AZURE subscription: <br/>
<b>Objective:</b> Establish the foundational Azure environment for the SIEM deployment. <br/>
<b>Actions:</b> - Creating an Azure subscription to initiate the project.
<br/>
<img src="https://imgur.com/XE558Ob.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br/>
  Setup Suceessful to  initiate project: <br/>
<img src="https://i.imgur.com/fsz0UMj.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<br/>
<b>2. Virtual Machine Configuration:  <br/>
<b>Objective:</b> Set up a controlled Virtual environment for monitoring and analyzing security events. <br/>
<b>Actions:</b> - Create a Virtual Machine in Azure. <br/>
- Deactivate external and Windows firewalls to intentionally expose the VM.
<br/>
<img src="https://imgur.com/UEiAWpX.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
 Create New Resource Group <br/>
<br />
<br />
<img src="https://imgur.com/pckrksf.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
 Confirm License and click next to Network panel <br/>
<img src="https://imgur.com/pckrksf.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br /> 
  Create a Network Security Group: <br/>
<img src="https://imgur.com/8SivjL8.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
  Click OK then Click Review & Create to Deploy VM- <br/>
<img src="https://imgur.com/VTHZH4p.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Deployment Completed, Click on Go to Resource- <br/>
<img src="https://imgur.com/Pj9Tf0w.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Click on Log Analytics Workspaces from Resource panel-  <br/>
<img src="https://imgur.com/XuP0p2D.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
create log analytic workspace - it purpose is to inject logs into the VM-  <br/>
<img src="https://imgur.com/9yzRzVV.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Click on Create to Create Workspace-  <br/>
<img src="https://imgur.com/N3V5Das.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2>SUMMARY</h2>
- <b>This Azure SIEM system, which makes use of Azure Sentinel and related capabilities, provides a comprehensive solution for monitoring, analyzing, and responding to security events. The purposeful exposure of the VM enables controlled testing and validation of the effectiveness of the SIEM architecture. This project provides a basis for organizations looking to improve their cloud cybersecurity posture. This Azure SIEM setup takes a methodical approach, beginning with the construction of an Azure subscription and a Virtual Machine, progressing to the creation of a Log Analytics Workspace, and concluding with the integration and visualization of security events using Azure Sentinel. Each step adds to the creation of an all-encompassing and controlled environment for monitoring, assessing, and responding to possible security risks within the Azure cloud.
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
