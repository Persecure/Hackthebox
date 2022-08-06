https://app.hackthebox.com/machines/Knife

Run a nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/183225092-69fc4537-086d-46d2-8bcd-37f39e8501ab.png)

Webpage shows some kind of medical interface. 

![image](https://user-images.githubusercontent.com/93418272/183225100-6fe2fb3e-b019-4b0b-98f6-e5ca851141a6.png)

Gobuster shows its run by PHP

![image](https://user-images.githubusercontent.com/93418272/183225118-2b07e55f-2cff-428b-8fdf-0ba61bedc479.png)


Use the curl command to get more info.

![image](https://user-images.githubusercontent.com/93418272/183225125-41fac985-926d-4a05-94d8-ca963ca555d4.png)


Using searchsploit with the PHP version we are able to get a RCE exploit.

![image](https://user-images.githubusercontent.com/93418272/183225128-33cf8347-dea4-44ac-947d-32a69be31725.png)


Download the exploit and run the python script.

![image](https://user-images.githubusercontent.com/93418272/183225132-d7cf3ce4-11c1-4871-8dc7-d62e2ae4aee2.png)


A shell is gained.

![image](https://user-images.githubusercontent.com/93418272/183225139-90c18c4c-795e-43c8-a526-2ddaccbde8f7.png)


Nothing much besides the ls command be used in this. We can ls the user.txt file.

![image](https://user-images.githubusercontent.com/93418272/183225147-0ca3696a-06c6-419a-8f6f-e6190217c7f5.png)


sudo -l shows that the james user can use sudo knife

![image](https://user-images.githubusercontent.com/93418272/183225161-af415fe4-7350-4fbb-a850-9aed6a2f0c1e.png)


We need a sub command to run the knife function. There are multiple sub commands available and after googling, knife exec seems to have some potential. 

![image](https://user-images.githubusercontent.com/93418272/183225177-3909be29-3ed7-4f46-937a-ba65fc5595a0.png)

![image](https://user-images.githubusercontent.com/93418272/183225183-b22b97cc-ddfe-49ba-8f1a-baa73a069cee.png)


Run the following ruby script and use the knife command to get the root flag.

![image](https://user-images.githubusercontent.com/93418272/183225195-1e68d18a-9432-461f-af3c-c5a58f7e07e5.png)

![image](https://user-images.githubusercontent.com/93418272/183225197-a68572b6-da66-48bf-b5ef-fafbfcc767d1.png)

