Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/182269745-9543bb1b-e5c8-4d8e-a3d4-163323e6fb22.png)

![image](https://user-images.githubusercontent.com/93418272/182269762-42759987-36d0-475f-80d9-863b9e5f04a0.png)

![image](https://user-images.githubusercontent.com/93418272/182269773-f6a8ab88-a98e-4406-b7e3-1afc4235863c.png)


Visiting port 80 will redirect to 443, which is a Elastix webserver.

![image](https://user-images.githubusercontent.com/93418272/182269777-565be0c2-e4b9-4fa8-a996-0599b96df6b3.png)

![image](https://user-images.githubusercontent.com/93418272/182269781-16ca96b9-e2bf-4aa5-a0b3-383715f93786.png)


Run a gobuster scan to find for directories.

![image](https://user-images.githubusercontent.com/93418272/182269791-6dece84e-2e75-4c2e-9567-c950fc41007f.png)


A web mail portal.

![image](https://user-images.githubusercontent.com/93418272/182269801-b5016814-c641-4e79-a323-1a5c95113fb2.png)


An admin page.

![image](https://user-images.githubusercontent.com/93418272/182269808-0d1019db-d0d0-46ba-ab3d-cce639ac7b05.png)


Run a searchsploit 

![image](https://user-images.githubusercontent.com/93418272/182269829-fe1d370f-d6a4-4dbb-b630-9c845007b8d4.png)


Google search the LFI exploit.

![image](https://user-images.githubusercontent.com/93418272/182269846-9f76f88b-94bd-469e-8b89-79988783a4e6.png)


Use the LFI Exploit script below.

![image](https://user-images.githubusercontent.com/93418272/182269860-cb6d0055-b94f-41fb-afeb-52c7c3f68e87.png)


Found some credentials. 

![image](https://user-images.githubusercontent.com/93418272/182269876-bd0cb063-612f-49a0-9501-7d3d2321edc7.png)


passw0rd & jEhdIekWmdjE

Login to the admin page with the 2nd password found. 

![image](https://user-images.githubusercontent.com/93418272/182269895-88a37c61-3f37-4341-a5df-7101fb43f89b.png)


Nothing much can be done.

Let's use the credentials found to login into port 10000 aka webmin.

![image](https://user-images.githubusercontent.com/93418272/182269912-c7abf195-cbdb-41da-af25-e422da36eb92.png)

![image](https://user-images.githubusercontent.com/93418272/182269927-5d47b72d-b3e6-4ef0-b4dd-a44be948a598.png)

In the module config tab we are able to schedule a command. Let's schedule a  bash reverse shell nc listener. 

![image](https://user-images.githubusercontent.com/93418272/182269948-684cf52f-084c-4cf2-9cbd-5fc190701ae2.png)

![image](https://user-images.githubusercontent.com/93418272/182269960-3aa22a68-366e-4e10-aef2-830ec77b3354.png)

![image](https://user-images.githubusercontent.com/93418272/182269988-6717bf8d-d40c-4211-9d85-60f863d59e7d.png)


Start up nc before the scheduled commands and root access is gained. 

![image](https://user-images.githubusercontent.com/93418272/182270002-6ca059ec-879e-46a0-be7e-9a454ac54f2e.png)


First flag is found in fanis 

![image](https://user-images.githubusercontent.com/93418272/182270019-1476a47d-0e7f-4bfc-a36a-2710852c5c20.png)


Root flag is found.

![image](https://user-images.githubusercontent.com/93418272/182270032-9e59874b-a058-4f86-87de-cd14f240262a.png)
