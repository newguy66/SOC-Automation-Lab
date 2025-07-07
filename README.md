# SOC-Automation-Lab
SOC Automation Lab with Shuffle SOAR

## Objective
The purpose of this lab was to build a SOC Automation Lab, using Wazuh for SIEM and XDR, TheHive for Case Management, and Shuffle for SOAR capabilities, to mimic a real response environment.
  
### Skills Learned
- Create a lab diagram 
- Deploy multiple Ubuntu servers to host Wazuh and TheHive.
- Configure Servers and Endpoints to communicate on a VLAN
- Set up Wazuh to collect telemetry and trigger alerts
- Integrate SOAR capabilites into the Lab
- 


### Tools Used

- Draw.io
- Wazuh
- TheHive
- Shuffle
- VirtualBox
- Sysmon
  

### Steps

- First I laid out the Lab diagram, visualizing the flow of traffic and noting the steps the lab will take

- After spinning up two instances of Ubuntu Server, I installed Wazuh and TheHive and configured them on my VLAN so they will communicate to each other

- I then ensured Sysmon was running and checked Wazuh for proper collection of data by deploying Mimikatz on my Windows 10 VM

- I configured an alert to trigger when Mimikatz is run, even if the name has been changed, by making it look for the original file name and verified that it works by renaming Mimikatz to kiwiclub.exe and re-running it

- On Shuffle, I created a workflow to collect the Wazuh alert and trigger a webhook, which I then used to run a parsed SHA256 hash through VirusTotal

- 
