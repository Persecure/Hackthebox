https://app.hackthebox.com/machines/Mirai

Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/183315964-fbc9f575-6ff1-4372-96e4-0958a94c1598.png)


Scanning all the ports.

![image](https://user-images.githubusercontent.com/93418272/183315971-06e66440-7f3f-4e8d-a5ce-6562daf3873d.png)


Webserver does not show anything.

![image](https://user-images.githubusercontent.com/93418272/183315973-ded5f680-2c12-4f2c-8ee1-4dcfd6d486d5.png)


Run a gobuster scan to find for other directories.

![image](https://user-images.githubusercontent.com/93418272/183315978-a58f688a-dc81-4b09-ae2c-0aeea094c091.png)


Head to the admin page. Seens like a Pi-hole interface.

![image](https://user-images.githubusercontent.com/93418272/183315984-c1be058b-399c-4960-9e50-a0ef45c8f9eb.png)


Search for default credentials. 

![image](https://user-images.githubusercontent.com/93418272/183315990-fbc400df-2160-49e0-8089-e03c3648c4c9.png)


Default credentials does not work for this interface.

![image](https://user-images.githubusercontent.com/93418272/183316001-314fcf30-c586-415d-91d6-a3a854c24287.png)


Let's try logging in via SSH.

![image](https://user-images.githubusercontent.com/93418272/183316007-ce5a227b-dc1f-4d8a-a29b-ff8f7f7895a9.png)


Able to gain access via default credentionals.

![image](https://user-images.githubusercontent.com/93418272/183316020-d90cc1db-178c-4fff-9c0b-89a7334f25f0.png)

Able to use sudo everywhere.

First flag is found.

![image](https://user-images.githubusercontent.com/93418272/183316026-e1dd6ad4-1ca1-48df-aba1-bdae593c0767.png)

Switch user to root and cat the root.txt file.

![image](https://user-images.githubusercontent.com/93418272/183316034-d4ad3673-4323-485c-a1d1-302a7fa19ab8.png)

Use the df command to find for all devices on the box

![image](https://user-images.githubusercontent.com/93418272/183316044-ab10e478-0aaa-413a-b110-46906ee24176.png)

Check out the usbstick folder and a clue is given.

![image](https://user-images.githubusercontent.com/93418272/183316051-79c406c3-1a60-404a-be7e-ab91fe7ad351.png)

Use the strings command to find the flag.

![image](https://user-images.githubusercontent.com/93418272/183316059-1e3fca3f-6a08-4d20-99c4-f167dcb3093d.png)
