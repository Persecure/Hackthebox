https://app.hackthebox.com/machines/Arctic

Enumeration

Run nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/184278379-28516fe8-76b2-4e0b-b4a8-d97b286bb523.png)


Port 8500 gives us the following:

![image](https://user-images.githubusercontent.com/93418272/184278384-40994d3f-dd77-4ff1-b1c7-debd7f5b4c6f.png)

![image](https://user-images.githubusercontent.com/93418272/184278389-f0a869a6-15b1-4db8-9318-944c5872128b.png)


CFIDE seems like some kind of interface

![image](https://user-images.githubusercontent.com/93418272/184278399-0c8384c0-9fe4-4cd0-bf11-2d13d33827c9.png)


Heading to the administrator page we can find login interface with version number.

![image](https://user-images.githubusercontent.com/93418272/184278414-0beb2fe9-c860-44e4-8d8b-7184d4211ee4.png)


Found a potential exploit on searchsploit.

![image](https://user-images.githubusercontent.com/93418272/184278428-730cbcce-383c-42c2-bfc9-549060014b08.png)


Foothold

Download the exploit.

![image](https://user-images.githubusercontent.com/93418272/184278453-91ce40e1-4d84-4f71-83f4-b9ab25ff1fdb.png)


Edit the exploit with the necessary details.

![image](https://user-images.githubusercontent.com/93418272/184278460-ccfc36b1-571e-4f41-8f86-15aa6d6f4b7a.png)


Start a nc listener and run the exploit.

![image](https://user-images.githubusercontent.com/93418272/184278476-6e42fe72-0c39-4adf-a717-c77fb1145f8e.png)

A shell is gained.

First flag is found on user tolis desktop.

![image](https://user-images.githubusercontent.com/93418272/184278494-32b53bd9-c3ed-4c06-8db6-02cc4f990594.png)


Privilege escalation

Run the windows exploit suggester to find for potential exploits.

![image](https://user-images.githubusercontent.com/93418272/184278515-03112bff-3edb-407c-9496-d83a9ee31b1e.png)


Use MS10-059

Get the exploit from here.

Transfer the exploit the windows machine.

![image](https://user-images.githubusercontent.com/93418272/184278531-089f0e1c-7176-48fd-b0fd-d5e51673fbb3.png)


Run the exploit and start a nc listener.

![image](https://user-images.githubusercontent.com/93418272/184278551-552452a4-f741-4cd9-ad20-553eb6c76517.png)


A shell is gained.

![image](https://user-images.githubusercontent.com/93418272/184278566-afd712a8-52ea-42f3-b1d6-a5f692a15a0d.png)


Root flag is found.

![image](https://user-images.githubusercontent.com/93418272/184278580-514d03e0-2366-46fe-ac2c-0cd51dd3ef31.png)
