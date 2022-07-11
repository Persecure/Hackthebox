Run a nmap scan to find for open ports. 

![image](https://user-images.githubusercontent.com/93418272/178170287-4fd45f35-c399-487f-8f74-e8319ac46b97.png)

The standard SMB ports are open.

Run a nmap vuln script to find for known vulnerabilities since it is a legacy machine. 

![image](https://user-images.githubusercontent.com/93418272/178170360-ec0163f0-00a5-461a-939b-56ebdb3b9ede.png)

MS08-067 & ms17-010 exploits. 

Start up msfconsole and search for the exploit. 

![image](https://user-images.githubusercontent.com/93418272/178170594-cf5665f1-bf12-4972-853a-0ad9a053a641.png)

Set up the necessary options and run the exploit to gain a meterpreter session.

![image](https://user-images.githubusercontent.com/93418272/178170698-660eecd7-4a26-4655-89bd-4ddc562d4e50.png)

Head to the john's folder to get the user flag.

![image](https://user-images.githubusercontent.com/93418272/178170843-f510045e-b5fc-4848-8201-dbb46b6ae591.png)

Head to the root folder to get the root flag.

![image](https://user-images.githubusercontent.com/93418272/178170978-7e8ad4c7-277d-479d-a8fe-7a3d94f5ccb4.png)

