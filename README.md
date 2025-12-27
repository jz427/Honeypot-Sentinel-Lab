# Honeypot-Sentinel-Lab

This is a hands‑on cloud security project where I deployed a vulnerable Windows VM in Azure, exposed it to the internet, ingested logs into Microsoft Sentinel, enriched attacker data, and built a live attack map to visualize global intrusion attempts.


## Objective


This labs purpose was to create a monitored honeypot in order to gain hands on experience with building structures in Azure and ingesting and analyzing logs with Sentinel
### Skills Learned

- Designing basic Azure infrastructure (resource groups, VNets, VMs)<br/>
- Creating and linking Log Analytics Workspaces <br/>
- Enriching logs with geolocation data (IP ranges, country, latitude/longitude) <br/>
- Visualizing attacker activity using Sentinel Workbooks <br/>

### Tools Used

- Microsoft Azure to build the necessary infrastructure
- Microsoft Sentinel

## Lab Build Steps 
## Step 1. Create Azure Enviornment
- Create free Azure account <br/>
- Create resource group to hold infrastructure<br/>
- Build Virtual Network<br/>

<img width="1229" height="37" alt="image" src="https://github.com/user-attachments/assets/08b938be-a30d-4602-93f0-0dce55af7511" />
<img width="1440" height="53" alt="image" src="https://github.com/user-attachments/assets/d0498bee-bb04-4255-addc-8394b79fce5d" /> <br/><br/>



## Step 2. Deploy the Honeypot VM

- Attempted Windows 11 but switched to Windows 10 due to zone restrictions<br/>
- Placed the VM inside the virtual network and Resource Group<br/>
- Modified Network Security Group inbound rules to allow all traffic<br/>
- Disabled Windows Defender Firewall (Domain, Private, Public) to fully expose the VM<br/>

<img width="804" height="49" alt="image" src="https://github.com/user-attachments/assets/2bce8acb-e2bd-4ab9-b4d7-105891eb1687" /> <br/><br/>
<img width="1289" height="419" alt="image" src="https://github.com/user-attachments/assets/2ad20a97-173f-4de1-84fc-e34fcc47fa43" /> <br/><br/>
<img width="548" height="597" alt="image" src="https://github.com/user-attachments/assets/19b0a7d4-b8d2-4ade-bfc5-1319fc5a5b3a" /> <br/><br/>


## Step 3. Configure Logging

- Created a Log Analytics Workspace<br/>
- Deployed a Microsoft Sentinel instance connected to the workspace<br/>
- Added the Windows Security Events connector<br/>
- Created a Data Collection Rule to forward VM logs to Sentinel<br/>

<img width="1209" height="397" alt="image" src="https://github.com/user-attachments/assets/985ab053-87b0-4c9d-b283-bd656cbc238d" /> <br/><br/>
<img width="1016" height="357" alt="image" src="https://github.com/user-attachments/assets/e92f1761-dc01-472e-97e3-07435c8dc31a" /> <br/><br/>
<img width="1044" height="401" alt="image" src="https://github.com/user-attachments/assets/46d9c481-a431-4c08-be0b-6e68a0c48d71" /> <br/><br/>
<img width="1408" height="344" alt="image" src="https://github.com/user-attachments/assets/4575dafd-bd95-4ab8-937f-4ca9f52ba4c2" /> <br/><br/>



## Step 4. Validate Attacker Activity
- Run "SecurityEvent" to confirm brute force attempts on the exposed VM <br/>
<img width="1812" height="851" alt="image" src="https://github.com/user-attachments/assets/8fb79b2d-710d-4fd5-9c0c-3b47aa4a412a" /> <br/><br/>



## Step 5. Enrich Logs with Geolocation Data

- Imported a public CSV containing attacker IP ranges, countries, and coordinates<br/>
- Added it to Sentinel as a Watchlist<br/>
- Logs now displayed attacker city and country information<br/>

csv -> https://drive.google.com/file/d/13EfjM_4BohrmaxqXZLB5VUBIz2sv9Siz/view?pli=1
<img width="1536" height="825" alt="image" src="https://github.com/user-attachments/assets/6ac4eb1a-ddd8-4e7b-af88-05c72e120fda" /> <br/><br/>

**The last step was to create a visual aid, one that you may see in a SIEM. I created an attack map to show the locations of the attackers. I copied a public json file and uploaded this into a Microsoft Defender workbook.**
json ->https://drive.google.com/file/d/1ErlVEK5cQjpGyOcu4T02xYy7F31dWuir/view
**As you can see below most of the attacks were from the UK and Australia.**
<img width="1088" height="357" alt="image" src="https://github.com/user-attachments/assets/6dab7c51-b3f9-4cfa-b8db-b7956fee0240" /> <br/><br/>

**I enjoyed this lab as it gave me hands on expereince with builidng in Azure and setting up Sentinel and ingesting logs**




