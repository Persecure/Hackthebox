Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/178629959-4e4924f1-2b96-4f49-999e-dc7415d5ddfb.png)

Port 80 shows some kind file server.

![image](https://user-images.githubusercontent.com/93418272/178629977-d15e938c-3bc2-4cc4-828d-040eb7a01ff3.png)

Searchsploit shows a vulnerability exploit in HttpFileServer.

![image](https://user-images.githubusercontent.com/93418272/178629999-2208af53-8a47-4059-b232-c1accc4c544e.png)


Start up metasploit and search for this exploit.

![image](https://user-images.githubusercontent.com/93418272/178630017-a5b91a9d-5129-4c6d-992a-98ea1b5846fc.png)


Set the necessary options and run the exploit.

![image](https://user-images.githubusercontent.com/93418272/178630034-e0763491-369d-42ce-af38-d14cbd93ac94.png)


The user flag is found in kostas Desktop folder.

![image](https://user-images.githubusercontent.com/93418272/178630055-30eb90d4-34f1-4fe8-b82a-92a60a3d9d8a.png)

We do not have admin rights with this account.

![image](https://user-images.githubusercontent.com/93418272/178630072-80703293-a0c4-4d50-b0ae-8b1be35f00f3.png)


We need privilege escalation to get the root flag. Background the session and use a local exploit suggestor.

![image](https://user-images.githubusercontent.com/93418272/178630086-317a2195-fa13-4218-9a61-4076466a1d45.png)


Failed to gain acess.

![image](https://user-images.githubusercontent.com/93418272/178630110-4e079cdd-9b4c-45f4-a134-daa701e26360.png)


From the first session , we can see it uses Windows 2012 R2 and it's Architecture is x64.

![image](https://user-images.githubusercontent.com/93418272/178630128-ab5e4eb6-77ea-41a7-95c8-38f9d0bd8553.png)


Search for an exploit for Windows 2012 R2

![image](https://user-images.githubusercontent.com/93418272/178630145-19eb6783-369a-4f4e-8864-f41277a31270.png)


Search for this exploit

![image](https://user-images.githubusercontent.com/93418272/178630160-8b4a6fce-b273-4423-b47a-c2eb0139d65f.png)


Set up the options and the payload to the x64 Architueure.

![image](https://user-images.githubusercontent.com/93418272/178630185-1db18189-c2f1-4b35-832b-45f0402f2e6d.png)


Run the exploit and access is gained.

![image](https://user-images.githubusercontent.com/93418272/178630205-ff1ec5ca-b665-4073-97f6-a40d9809b26f.png)


Get the root flag.

![image](https://user-images.githubusercontent.com/93418272/178630221-039ddc6a-eeae-4523-8c5e-fb212cdad6b6.png)
