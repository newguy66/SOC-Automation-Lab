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
  


### Tools Used

- Draw.io
- Wazuh
- TheHive
- Shuffle
- VirtualBox
- Sysmon
  

### Steps

- First I laid out the Lab diagram, visualizing the flow of traffic and noting the steps the lab will take

  ![image](https://github.com/user-attachments/assets/090bde27-860c-40cd-8614-bb93e16001f1)

- After spinning up two instances of Ubuntu Server, I installed Wazuh and TheHive and configured them on my VLAN so they will communicate to each other

  ![image](https://github.com/user-attachments/assets/11abf1f7-0f6d-4a64-8193-2f25167bd976)
  ![image](https://github.com/user-attachments/assets/aeb7534d-d263-4846-bb62-1198d7ce88ee)

- I then ensured Sysmon was running and checked Wazuh for proper collection of data by deploying Mimikatz on my Windows 10 VM

  ![image](https://github.com/user-attachments/assets/d7fff846-9632-4a0f-9229-f0bb4a4dad64)

- I configured an alert to trigger when Mimikatz is run, even if the name has been changed, by making it look for the original file name and verified that it works by renaming Mimikatz to kiwiclub.exe and re-running it

  ![image](https://github.com/user-attachments/assets/869da7c7-7675-4c16-b46b-70d61c1e8150)

- On Shuffle, I created a workflow to collect the Wazuh alert and trigger a webhook, which I then used to run a parsed SHA256 hash through VirusTotal

  ![image](https://github.com/user-attachments/assets/3fd20895-ec94-4376-9728-85196032118d)

- This was then piped to TheHive, in order to create alerts and email notifications
