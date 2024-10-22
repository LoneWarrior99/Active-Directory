## Setting up Virtual machines in Virtual Box

![image](https://github.com/user-attachments/assets/9b456635-e470-4dac-bbf6-4a9a184d1043)

- Base ISO images installed.
- NAT Network Applied to machines
- Shared Folder Created 

![image](https://github.com/user-attachments/assets/433ca734-83e7-4d39-8def-4f6613fdca8d)







## Objective: Install & Configure Symon & Splunk

Targets: Windows Machine, Windows Server


### Splunk Server - Linux Headless - 192.168.10.10:8000
- Installed Splunk Enterprise on machine
- Enable Splunk to start when booted 

### Windows 10 Client - 192.168.10.100
- Download Splunk Forwarder
- Download Sysmon from sysinternals
- Download Sysmon Olaf config file

![image](https://github.com/user-attachments/assets/e4d8170c-4a6b-464e-a4a6-27e75d8090ac)

- Need to edit the forwarder, go to C:\Program Files\SplunkUniversalForwarder\etc\system\local .> (Copy MyFDIR splunk inputs.conf)
- Restart forwarder service, change log on as to local system
- Created endpoint index

![image](https://github.com/user-attachments/assets/70ba60f1-18a9-4729-be8f-20fa5521f072)


- Go to Forwarding and receiving, create listening port on 9997
- We can see if its working now by checking the index for our target pc

![image](https://github.com/user-attachments/assets/bcf176dd-39a5-4106-b0b5-f7ee90007dd4)



### Windows 2022 Server- 192.168.10.7
- Download Splunk Forwarder
- Download Sysmon from sysinternals
- Download Sysmon Olaf config file

- Need to edit the forwarder, go to C:\Program Files\SplunkUniversalForwarder\etc\system\local .> (Copy MyFDIR splunk inputs.conf)
- Restart forwarder service, change log on as to local system
- Now we can check to see if everythings working:

![image](https://github.com/user-attachments/assets/5c4aa173-0283-4ef1-bdcf-a49dc32c051e)



## AD Install:

### Windows 2022 Server- 192.168.10.7

- Add roles and Features
- Active Directory Domain Services
- Finish Install, go back to server manager and click flag to promote this server to a domain controller
- Add a new forest, create top level domain, shrine.local

- Creating Users
- Uses and computers, create any OUs or Users


- Adding Computer to Domain
- On target pc, settings > systems properties > advanced > Domain 


## Objective:

- Use Kali linux to perform brute force attack

- Query activity using splunk

- Setup and install ART to run atomic test


### Set Kali Linux - 192.168.10.250


