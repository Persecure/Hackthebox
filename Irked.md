## https://app.hackthebox.com/machines/Irked

Use nmap to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/183801538-92c4e9c5-fc93-4c71-a410-e0e288ee3692.png)

![image](https://user-images.githubusercontent.com/93418272/183801553-074e2518-82ce-4e19-8429-0dfd39d6b9d7.png)


## Enumeration

Run a gobuster scan to find for directories. 

![image](https://user-images.githubusercontent.com/93418272/183801596-468cbf39-89b2-47c5-8f7d-b348f3e1e99d.png)


Web server shows nothing interesting.

![image](https://user-images.githubusercontent.com/93418272/183801610-730e4bdc-1d1c-4da9-8535-f3766718eb15.png)


### RPC

![image](https://user-images.githubusercontent.com/93418272/183801635-39d5f2b3-5a03-4028-9d7d-f863670292a6.png)

![image](https://user-images.githubusercontent.com/93418272/183801644-e0bc4e71-4ccd-405f-94cc-a0a3b28cf3b6.png)


### IRC

![image](https://user-images.githubusercontent.com/93418272/183801671-fc695db2-b902-464a-8bbc-b6aec1a4e31b.png)

![image](https://user-images.githubusercontent.com/93418272/183801680-f97ca2e2-c2d7-425b-908e-82c0f36b6966.png)

Unreal server is version is 3.2.8.1  

Check searchsploit for vulnerabilities.

![image](https://user-images.githubusercontent.com/93418272/183801739-3af6e878-218f-4294-aae9-9b468a36bd9f.png)


Run the metasploit exploit and a shell is gained.

![image](https://user-images.githubusercontent.com/93418272/183801750-42b9ef71-b674-48c8-b82e-243ce9cf24cc.png)

Unable to view user.text but the .backup file gives us steg password.

![image](https://user-images.githubusercontent.com/93418272/183801767-ef5f9712-7059-4a6b-8f8a-004e5a25f944.png)

There was an image file in the webserver.

![image](https://user-images.githubusercontent.com/93418272/183801795-9ad2bcdc-2b12-4384-9d32-d70b67c0c192.png)

Get the image file.

![image](https://user-images.githubusercontent.com/93418272/183801820-abc6684c-1bfd-4f54-9d38-04017c6c6e8a.png)

Use steghide to extract information

![image](https://user-images.githubusercontent.com/93418272/183801839-6f4ab843-ca3e-463f-9b2e-c93618640155.png)

Found a password.

![image](https://user-images.githubusercontent.com/93418272/183801854-4f88dce5-be9a-4040-ab2e-5de4be0fe1a0.png)

Use ssh to gain a shell with the password.

![image](https://user-images.githubusercontent.com/93418272/183801873-4591e45f-5ea1-430f-ab9e-f02f5a8722d5.png)


First flag is found.

![image](https://user-images.githubusercontent.com/93418272/183801886-08b9efba-7026-4cf4-af89-a0a29cd7db22.png)


Find for setuid resources.

![image](https://user-images.githubusercontent.com/93418272/183801896-df8f58a8-018c-4325-b05c-69419323761d.png)


The /tmp/listusers is not found.

![image](https://user-images.githubusercontent.com/93418272/183801917-8359beda-2565-48a9-8c48-839c4bfe69b6.png)


Download the viewuser file into your local machine.

![image](https://user-images.githubusercontent.com/93418272/183801932-38bb0d97-9be6-4405-ac5c-bedbfb616c72.png)


Use ltrace to analyze the file.

![image](https://user-images.githubusercontent.com/93418272/183801941-bf267c40-ed9f-4a43-bf06-c169ef7097df.png)


binary runs as root, then it also executes /tmp/listusers as root. So we can simply get a reverse shell by putting the payload in /tmp/listusers, Then after running the binary again it should execute the payload.

Insert a reverse shell payload and run viewuser.

![image](https://user-images.githubusercontent.com/93418272/183801963-c087acda-1c1f-4c7a-a287-45e1000d5fea.png)


Root accessed is gained.

![image](https://user-images.githubusercontent.com/93418272/183801979-6db965e6-99a1-4b50-a6d1-a31c679e6634.png)
