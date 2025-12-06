# Honeypot-Sentinel-Lab


## Objective


This labs purpose was to create a monitored honeypot in order to gain hands on experience with building structures in Azure and ingesting and analyzing logs with Sentinel
### Skills Learned


- Basic Azure architecture building
- Building and linking a log repository 
- KQL queries
- Adding Location data to enrich logs and see attacker locations
- 

### Tools Used


- Microsoft Azure to build the necessary infrastructure
- Microsoft Sentinel

## Steps
To begin I needed to create an free Azure account.

Once this was completed, I first began by creating a Resource group which would hold all my virtual infrastructure.
<img width="1229" height="37" alt="image" src="https://github.com/user-attachments/assets/08b938be-a30d-4602-93f0-0dce55af7511" />


The next step was to create a virtual network. I left all the settings default.
<img width="1440" height="53" alt="image" src="https://github.com/user-attachments/assets/d0498bee-bb04-4255-addc-8394b79fce5d" />


I then began setting up the virtual machine. I had to do some troubleshooting as Windows 11 wouldnt work due to zone restrictions so I went with Windows 10.
I placed the virtual machine inside the virtual network which are both in the resource group I created at the start.
<img width="804" height="49" alt="image" src="https://github.com/user-attachments/assets/2bce8acb-e2bd-4ab9-b4d7-105891eb1687" />

I then edited the inbound rules on the network security group to enable all traffic to all ports which would allow attackers to scan and attempt to gain access in turn giving me logs to check.

<img width="1289" height="419" alt="image" src="https://github.com/user-attachments/assets/2ad20a97-173f-4de1-84fc-e34fcc47fa43" />


