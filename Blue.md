Run a nmap scan to find for open ports.
![image](https://user-images.githubusercontent.com/93418272/177671726-78fe9342-d61d-49e3-a5a3-3477e1e87b7b.png)

Let's use an nmap vulnerability script to find for more clues.
![image](https://user-images.githubusercontent.com/93418272/177671740-ae0da7eb-c83e-48b3-99db-98e13d9b9b18.png)

Found a CVE.
![image](https://user-images.githubusercontent.com/93418272/177671756-40d4c3fb-6ce8-4927-84e9-f419b6b90936.png)

Start up metasploit.
![image](https://user-images.githubusercontent.com/93418272/177671772-f4866447-bc1a-4423-9f22-af950015675d.png)

Search for smbv1 and use the eternalblue exploit.
![image](https://user-images.githubusercontent.com/93418272/177671786-4b0f3201-8cc1-4ec0-be9b-7f52586b0110.png)

Set up the necessary option values. 
![image](https://user-images.githubusercontent.com/93418272/177671797-7b790112-89cd-4097-957a-a1cc1de8a9ed.png)

Run the exploit.
![image](https://user-images.githubusercontent.com/93418272/177671810-b14fc874-eaaf-48b1-a5e0-30fab0d4cb52.png)

Session is gained.

Change directory to user Harris desktop to get the user flag.
![image](https://user-images.githubusercontent.com/93418272/177671843-aff7b874-7e8f-4dbf-b67b-9070f936f7c6.png)

Head to the root desktop to get the root flag.
![image](https://user-images.githubusercontent.com/93418272/177671860-b517bee9-1f92-4030-9e44-deff35667264.png)
