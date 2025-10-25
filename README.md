<h1>SECURE VISION: SIEM & SOC PROJECT </h1>

Slide 1: Title

Title: Secure Vision

Subtitle: A Microsoft Sentinel–based SIEM & SOC Implementation

Tagline: “Empowering Intelligent Security Monitoring”
<br />
<br />



Slide 2: Project Overview


•	Objective: Develop a centralized security monitoring solution using Microsoft Sentinel.

•	Goal: Detect, investigate, and respond to security threats in real time.

•	Key Components:

o	Log collection & correlation

o	Threat detection

o	Incident response automation

o	SOC visibility


 
<h2>Description</h2>
Welcome to my SIEM & SOC Project

Secure Vision is a Security Information and Event Management (SIEM) project built using Microsoft Sentinel, designed to provide real-time monitoring, detection, and automated response to security incidents within an organization. The project focuses on building a centralized Security Operations Center (SOC) environment that enhances visibility, improves threat detection accuracy, and streamlines incident management.

In this repository, we were embarking on an intriguing cybersecurity journey. Our primary goal is to setup a Azure portal, a powerful cloud-based security information and event management (SIEM) solution and along side it. What makes this honeypot unique is that we intentionally make it super vulnerable to the vast expanse of the internet.

What’s then catch? We are going to monitor and log a myriad of attacks coming from different IP address located in various countries worldwide. These attacks will be tracked and analysed, and then real fun begins. We will take this data and visulaize it on a map, providing a real-time, geographical representation of the global cyber threat landscape.

In this project, our focus narrows down to examining failed to Remote Desktop(RDP) login attempts. These failed RDP logs will dissected, geolocated and ultimately placed on a map. The result? A visual representation of where all these attacks are originating from, giving us unique insights into the world of cybersecurity.


<h2>High level overview</h2>

<p align="center">

<img src="https://i.ibb.co/7NtFMZKY/re.png" height="80%" width="80%" alt="Activity Diagram"/>

In this project, we will guide you through a unique journey into the realm of cybersecurity. Here's a high-level overview of what to expect
<br />
<br />

  Azure Subscription Setup
  
Azure is Microsoft”s cloud computing platform.It is like a online data center that lets you use powerful computers, storage, database, networks, and many other services over the internet instead of buying or maintaining physical hardware.

Now, We buy our Azure subscription step by step

First and foremost, we'll set up an Azure subscription. The best part? It's free, and you'll receive 16,645 rupees in Azure credits to kickstart your project. 

Azure Sentinel Setup: Here comes the star of the show, Azure Sentinel! It's Microsoft's Security Information and Event Management (SIEM) solution, and we'll use it to create a dynamic map that visualizes data about various attackers. This map will show their country of origin, IP addresses, and more.

In our inaugural step, we're taking advantage of the Azure free account trial. By signing up for this free account, you'll receive a generous $200 credit that we'll utilize to kickstart our project. 



Step 1: CREATING A RESOURCE GROUP

First we goto the Microsoft azure portal and there we search Resource Group(RG),and then opening the resource group we have to create our own resource in that resource we have

Subscription: Azure subscription 1

Resource group name: RG-SOC-Lab

Region: (us) East us 2

RG Definition: Resource group Is a grouping of resources which is allow you to track the resources of a particular project

•	It is basic/First thing to create a VM

•	With the help of RG we can easily find them instead of searching every where.

<br />
<br />





<p align="center">
  
<img src="https://i.ibb.co/cKS3Qc9r/2025-09-15-15-28-20-Create-a-resource-group-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


  Step 2: Creating a Virtual Network

Here also same as it is goto search bar and search virtual network and we have to create it.

Subscription: Azure Subscription 1

Resource Group: RG-SOC-Lab

Virtual network name: Vnet-Soc-Lab

Region: (US) East US 2

IP Address: 10.0.0.0 – 10.0.0.255 (default)

•	Virtual network is the foundation for setting up secure communication in Azure.

•	All the resources like(Vm’s & databases…) are talk eachother securely.
 <br/>


<p align="center">
  
<img src="https://i.ibb.co/1JJBCGwy/2025-09-15-15-40-12-Create-virtual-network-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

•	After creating vnet it shows the image like these I can upload in the bottom how the deployment is completed successfully.

 <br/>
 <p align="center">
   
<img src="https://i.ibb.co/fGDkqstY/2025-09-15-15-49-31-Vnet-sco-lab-1757931314478-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

VM Creation

Step 2 : brings us to the creation of a pivotal component in our cybersecurity experiment. Once you have your Azure subscription all set up, simply head over to portal.azure.com to get started. At the top of the Azure portal, you'll find the 'Virtual Machine' option, This virtual machine will be sitting on the internet, fully exposed to the world, ready to pique the curiosity of individuals from various countries who will undoubtedly attempt to log into it once they discover its online presence.

Here's what you need to do: Click 'Create' and select 'Virtual Machine' on the left. We would create a new 'Resource Group,' essentially a logical grouping of resources in Azure that share the same lifespan. Then, for the name of our virtual machine,
When it comes to setting up a username and password, you can use any combination, but make sure you remember it because we'll need this information to log into the virtual machine later. Leave the rest of the settings as is, check the appropriate boxes, and hit 'Next.'

Moving to the 'Networking' section, under 'Network Security Group' (think of it as a firewall), we'll get into some advanced configurations. Here's the catch: We want to 'Allow all' in the firewall, creating a new rule that essentially opens the doors for anything on the public internet. To do this, we'll remove the default rule and craft our custom inbound rule.
 
This rule will permit all traffic to flow into the virtual machine. Set the destination port to '*', and allow any protocol. Set the action to 'Allow,' and assign it a low priority, like 100. You can name it something memorable, like 'danger any in.'

This setup is designed to make the virtual machine extremely discoverable. It's intended to respond to any kind of traffic – from TCP pings to ICMP pings – making it enticing and discoverable to anyone. While this approach might not be suitable for a production environment, it serves the purpose of our lab: to facilitate swift discovery and subsequent attacks. Once these configurations are in place, you're ready to go. Click 'Review and Create,' and then 'Create' to initiate the creation of the virtual machine

Step 3: CREATING A VIRTUAL MACHINE

Here brings us to the creation of a pivotal component in our cybersecurity experiment.In the same search bar we search it as Virtual machine click it and we ready to create it.But here so many options from where we have to create it here I create Virtual machine (VM) in VMSS. I will shown in the below figure where I created.

  <br/>
   <p align="center">
     
<img src="https://i.ibb.co/NGMr9cL/VMSS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

VM Name: CORP-NET-EAST-1

Image: Windows 11Pro,Version 24hz-X64 Gen2

Username: ***

Password: ****

Virtual machine are created it is like a open server attackers easily hack them if the attacker attack them it don’t affect our real computer.

After the attack all the logs are collected in the log repository and all it is shown in the map we can saw in our next steps.

Main reasons are:

For testing and learning, Security, For Running multiple systems, hosting applications, Backup and recovery…

<br />
<br />
  <br/>

   <p align="center">
   
     
<img src="https://i.ibb.co/nqBDdkdm/93975877-c5cd-4b88-89a4-b0ea8a773bbd.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br /> 

<img src="https://i.ibb.co/N6q7SMqq/ED.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />

Step 4: CREATING INBOUND AND OUTBOUND SECURITY RULES

Inbound: These are the rules that define what kind of network traffic is allowed or denied to come into a resource.

Outbound: these rules are the network rules that control the traffic leaving your resource or system.

Here, We create  inbound rules intentionally for learning.

  Source - Any                              
  action – allow
  
  Source port range - *                        
  Priority - 100
  
  Destination – any                              
  Name – DANGER_AllowAnyCustomInbound

 <br/>
   <p align="center">
   
    
<img src="https://i.ibb.co/q3Sv8Xp1/2025-09-16-13-16-27-Add-inbound-security-rule-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Creating all these stuffs it shows in our priority list

 <p align="center">

<img src="https://i.ibb.co/Kz392k3s/2025-09-16-13-19-48-basic-Nsg-Vnet-sco-lab-nic01-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />

•	Next step we go to the virtual machine to disable the internal windows firewall.

•	In virtual machine we select CORP-NET-SOC-LAB-1 in that we select a public IP.


 <p align="center">

 <img src="https://i.ibb.co/27xwS2Hb/2025-09-16-13-23-36-Remote-Desktop-Connection.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

 <br />
 <br />

•	And then we go to Remote Desk (RDP) and there we copy the IP address and wait for connect it.

•	After connecting we enter our username and password it was already created in virtual network.

•	After it connect it directly goes to the RDP.

•	In case it does not connect in the RDP wf.msc (windows defender firewall properties) here in every tab we turnoff everything.

•	Then if we want to check whether virtual machine is connected or not .

•	Go for prompt command type  %  ping + IP address and it shows like these.


 <p align="center">

  <img src="https://i.ibb.co/353VYpmk/2025-09-22-12-58-59-Select-Command-Prompt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  <br />
  <br />

Finding Unknown Identity:

•	If we have any login failure or unknown user try to enter the virtual machine we have to saw in the RDP.

•	Simply go to the RDP type Event Viewer here we directly go to windows logs – security.

•	Here we see who are try to login and how many login attempts held and failed.



Step 5: CREATING LOG ANALYTICS WORKSPACE

Definition: A log Repository is like a digital record workbook that keeps track of everything happening in our virtual machine.

When we create a Log Analytics Workspace, it becomes our log repository.

Why we install it, Because instead of checking logs on each VM separately, all logs are stored in one place this saves our time and it also helps detect suspicious activities like failed logins, malware or brute-force attack. If something goes wrong (like a system crash or error), you can check the log repository to find out what happened and when. And it also used for monitoring and detect threats.

Subscription: Azure Subscription 1

RG: RG-SOC-Lab

Name: LAW-SOC-LAB-0000

Region: East us-2

After we created a log workstation it shows like below the diagram

 <p align="center">

  <img src="https://i.ibb.co/1Yb38bjX/2025-09-24-17-03-45-Microsoft-Log-Analytics-OMS-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  <br />
  <br />

Step 6: CREATING MICROSOFT SENTINEL

It is a security system in azure that collects logs from different sources analyse them and detects threats and can even respond automatically.

It is a cloud based SIEM & SOAR (security orchestration, automation and response) tool

It gathers logs and alerts from virtual machines, firewalls, networks, applications, and cloud services and all this data stored in log analytics workspace.

SIEM: Collects and analyses logs from multiple sources.

SOAR: Automates responses to security threats.

It basically connection between virtual machine and log analytics workspace.

Virtual machine --> Log Repository --> Sentinel

In the Microsoft Sentinel (MS) we have to install the security events because security events bring windows event logs (like failed logins, logouts, account changes and policy updates) from our VMs into sentinel. Helping us monitor, protect and respond to security threats effectively.


 <p align="center">
 
  <img src="https://i.ibb.co/k6hHDrGQ/2025-09-29-15-44-15-Content-hub-Microsoft-Defender.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  <br />
  <br />
  
After that we open VM and open CORP-NET-SOC-LAB-1_19bde5d9  here we go to setting + extension + applications here it shows no resources then we again go for security events here we select windows security events via azure monitoring agent (AMA) and connect it. shown in below diagram

<p align="center">
 
  <img src="https://i.ibb.co/574kTGr/2025-09-29-15-52-57-Microsoft-Defender.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

After that we create data collection rule why it is created is because basically it is used by the VM to forward Logs in to our Log analytics workspace which let us access them inside our SIEM. A DCR tells azure which logs and metrics to collect, from where, and where to store them it is like a data pipeline for monitoring and security systems.

Main reasons are to collect right logs, send data to the log repository, customize it. Without DCR sentinel can’t receive data from your VM. DCR act’s as a bridge between our VM and sentinel.

We create DCR to decide what data to collect from resources in VMs and send it to the log repository so tools like Microsoft’s Sentinel can easily analyse and detect security threats.


<p align="center">
 
  <img src="https://i.ibb.co/3YcbNsdW/2025-09-29-16-13-10-Data-Connector-Page-Microsoft-Defender.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  In these, name we created data collection rule. After creating we go to VM and again Setting + Extension + Application here it shows the name what we created. It shows in the below diagram.


<p align="center">

 
  <img src="https://i.ibb.co/x8LHGn0Q/2025-10-13-17-54-49-CORP-NET-SOC-LAB-1-19bde5d9-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  Now we see the logs, go to Log Analytics Workspace and click on the logs here we select Kql mode and here we type command called “SecurityEvent” and below the diagram we can see the bunch of logs.
  

  <p align="center">


  <img src="https://i.ibb.co/BHp2cvDn/2025-09-30-10-44-52-LAW-soc-lab-0000-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  And these like a giant spread sheet these logs have a lot of columns like time, channel, task, computer, account etc…  these all logs are forwarding to VM using azure monitoring agent from log analytics workspace.
  
By using KQl (Kusto Query Language) we see the logs what we actually want no need to see all the logs.

Next, we created a Watchlist in Microsoft Sentinel it is like a custom reference list that helps sentinel to compare incoming logs with known information, so it can quickly identify trusted users or attackers.

Here we store our own list of known malicious IP address, domains, users and now sentinel can compare incoming logs against this list and trigger alerts if a match is found.

We uploaded our own watchlist its name is geoip in these a bunch of random IP address, longitudes, latitudes, city name etc.. are there.


  <p align="center">

  <img src="https://i.ibb.co/836QnZ0/2025-09-30-11-48-58-Watchlist-Microsoft-Defender.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

And we created like above the diagram after uploading it take some time to upload in the watchlist after uploading its shows like these


 <p align="center">

  <img src="https://i.ibb.co/CpHThpkQ/2025-09-30-15-25-33-Microsoft-Sentinel-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

After uploading we go to log analytics workspace and in the logs we can type that  _GetWatchlist(“geoip”) and it gives the result.


 <p align="center">

  <img src="https://i.ibb.co/ksKTxKXm/2025-10-14-10-55-08-162-Cyber-Home-Lab-from-ZERO-and-Catch-Attackers-Free-Easy-and-REAL-Micros.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  Now we can type kql query to get some random login failure in our VM. 
  

  <p align="center">

  <img src="https://i.ibb.co/j9NbfwhC/2025-10-06-11-46-41-Microsoft-Sentinel-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  these are the failed login attempts in  security events in our VM. And our watchlist gives access that where the attacker come from and his longitude, city name, latitude etc…
  
In the above list we can take one particular IP address and what we actually want and we type a query in the logs what we want it gives the result below I uploaded the both query and result.


  <p align="center">

  <img src="https://i.ibb.co/mCqMFZsy/2025-10-06-12-06-20-Microsoft-Sentinel-Microsoft-Azure.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  And the result shows like these
  
    
  <p align="center">
  
  <img src="https://i.ibb.co/9k7cq01F/2025-10-16-17-42-32.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

Step 7: CREATING A MAP

Creating a map is the best thing in the azure and it is the last step we created it shows different of failed login all over the world.

How to create a map, First we go to microsoft sentinel and  there we go to workbook and there we select edit and edit what already there and now we can select new workbook and there we select the options called Add data source + Visualization. Here we created our map buy using a code that I uploaded in the below diagram.

But in my code I edited little bit in the code 9 I remove the comma ( , ) in the flower bracket ( } ). 
After editing these I get my failed login map.


<p align="center">
  
  <img src="https://i.ibb.co/B52yVFX3/2025-10-06-12-26-02-Untitled-Notepad.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />
  
After these it take sometimes to load the map and now we get our map


<p align="center">
  
  <img src="https://i.ibb.co/0y16rqr8/2025-10-06-12-33-53.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />
  
These is the map we created. And name is “Windows VM Attack Map”


  <p align="center">
  
  <img src="https://i.ibb.co/HDHWY1gq/2025-10-06-12-28-38-Workbook-Microsoft-Defender.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  

  <br />
  <br />

  These map will be change according to the time.

  




    
  
  
  
  


  

  

  




  

<!--
 diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
