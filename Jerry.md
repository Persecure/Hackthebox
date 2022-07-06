Run nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/177588890-0daeb4cc-8c0d-4311-af11-a7b268e1cc7a.png)

An Apache webserver is open on port 8080.
![image](https://user-images.githubusercontent.com/93418272/177589005-90b2f098-a58d-42a7-9298-ed05e459260d.png)

Found default credentials which exploring the Host Manager.
![image](https://user-images.githubusercontent.com/93418272/177589049-abef3f3e-4a54-438f-8d23-0f45abe3292c.png)

Start up metasploit and search for apache tomcat exploits 
![image](https://user-images.githubusercontent.com/93418272/177589072-467ed703-7fb2-4208-9f8f-8e6b34187ea6.png)

Use the Apache Tomcat Manager Authenticated Upload Code Execution exploit
![image](https://user-images.githubusercontent.com/93418272/177589110-ba453684-4c91-44c3-b3a2-159e62d45128.png)

Set the following options.
![image](https://user-images.githubusercontent.com/93418272/177589138-05e9ffb0-e6fa-4bc8-86a8-9a43d8625628.png)

Run the exploit and a session is gained.
![image](https://user-images.githubusercontent.com/93418272/177589157-ce361aab-9004-4cfe-873c-fc674166bfb3.png)

Change directory to administrator and desktop and a flags folder is found.

![image](https://user-images.githubusercontent.com/93418272/177589183-df6c6758-cace-4d39-abc5-549deaf4864d.png)

Both flags are found.
