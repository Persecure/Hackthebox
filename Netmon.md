https://app.hackthebox.com/machines/Netmon

Review

- FTP server can be accessed anonymously
- Search for default credentials for interfaces
- Basic passwords are vulnerable
- CVE-2018-9276 : An attacker who has access to the PRTG System Administrator web console with administrative privileges can exploit an OS command injection vulnerability
- PRTG Network Monitor 18.2.38 - (Authenticated) Remote Code Execution scripts creates a new administrator user for us to access

## Enumeration

Run nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/184788889-02c0276b-aa5d-43bb-addd-8e4898552428.png)

![image](https://user-images.githubusercontent.com/93418272/184788903-7922743d-8659-4e38-99d3-112289a9163d.png)


Run a gobuster scan to find for hidden directories. 

![image](https://user-images.githubusercontent.com/93418272/184788913-a9556a0f-4222-494b-a4f6-f2ebb095cc7f.png)


The scan doesn't provides any clues.

The webserver shows us a network monitor interface.

![image](https://user-images.githubusercontent.com/93418272/184788925-2a4002bc-9c34-4684-8af6-94766b776b41.png)


Google for default credentials.

![image](https://user-images.githubusercontent.com/93418272/184788936-1f205fe5-ef69-4454-9655-cfbd68037209.png)


Unable to login via default credentials.

![image](https://user-images.githubusercontent.com/93418272/184788947-c46ab2e5-682d-4f96-9620-b34d56d19cb9.png)


Check out ftp anonymous server login.

![image](https://user-images.githubusercontent.com/93418272/184788957-7aadfdf7-25b3-4d92-8dc6-bfa4551ba6b7.png)


The public folder has the user.txt file.

![image](https://user-images.githubusercontent.com/93418272/184788972-a2939e78-a636-4868-9c37-a7a3a8da96a4.png)


First flag is found.

![image](https://user-images.githubusercontent.com/93418272/184788980-435549f7-7357-458a-853d-cb2772208150.png)


Exploring the Users folders we find the PRTG Network Monitor config files.

![image](https://user-images.githubusercontent.com/93418272/184789005-4c17c98b-4a24-4916-94cb-f826917d1ef6.png)


Download these files and search for prtgadmin to find for any clues.

![image](https://user-images.githubusercontent.com/93418272/184789030-275537b3-bb74-45e7-9419-7c283d2bb1ee.png)


Tried it with the password but login failed. Since the password is in the old config file and has the year 2018, let's increase to 2019.

Access gained.

![image](https://user-images.githubusercontent.com/93418272/184789050-20cc1925-23ac-44ae-ba5a-483d90ac5955.png)


## Foothold

Google exploits for PRTG-Network and we can find a RCE exploit here .

Download the script to the machine.

![image](https://user-images.githubusercontent.com/93418272/184789090-dddc2bf2-052e-44dd-8886-0aa86b95c932.png)


To use the script cookies of the login page need to be included.

![image](https://user-images.githubusercontent.com/93418272/184789102-1680f873-ec99-44fc-9ab5-1adfe8f96994.png)


Run the script.

![image](https://user-images.githubusercontent.com/93418272/184789122-db528216-90dd-4f82-b2f0-d3738118e487.png)


## Privilege escalation

With the newly created password and user we can gain access by evil winrm.

![image](https://user-images.githubusercontent.com/93418272/184789157-9dc7cf30-2697-468a-ae9e-35e268df245a.png)


The final flag is found.

![image](https://user-images.githubusercontent.com/93418272/184789176-9f7f8cc0-2bbd-463c-b74b-e7c3edbf6f36.png)
