<h1>SIEM SET UP IN MICROSOFT AZURE (SENTINEL) TO ANALYZE FAILED RDP LOGIN ATTACKS </h1>

 ###

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
<b>Step1.	Create an AZURE subscription <br/>
<b>Objective:</b> Establish the foundational Azure environment for the SIEM deployment. <br/>
<b>Actions:</b> <br/>
 - Creating an Azure subscription to initiate the project. <br/>
<b>-------------------------------------------------------------------------  <br/>
>Sign up for Azure with your Microsoft Account. <br/>
<img src="https://imgur.com/XE558Ob.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<br/>
<b>-------------------------------------------------------------------------  <br/>
>Setup Suceessful to  initiate project: <br/>
<img src="https://i.imgur.com/fsz0UMj.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<br/>
<b>Step2. Virtual Machine Configuration:  <br/>
<b>Objective:</b> Set up a controlled Virtual environment for monitoring and analyzing security events. <br/>
<b>Actions:</b> <br/>
- Create a Virtual Machine in Azure. <br/>
- Deactivate external and Windows firewalls to intentionally expose the VM. <br/>
<b>-------------------------------------------------------------------------  <br/>
 >Click on Virtual Machine from the home page or search for VM on resource panel to Create Resource <br/>
<img src="https://imgur.com/UEiAWpX.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<br/>
<b> > On the Basics configuration tab Create a New Resource Group <br/>
<img src="https://imgur.com/pckrksf.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<br/>
<b>-------------------------------------------------------------------------  <br/>
<b> > Confirm License and click next to Network panel <br/>
<img src="https://imgur.com/pckrksf.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br /> 
<b>-------------------------------------------------------------------------  <br/>
<b> > Create a Network Security Group <br/>
<img src="https://imgur.com/8SivjL8.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Click OK then Click Review & Create to Deploy VM- <br/>
<img src="https://imgur.com/VTHZH4p.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Deployment Completed, Click on Go to Resource <br/>
<img src="https://imgur.com/Pj9Tf0w.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>Step 3: Log Repository Creation  <br/>
<b>Objective:</b> Create a centralized hub for ingesting and storing logs. <br/>
<b>Actions:</b> <br/>
 - Develop a Log Analytics Workspace in Azure to serve as the log repository. <br/>
<b>-------------------------------------------------------------------------  <br/>
<b> > Click on Log Analytics Workspaces from Resource panel  <br/>
<img src="https://imgur.com/XuP0p2D.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > create log analytic workspace - it purpose is to inject logs into the VM-  <br/>
<img src="https://imgur.com/9yzRzVV.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Click on Create to Create Workspace-  <br/>
<img src="https://imgur.com/N3V5Das.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br /><b>Step 4: Security Center Configuration.  <br/>
<b>Objective:</b> Facilitate log gathering and enhance threat visualization. <br/>
<b>Actions:</b> <br/>
- Set up Azure Security Center. <br/>
- Enable Defender plan and data collection. <br/>
- Connect Log Analytics Workspace to the virtual machine. <br/>
<b>-------------------------------------------------------------------------  <br/>
 <b> > Enable and Install Agent for Cloud security-this gives the system the ability to collect logs from virtual machines and store them in the log analytics workspace  <br/>
<img src="https://imgur.com/YRuT76e.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Enable Defender plans-Click Servers ON <br/>
<img src="https://imgur.com/989yuWf.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Set Data Collection to All Events <br/>
<img src="https://imgur.com/mnz96mn.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Next Connect the Log Analytics Workspace to the VM for threat visualization. <br/>
<img src="https://imgur.com/W5dYxS0.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>Step 5: Azure Sentinel Integration  <br/>
<b>Objective:</b> Orchestrate and analyze collected logs using Microsoft's cloud-native SIEM solution. <br/>
<b>Actions:</b> <br/>
 - Integrate Azure Sentinel within Azure. <br/>
 - Map attacker data. <br/>
 - Utilize PowerShell for log transformation.  <br/>
<b>-------------------------------------------------------------------------  <br/>
<b> > Create Sentinel by connecting Workspace <br/>
<img src="https://imgur.com/WPqhieR.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Workspace connected to VM Successfully <br/>
<img src="https://imgur.com/Riw5cVW.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>Step 6: Log Analysis on VM  <br/>
<b>Objective:</b> Investigate potential security incidents within the VM. <br/>
<b>Actions:</b> <br/>
- Access the VM using RDP. <br/>
- Open Event Viewer to analyze event logs. <br/>
<b>-------------------------------------------------------------------------  <br/>
<b> > Access the VM through Remote Desktop Protocol (RDP) using the public IP address.  <br/>
<img src="https://imgur.com/NdDl5Wt.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Enter System credentials we had previously configured on the VM. <br/>
<img src="https://imgur.com/L46EhxJ.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
 <b>-------------------------------------------------------------------------  <br/>
<b> > RDP Logged on VM Succesfully <br/>
<img src="https://imgur.com/4wpc0TV.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
 <b>-------------------------------------------------------------------------  <br/>
<b> > Open event Viewer viewer from START Menu and click on Security <br/>
<img src="https://imgur.com/2aDqpUA.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>-------------------------------------------------------------------------  <br/>
<b> > Analyze Events with Audit Failure, NOTE the Task Category as Logon failure observe the source Network Address(IP) <br/>
<img src="https://imgur.com/aXGzZP3.png" height="70%" width="70%" alt="Azure SIEM Steps"/> <br/>
<br />
<b>Step 7: Vulnerability Testing  <br/>
<b>Objective:</b> Temporarily expose the VM to potential threats for testing and validation. <br/>
<b>Actions:</b> <br/>
- Disable the virtual machine's firewall temporarily. <br/>
- Verify visibility by pinging from a personal computer.
<br/>
 <b>-------------------------------------------------------------------------  <br/>
 <b> > Turn Off Window Firewall on VM <br/>
<img src="https://imgur.com/EIjQOvG.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
 <b>-------------------------------------------------------------------------  <br/>
<b> > Verify system visibility by pinging from a personal computer. <br/>
<img src="https://imgur.com/XIqKgwm.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br/>
<b>Step 8: Geolocation Analysis. <br/>
<b>Objective:</b> Gather data on the geographical origin of potential attackers. <br/>
<b>Actions:</b> <br/>
 - Execute a PowerShell script using the Geolocation API. <br/>
<br/>
<b> <br/>
 <b>-------------------------------------------------------------------------  <br/>
<img src="https://imgur.com/k6dh3Y9.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>Step 9: Custom Log Creation  <br/>
<b>Objective:</b> Enhance log analysis capabilities by creating custom logs. <br/>
<b>Actions:</b> <br/>  
- Create custom logs in the Log Analytics Workspace. <br/>
- Copy logs from RDP to the local machine for utilization in Azure. <br/>
- Use KQL to set log collection paths and extract relevant fields. <br/>
<b>-------------------------------------------------------------------------  <br/>
 <b> > Create Custom Log from Log analytics workspace Tables </b>
<img src="https://imgur.com/8auioLe.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<b>-------------------------------------------------------------------------  <br/>
 <b> > Copy logs generated from RDP to the local machine-Preview </b>
<img src="https://imgur.com/YrxSItr.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
 <b>-------------------------------------------------------------------------  <br/>
 <b> > Set the log collection path  C:/ProgramData/ ??? same path name(if 'u' wish) </b>
<img src="https://imgur.com/OvcUJl5.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
  <br />
 <b>-------------------------------------------------------------------------  <br/>
 <b> > Run Kusto Query Language (KQL) to extract relevant fields from the Raw Log Files. </b>
<img src="https://imgur.com/3wwm1es.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
  <br /> 
<b>Step 10: Azure Sentinel Mapping.  <br/>
<b>Objective:</b> Visualize security incidents through Azure Sentinel. <br/>
<b>Actions:</b> <br/> 
- Configure maps within Azure Sentinel. <br/>
- Utilize workbooks and KQL scripts for threat management. <br/>
- Create visual representations of security incidents. <br/>
<b>-------------------------------------------------------------------------  <br/>
 <b> > Next, We'd Go to Microsoft Sentinel Through Resource and Add New Workbooks from Sentinel menu </b>
<img src="https://imgur.com/jE39Y6P.png" height="70%" width="70%" alt="Azure SIEM Steps"/> <br/>
<br />
 <b>-------------------------------------------------------------------------  <br/>
 <b> > On the New Workbook Remove all Default Widgets and customize to Choice </b>
<img src="https://imgur.com/LWwU985.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br />
<br />
<b>-------------------------------------------------------------------------  <br/>
 <b> > Add KQL Query on New workbook <br/>
<img src="https://imgur.com/aboaPtF.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
 <br />
<b>-------------------------------------------------------------------------  <br/>
 <b> > Run the Added Query to create the logs Visualization </b>
<img src="https://imgur.com/NRp1CzP.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<b>-------------------------------------------------------------------------  <br/>
 <b> > Customize Visualization by Changing from Default(set by Query) to Map on map setting </b>
<img src="https://imgur.com/LWwU985.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<b>-------------------------------------------------------------------------  <br/>
 <b> > Failed RDP Map Visualization Generated Successful. </b>
<img src="https://imgur.com/tqydM38.png" height="70%" width="70%" alt="Azure SIEM Steps"/>
<br/>
<b>-------------------------------------------------------------------------  <br/>
<br/>
<h2>SUMMARY</h2>
 <p align="justify">
<b>  This Azure SIEM system, which makes use of Azure Sentinel and related capabilities, provides a comprehensive solution for monitoring, analyzing, and responding to security events. The purposeful exposure of the VM enables controlled testing and validation of the effectiveness of the SIEM architecture. This project provides a basis for organizations looking to improve their cloud cybersecurity posture. This Azure SIEM setup takes a methodical approach, beginning with the construction of an Azure subscription and a Virtual Machine, progressing to the creation of a Log Analytics Workspace, and concluding with the integration and visualization of security events using Azure Sentinel. Each step adds to the creation of an all-encompassing and controlled environment for monitoring, assessing, and responding to possible security risks within the Azure cloud. <br/>
<br/>
<p align="center">
<b>------------------------------------------------------------------------- <br/>
<b>-------------------------------------------------------------------------  <br/>
 <br/>
<b> * * * THANK YOU FOR READING THROUGH. FEEL FREE TO DROP YOU COMMENTS ANYTIME. * * * <br/>
<br/>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
