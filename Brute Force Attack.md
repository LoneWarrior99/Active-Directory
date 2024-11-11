
# Objective:
- Use Kali linux to perform brute force attack

- Query activity using splunk

- Setup and install ART to run atomic test

--- 

### Set Kali Linux - 192.168.10.250
- Made ad-project directory
- Copied Rockyou.txt file to Directory
- Made a password.txt with adding user's password

--- 
### Brute Force Attack
On our Kali machine I installed crowbar for our bruteforce tool and use it to simulate an attack.

![image](https://github.com/user-attachments/assets/179dddb7-7831-4f13-bcb7-1d43ddce618f)

We can see we have an RDP-SUCCESS with the target user using our wordlist.

Lets take a look at Splunk and see what we find.

![image](https://github.com/user-attachments/assets/d6341f9d-9ab3-4a23-bd06-873be56ffa2e)

Searching from a target users we can see look at the event codes to see whats happenening.

Event 4625 tells us bad logins and Event 4624 tells us successfully logins.

![image](https://github.com/user-attachments/assets/08b94cbc-fbb5-48a4-b0e4-830598d3df55)

Looking at the Event Code 4625, we can see multiple attemepts within seconds of eachother which would be an indicator of a brute force attack.

If we turn to Event Code 4624, we can see who logged in and our attack machine information.

![image](https://github.com/user-attachments/assets/7c95d0cb-d3c0-4dbe-baa4-8073abd52512)

