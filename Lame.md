Run a nmap scan to find for open ports.
![image](https://user-images.githubusercontent.com/93418272/177899800-19cc24c2-e8a1-4398-af42-4c83573c7c6b.png)

Examined the Anonymous FTP login but no clues inside.
![image](https://user-images.githubusercontent.com/93418272/177899822-ad609b8a-f6b4-4178-8c19-81eaf8042b91.png)


The smb version is 3.0, use searchspolit to find for exploit.
![image](https://user-images.githubusercontent.com/93418272/177899845-ffc69e09-102b-417c-b071-57ca7ec732e3.png)


The username map script command execution looks interesting.

Start up metasploit.
![image](https://user-images.githubusercontent.com/93418272/177899875-6bcfcf01-9526-498b-9547-8f56c8ba5c3c.png)


Use the usermap_script.

![image](https://user-images.githubusercontent.com/93418272/177899891-f268fd91-9940-40f8-ab6c-58b109df9016.png)

Set up the options and run the exploit.
![image](https://user-images.githubusercontent.com/93418272/177899918-28b9886d-82b8-42a3-a1e0-e9363442a614.png)


Session is gained.
![image](https://user-images.githubusercontent.com/93418272/177899938-f5ba5b75-7e19-465a-b156-e1b4f47e07a7.png)


Head to the makis directory to find the user flag.

![image](https://user-images.githubusercontent.com/93418272/177899951-69f8a623-b31a-4486-aa1c-fa66af0bf0f1.png)


Then head to the root folder to find the root flag.

![image](https://user-images.githubusercontent.com/93418272/177899959-49f32146-1480-42c9-906a-a0360663ab3a.png)


