https://app.hackthebox.com/machines/Sense

Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/182502084-4d808413-6aa9-4fc1-811b-8fe5f714815a.png)


The webserver leads to PF SENSE login page.

![image](https://user-images.githubusercontent.com/93418272/182502094-8bbd9a7c-324f-4dee-8231-c6080dc994a8.png)


Default Username and Password does not give us access. 

![image](https://user-images.githubusercontent.com/93418272/182502109-7a4d904a-4ed4-42a1-8b8a-7247d9ed2b9d.png)


Run a gobuster scan to find for directories.

![image](https://user-images.githubusercontent.com/93418272/182502126-9b2aef90-3167-463e-99bf-2ea10affaf8a.png)


changelog.txt gives us a clue.

![image](https://user-images.githubusercontent.com/93418272/182502136-b46a5b6c-b046-4524-8475-f61063a26106.png)


Found a user with default password.

![image](https://user-images.githubusercontent.com/93418272/182502143-6ff0552b-df22-4b2d-b6f4-9eb09f12c9a6.png)


Login with user: rohit & password: pfsense

![image](https://user-images.githubusercontent.com/93418272/182502152-14a266fc-4285-47db-a14b-d6a037475fa9.png)


Version is found.

Run a searchsploit on pfsense.

![image](https://user-images.githubusercontent.com/93418272/182502180-df8c4772-88d5-4aef-934e-673f6cfd1cd8.png)


Found a possible command injection.

Download the exploit and examine the python source code.

![image](https://user-images.githubusercontent.com/93418272/182502197-0d2b8dfc-4cf1-4b6e-b481-8a3408be707e.png)


Able to get a reverse shell with this exploit.

Input the necessary details.

![image](https://user-images.githubusercontent.com/93418272/182502209-0a0e8d11-6500-40b1-ab79-2a3cfe26350b.png)


Before running the exploit start a netcat listener.

![image](https://user-images.githubusercontent.com/93418272/182502225-36f27764-0810-4189-a54a-e990484b7750.png)


A shell is gained.

![image](https://user-images.githubusercontent.com/93418272/182502251-21d893c1-a0ee-4409-a03f-4aaa31a2a6ca.png)


user.txt is found in rohit's folder.

![image](https://user-images.githubusercontent.com/93418272/182502262-a1d5c5da-8f6e-479c-982c-35d406d52824.png)


root.txt is found in root's folder.

![image](https://user-images.githubusercontent.com/93418272/182502278-5151c2e9-586f-4722-a2eb-01369e32a586.png)
