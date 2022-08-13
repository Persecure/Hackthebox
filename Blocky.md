https://app.hackthebox.com/machines/Blocky

## Enumeration

Run nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/184464247-4e87fe3e-bd5e-4c20-8bf1-b729789d09e8.png)


Unable to login via FTP anonymously.

![image](https://user-images.githubusercontent.com/93418272/184464254-2f03b2b8-2b54-4e70-9dc6-595fec7c1fc2.png)


Run a gobuster scan

![image](https://user-images.githubusercontent.com/93418272/184464257-20a11667-6495-41d9-8623-0fea4436525e.png)


There is a phpadmin page.

![image](https://user-images.githubusercontent.com/93418272/184464261-18b2dba7-7366-42c2-b1a0-b1c9b43ccb87.png)


Wpscan shows no results.

The plugins directory have 2 files inside.

![image](https://user-images.githubusercontent.com/93418272/184464269-60d6a22c-7894-45cc-b3ac-0d08a604a835.png)


Use a java decompiler like jdi-gui to open up the file.

Found some mysql credentials.

![image](https://user-images.githubusercontent.com/93418272/184464274-d9aadbc3-7e73-4677-970a-23c11aa660c3.png)


The 2nd file has a whole bunch of functions, let's put this aside for now. 

Let's login with the credentials via the phpmyadmin page. 

![image](https://user-images.githubusercontent.com/93418272/184464280-23009f91-a7d1-46ce-9438-2e2dfb567618.png)


Access gained.

In the wordpress section page there is a credential found.

![image](https://user-images.githubusercontent.com/93418272/184464285-24294a04-d6cf-464a-976d-e5d01b4a86c3.png)


## Foothold

SSH login via the user notch and the password found in the jar file.

![image](https://user-images.githubusercontent.com/93418272/184464291-3574fce4-98bb-43d1-9951-5bb48d27908a.png)


First flag is found

![image](https://user-images.githubusercontent.com/93418272/184464294-23fc0aa2-7d9e-4ad5-93ae-8333c401fb0a.png)


## Privilege escalation

Check sudo -l 

![image](https://user-images.githubusercontent.com/93418272/184464298-ef311acb-3086-48c5-85a0-8c34edc2b15b.png)


We are able to sudo everything.

Change to root user and get the final flag.

![image](https://user-images.githubusercontent.com/93418272/184464310-3deec336-4ea7-46a9-9018-b74403c75c65.png)
