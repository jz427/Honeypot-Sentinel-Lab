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

**Once this was completed, I first began by creating a Resource group which would hold all my virtual infrastructure.**
<img width="1229" height="37" alt="image" src="https://github.com/user-attachments/assets/08b938be-a30d-4602-93f0-0dce55af7511" /> <br/><br/>


**The next step was to create a virtual network. I left all the settings default.**
<img width="1440" height="53" alt="image" src="https://github.com/user-attachments/assets/d0498bee-bb04-4255-addc-8394b79fce5d" /> <br/><br/>


**I then began setting up the virtual machine. I had to do some troubleshooting as Windows 11 wouldnt work due to zone restrictions so I went with Windows 10.
I placed the virtual machine inside the virtual network which are both in the resource group I created at the start.**
<img width="804" height="49" alt="image" src="https://github.com/user-attachments/assets/2bce8acb-e2bd-4ab9-b4d7-105891eb1687" /> <br/><br/>

**I then edited the inbound rules on the network security group to enable all traffic to all ports which would allow attackers to scan and attempt to gain access in turn giving me logs to check.**
<img width="1289" height="419" alt="image" src="https://github.com/user-attachments/assets/2ad20a97-173f-4de1-84fc-e34fcc47fa43" /> <br/><br/>

**After doing this I needed to change a few firewall settings in the virtual machine itself. I opened up Windows Defender Firewall and turned off the firewall for the domain profile, private profile, and public profile. After doing this the VM is opened to attackers.**
<img width="548" height="597" alt="image" src="https://github.com/user-attachments/assets/19b0a7d4-b8d2-4ade-bfc5-1319fc5a5b3a" /> <br/><br/>

**I next created a log analystics workspace to hold all the logs from my Azure VM.**
<img width="1209" height="397" alt="image" src="https://github.com/user-attachments/assets/985ab053-87b0-4c9d-b283-bd656cbc238d" /> <br/><br/>

**Now to create the Sentinel instace which the log analytic workspace will sit in.**
<img width="1016" height="357" alt="image" src="https://github.com/user-attachments/assets/e92f1761-dc01-472e-97e3-07435c8dc31a" /> <br/><br/>


**The next step is to link the log analytic workspace and the VM. In sentinel I add the Windows security events connector**
<img width="1044" height="401" alt="image" src="https://github.com/user-attachments/assets/46d9c481-a431-4c08-be0b-6e68a0c48d71" /> <br/><br/>

**After this I create a data collection rule which will forward the VM logs to the log analystic workspace and the Sentinel instance.**
<img width="1408" height="344" alt="image" src="https://github.com/user-attachments/assets/4575dafd-bd95-4ab8-937f-4ca9f52ba4c2" /> <br/><br/>

**To then confirm the machine is opened and being scanned, I checked the log function in the log analytical workspace. I used the KQP query of "SecurityEvent" and as you can see below attackers are using different account names to try and get in.**
<img width="1812" height="851" alt="image" src="https://github.com/user-attachments/assets/8fb79b2d-710d-4fd5-9c0c-3b47aa4a412a" /> <br/><br/>

**I then used a public csv of common attacker locations including ip ranges, country name, latitutde and longitude etc, and uploaded it to enrich the logs and aid me in showing the attackers locations in an easier way.**
csv -> https://drive.google.com/file/d/13EfjM_4BohrmaxqXZLB5VUBIz2sv9Siz/view?pli=1
**I uploaded the csv into the Sentinel instace and added it under watchlist. As you can see below the logs now show the city and country.**
<img width="1536" height="825" alt="image" src="https://github.com/user-attachments/assets/6ac4eb1a-ddd8-4e7b-af88-05c72e120fda" /> <br/><br/>

**The last step was to create a visual aid, one that you may see in a SIEM. I created an attack map to show the locations of the attackers. I copied a public json file and uploaded this into a Microsoft Defender workbook.**
json ->https://drive.google.com/file/d/1ErlVEK5cQjpGyOcu4T02xYy7F31dWuir/view
**As you can see below most of the attacks were from the UK and Australia.**
<img width="1088" height="357" alt="image" src="https://github.com/user-attachments/assets/6dab7c51-b3f9-4cfa-b8db-b7956fee0240" /> <br/><br/>

**I enjoyed this lab as it gave me hands on expereince with builidng in Azure and setting up Sentinel and ingesting Logs**




